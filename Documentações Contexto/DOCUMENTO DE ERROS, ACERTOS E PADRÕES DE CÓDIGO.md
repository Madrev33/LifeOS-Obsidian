### **Documento de Erros, Acertos e Padrões de Código (SOTA Obsidian)**

*Este documento consolida os aprendizados chave, erros comuns e os padrões de código que se provaram robustos durante o desenvolvimento do sistema.*

---

**I. ACERTOS: Padrões de Código que FUNCIONAM**

1.  **Acesso à API em Scripts (QuickAdd e Meta Bind):**
    *   A forma mais robusta e universal de acessar as APIs principais de dentro de um script é através do objeto `params` ou do `this` que o plugin injeta.
    *   **Padrão CORRETO (QuickAdd `module.exports`):**
        ```javascript
        module.exports = async (params) => {
            const { app, quickAddApi: qa, obsidian } = params;
            const moment = params.obsidian.moment;
            // ... seu código ...
        };
        ```
    *   **Padrão CORRETO (Meta Bind `inlineJS` ou `js-view`):**
        ```javascript
        // 'this.app' é a forma mais segura de obter a instância principal
        const dv = this.app.plugins.plugins["dataview"]?.api;
        // Tenta pegar 'moment' do escopo global (window), se não der, busca no plugin
        const moment = window.moment || this.app.plugins.plugins["templater-obsidian"]?.templater.date.moment;
        ```

2.  **Extração de Dados do Corpo da Nota (A Prova de Falhas):**
    *   Tentar usar a API do Dataview (`dv.page(..).file.sections` ou `...lists`) para extrair conteúdo de texto (como "Acontecimentos") é instável devido a problemas de cache.
    *   **Padrão CORRETO:** Ler o arquivo como texto bruto e usar uma "máquina de estados" para iterar linha por linha.
        ```javascript
        const conteudoArquivo = await app.vault.read(activeFile);
        const linhas = conteudoArquivo.split('\n');
        let estado = null; // Ex: 'acontecimento_manha', 'feitosHoje'

        for (const linha of linhas) {
            // Lógica para mudar o 'estado' com base em headings (###, ##)
            // Lógica para coletar dados com base no 'estado' atual
        }
        ```

3.  **Atualização de Frontmatter a partir de Scripts:**
    *   **Padrão CORRETO:** Usar `app.fileManager.processFrontMatter(arquivo, (fm) => { ... })`. É a forma oficial, segura e reativa.
    *   **Padrão SEGURO (dentro de DataviewJS/MetaBind):** Envolver a chamada em um `setTimeout` para evitar "condições de corrida" com a renderização do Obsidian.
        ```javascript
        setTimeout(async () => {
            await app.fileManager.processFrontMatter(activeFile, (fm) => {
                fm.campo = novoValor;
            });
        }, 150);
        ```

4.  **Sintaxe de Plugins em Blocos de Código:**
    *   **Tracker:** A sintaxe YAML é extremamente sensível. Nomes de chaves (`datasetName`, `yAxisLabel`, `xAxis`) devem ter o `case` exato e estar no nível de indentação correto. Listas devem usar o formato de hífen (`- item`).
    *   **Meta Bind Buttons:** A ação `updateMetadata` com valores dinâmicos deve usar `evaluate: true` e código JavaScript puro (`new Date()...`), não a sintaxe `{{...}}`.

---

**II. ERROS: Padrões de Código que FALHAM (e devem ser evitados)**

1.  **Erro: Dependência Cega do Cache do Dataview.**
    *   **Código que FALHA:** `dv.page("path/to/note").file.sections.find(...)` ou `dv.page(...).file.lists.where(...)` executado imediatamente após uma modificação de arquivo ou criação de nota.
    *   **Motivo:** O cache do Dataview não é instantâneo. O script pode rodar antes de o Dataview ter indexado a estrutura completa do arquivo, resultando em `undefined`.

2.  **Erro: Confusão de Tipos em Arrays Dataview.**
    *   **Código que FALHA:** `dv.pages(...).map(...).reduce(...)`
    *   **Motivo:** `.map()` em um `DataArray` do Dataview retorna outro `DataArray`, que não tem o método `.reduce()`.
    *   **Correção:** Sempre converter para um array JavaScript padrão antes de usar métodos de array nativos: `...map(...).values.reduce(...)`.

3.  **Erro: Sintaxe de Datas do Templater vs. Tracker Nativo.**
    *   **Código que FALHA:** Usar comandos complexos do Templater `<% ... %>` dentro de `startDate` ou `endDate` de um bloco `tracker`.
    *   **Motivo:** O Tracker não executa o Templater de forma confiável para obter as datas.
    *   **Correção:** Usar as datas relativas nativas do Tracker (`-1w`, `today`) ou, para máxima precisão, gerar o bloco `tracker` inteiro via um script `dataviewjs`.

4.  **Erro: Inserção de Scripts Multilinha no Frontmatter.**
    *   **Código que FALHA:**
        ```yaml
        campo: <%*
          let a = 1;
          let b = 2;
          tR += a + b;
        %>
        ```
    *   **Motivo:** Qualquer caractere (incluindo quebras de linha) antes da primeira linha `---` ou um valor YAML malformado quebra o frontmatter.
    *   **Correção:** Fazer o cálculo em um bloco `<%_ ... _%>` **antes** do frontmatter, salvar em uma variável, e então imprimir a variável no YAML: `campo: <% nomeDaVariavel %>`.

**III. LÓGICA DE NEGÓCIO E FILOSOFIA DO SISTEMA**

1.  **O "Dia Psicológico" vs. Dia do Calendário:**
    *   **Decisão Original:** A intenção era que os logs da madrugada (00:00 - 05:59) fossem registrados na nota do dia anterior.
    *   **Decisão Final (Robustez):** Devido a problemas de timing e complexidade, decidimos simplificar. **Logs são sempre registrados na nota do dia do calendário em que ocorrem.** A inteligência para "conectar" a madrugada ao dia anterior será feita nas *queries de visualização* (Fase 7), e não na captura de dados.
    *   **Aprendizado:** A captura de dados deve ser o mais simples e "burra" possível para garantir que nunca falhe. A complexidade e a inteligência devem residir na camada de visualização e análise.

2.  **Gamificação Baseada em Ação:**
    *   **Padrão CORRETO:** A pontuação de stats (Gênio, Resiliência) não deve ser dada no momento da *criação* de um desafio, mas sim na sua *conclusão*.
    *   **Implementação:**
        *   Scripts do QuickAdd criam a tarefa (`- [ ] ...`).
        *   Scripts `meta-bind-js-view` escaneiam a nota em busca de tarefas com `t.completed === true` para atribuir os pontos.
    *   **Aprendizado:** A recompensa deve seguir a conclusão do esforço para ser psicologicamente eficaz.

3.  **Responsabilidade Única dos Plugins:**
    *   **Padrão CORRETO:** Cada plugin deve ser usado para o que ele faz de melhor, evitando sobreposições complexas.
    *   **Exemplo de SUCESSO:** Para criar a nota de mídia, o **QuickAdd** executa um script que coleta os dados. O script então usa a **API nativa do Obsidian (`app.vault.create`)** para criar o arquivo, e o **Templater** é chamado explicitamente (`app.plugins.plugins['templater-obsidian']...`) se necessário. Não tentamos fazer o QuickAdd chamar um Template Choice que chama o Templater.
    *   **Exemplo de FRACASSO:** Tentar fazer um botão **Meta Bind** chamar um **comando QuickAdd** se provou instável. A solução foi fazer o botão Meta Bind executar um **`inlineJS`** que continha toda a lógica, eliminando o intermediário.
    *   **Aprendizado:** Menos "pontes" entre plugins para uma única ação resulta em um sistema mais estável.

---

**IV. PADRÕES DE INTERFACE E FLUXO DE TRABALHO (UX)**

1.  **Feedback Imediato ao Usuário:**
    *   **Padrão CORRETO:** Todos os scripts acionados pelo usuário (QuickAdd, botões) devem terminar com uma chamada a `new Notice("✅ Ação concluída!")`.
    *   **Motivo:** Isso fornece um feedback visual imediato de que a automação foi executada com sucesso, melhorando a experiência do usuário. Se uma ação falhar, a ausência da notificação é um sinal claro de problema.

2.  **Modularidade de Templates:**
    *   **Padrão CORRETO:** Em vez de um template monolítico, criamos templates específicos para cada "entidade" do sistema: `Daily Note`, `Weekly Note`, `Missao`, `Filme`, `Livro`, etc.
    *   **Aprendizado:** Isso torna a manutenção e aprimoramento muito mais fáceis. Mudar o template de "Filme" não corre o risco de quebrar o de "Livro".

3.  **Abstração para o Usuário:**
    *   **Padrão CORRETO:** A complexidade (scripts, queries) deve ficar "escondida" nos templates e na pasta `Backend Obsidian`. A interação do usuário no dia a dia deve ser simples: clicar em botões, usar comandos do QuickAdd e preencher campos.
    *   **Exemplo:** O usuário não precisa saber como o XP é calculado; ele apenas vê a tabela de "Perfil SOTA" na dashboard. Ele não precisa saber como os aprimoramentos são processados; ele apenas clica no botão.

---

**V. ESTRUTURA DE DADOS E METADADOS**

1.  **Consistência é Rei:**
    *   **Padrão CORRETO:** Todas as entidades do mesmo tipo devem ter a mesma estrutura de frontmatter. O uso de **templates** (`Missao_Template.md`, etc.) e **scripts de criação** (`criarMidia.js`) é crucial para garantir essa consistência.

2.  **Logs Auto-contidos:**
    *   **Decisão Final:** Cada linha de log gerada deve conter toda a informação necessária para ser analisada de forma independente.
    *   **Padrão CORRETO:** `- Conteúdo... #tag_tipo #periodo/nome (log_date::AAAA-MM-DD) (log_time::HH:mm:ss)`
    *   **Motivo:** Isso torna as queries futuras muito mais simples e robustas, pois não precisamos depender do nome do arquivo para saber a data de um log.

3.  **Status Manual vs. Status Dinâmico:**
    *   **Aprendizado:** Não se pode ter um único campo no frontmatter que seja ao mesmo tempo editado manualmente e calculado dinamicamente.
    *   **Padrão CORRETO:** Usar dois campos. Exemplo para mídias:
        *   `status_manual:` (editado pelos botões "Começar a Ler", "Finalizar").
        *   `Status: = choice(...)` (um campo Dataview inline no corpo da nota que exibe um status amigável baseado na pasta em que o arquivo está).

**VI. LIÇÕES APRENDIDAS POR PLUGIN (GUIA DE REFERÊNCIA RÁPIDA)**

1.  **`QuickAdd`**
    *   **Acerto:** Usá-lo como o principal motor para **captura de dados interativa**. A capacidade de criar menus (`suggester`) e pedir inputs (`inputPrompt`) o torna perfeito para criar notas estruturadas (`criarMidia.js`) ou logs complexos (`registrarEvento.js`).
    *   **Erro a Evitar:** Tentar criar fluxos complexos com múltiplos passos de "Choice" dentro de uma "Macro". Isso se mostrou instável.
    *   **Padrão de Ouro:** Criar uma **Macro** que chama um **único e poderoso User Script** que contém toda a lógica. O script é o "cérebro", a macro é apenas o "gatilho".

2.  **`Meta Bind`**
    *   **Acerto:** Perfeito para duas coisas:
        1.  **Inputs Interativos:** Criar `INPUT[slider]`, `INPUT[toggle]`, `INPUT[number]` no corpo da nota para modificar o frontmatter em tempo real.
        2.  **Cálculos Reativos:** Usar `meta-bind-js-view` para cálculos que dependem de outros campos do frontmatter. É o motor dos nossos Stats de Vida.
    *   **Erro a Evitar:** Usar `meta-bind-js-view` para ações que deveriam ser acionadas por um clique (como "Processar Aprimoramentos"). Ele é reativo, não um gatilho de evento.
    *   **Padrão de Ouro (para botões com lógica):** Usar um bloco `meta-bind-button` com `type: inlineJS`. Isso mantém a lógica contida e isolada, evitando conflitos com o QuickAdd ou outros plugins. A sintaxe YAML deve ser impecável.
    *   **Erro de Sintaxe Comum:** O erro `Invalid escape sequence` acontece ao usar `\` em caminhos de arquivo no Windows. **Sempre use barras normais `/`** nos caminhos dentro do YAML do botão.

3.  **`Dataview` (especialmente `dataviewjs`)**
    *   **Acerto:** Indispensável para **visualização e agregação de dados** em dashboards e notas de revisão. Perfeito para criar tabelas e listas dinâmicas.
    *   **Erro a Evitar:** Confiar no cache do Dataview (`dv.page(...).file.sections` ou `...lists`) dentro de scripts que rodam muito rápido (QuickAdd, Meta Bind). O cache pode estar desatualizado.
    *   **Padrão de Ouro (para extração de dados em scripts):** Ler o arquivo como texto bruto (`app.vault.read()`) e analisá-lo manualmente. Para buscar páginas, a query `dv.pages('"caminho/completo"')` é a mais confiável.
    *   **Erro de Tipo Comum:** O erro `.reduce is not a function` acontece porque `.map()` em um `DataArray` retorna outro `DataArray`. **Sempre use `.values`** para converter para um array JavaScript antes de usar `.reduce()`, `.filter()` nativo, etc.

4.  **`Tracker`**
    *   **Acerto:** Excelente para visualizações de séries temporais (gráficos de linha).
    *   **Erro a Evitar:** Usar comandos complexos do Templater para `startDate` e `endDate`. É instável.
    *   **Padrão de Ouro (Gráfico Simples):** Usar datas relativas nativas (`-30d`, `today`) quando possível, ou datas explícitas no formato `YYYY-MM-DD`. A chave `dateFormat: YYYY-MM-DD` é crucial para ele encontrar as notas diárias.
    *   **Padrão de Ouro (Gráfico de Resumo):** A sintaxe é completamente diferente. As configurações (`xAxisLabel`, `yAxisLabel`, `xAxisStep`) vão para dentro da seção `summary:`.

5.  **`Templater`**
    *   **Acerto:** Essencial para popular os templates no momento da criação, especialmente com dados dinâmicos como a data (`<% tp.date.now() %>`).
    *   **Erro a Evitar:** Colocar blocos de script multilinha (`<%* ... %>`) diretamente como valor de uma chave no frontmatter. Isso quebra o YAML.
    *   **Padrão de Ouro:** Executar a lógica em um bloco `<%_ ... _%>` **antes** do frontmatter, salvar o resultado em uma variável, e então imprimir essa variável no frontmatter: `campo: <% nomeDaVariavel %>`. O uso de `_` para controle de whitespace é fundamental para não quebrar o frontmatter.


# Logs de aprendizado

### **Entrada de Aprendizado #1: Erro de API em Botões Interativos**

*   **O Erro:**
    Botões `meta-bind-button` com `type: inlineJS` ou `type: command` que tentavam chamar a API do QuickAdd (`qa.suggester`, `quickadd:macro:...`) falhavam silenciosamente ou geravam o erro `qa.suggester is not a function`.

*   **A Causa Raiz:**
    Incompatibilidade de contexto e timing entre plugins. O ambiente de execução do Meta Bind não garante que a API do QuickAdd esteja inicializada, disponível e no escopo correto para ser chamada diretamente por um script `inlineJS`. A ponte entre os dois plugins para ações de UI interativa se provou instável e não confiável.

*   **A Solução/Padrão de Ouro:**
    Redesenhar a interação para usar as ferramentas nativas de cada plugin, eliminando a dependência cruzada. Em vez de um botão acionar um prompt, a seleção é feita diretamente na nota.
    1.  **Simplificar o script de criação (`criarArtigo.js`):** Remover todas as perguntas interativas (`suggester`, `inputPrompt`) do fluxo inicial, deixando-o focado apenas nos dados essenciais (título, autor, url).
    2.  **Usar Inputs Nativos do Meta Bind no Template:** Adicionar campos `INPUT[suggester(optionQuery(...))]` diretamente no corpo da nota (`Artigo_Template.md`).
    3.  **Fonte de Dados Centralizada:** Criar notas dedicadas (ex: `Fontes de Artigos.md`) contendo as opções como tags (ex: `#artigo_fonte Blog`). A `optionQuery` busca dinamicamente essas tags em todo o vault.

    **Exemplo de Código (no template):**
    ```markdown
    - **Fonte:** `INPUT[suggester(optionQuery(#artigo_fonte), allowOther):fonte]`
    - **Categoria:** `INPUT[suggester(optionQuery(#artigo_categoria), allowOther):categoria]`
    ```

    **Aprendizado Crucial:** Para *seleção de dados* em uma nota, o `INPUT[suggester]` do Meta Bind é superior e mais robusto do que um botão que chama o QuickAdd. A lógica de "um botão para tudo" não é a ideal; a melhor solução é a que usa a ferramenta mais especializada para a tarefa.

---

### **Entrada de Aprendizado #2: Instabilidade em Queries Dataview Inline**

*   **O Erro:**
    Queries `dataviewjs` inline, como `= dv.elink(dv.current().url, "Acessar")`, falhavam esporadicamente com o erro `Cannot call type 'null' as a function`.

*   **A Causa Raiz:**
    Problema de timing. A query era executada antes que o índice global do Dataview estivesse completamente pronto, fazendo com que `dv.current()` retornasse `null` ou um objeto incompleto.

*   **A Solução/Padrão de Ouro:**
    Para queries inline que se referem a metadados da **própria página**, usar o objeto `this` em vez de `dv.current()`. Adicionalmente, para funcionalidades complexas como links externos, optar pela sintaxe Markdown mais fundamental e direta.

    **Código que FALHA (instável):**
    ```markdown
    `= dv.elink(dv.current().url, "Acessar")`
    ```
    **Código que FUNCIONA (robusto):**
    ```markdown
    [Acessar](`= this.url`)
    ```

    **Aprendizado Crucial:** A simplicidade supera a complexidade. Usar a sintaxe mais básica e direta (Markdown puro) com a referência mais confiável (`this`) é mais resiliente a problemas de cache e timing do que depender da execução de funções complexas de uma API (`dv.elink`).

---

### **Entrada de Aprendizado #3: Atualização de Frontmatter a partir de `dataviewjs`**

*   **O Erro:**
    O campo `tempo_foco_total` no frontmatter não era atualizado, apesar de o cálculo aparecer corretamente na tabela `dataviewjs`.

*   **A Causa Raiz:**
    Confusão de responsabilidades. Um bloco `dataviewjs` é projetado para **ler e exibir** dados. Embora possa executar `app.fileManager.processFrontMatter`, seu ciclo de vida de renderização pode causar inconsistências. A tentativa de usar `setTimeout` dentro dele é uma gambiarra, não uma solução arquitetural.

*   **A Solução/Padrão de Ouro:**
    Separar completamente a lógica de **visualização** da lógica de **atualização**.
    1.  **Bloco `dataviewjs`:** Responsável apenas por ler os logs e renderizar a tabela detalhada para o usuário.
    2.  **Bloco `meta-bind-js-view` (com `hidden`):** Responsável apenas por ler os logs, calcular o valor total e usar `app.fileManager.processFrontMatter` para atualizar o frontmatter. Este bloco funciona como um "processador de fundo" reativo e invisível.

    **Exemplo de Código (no template):**
    ```markdown
    <!-- Bloco de Visualização -->
    ```dataviewjs
    const pomodoros = dv.pages(...).where(...);
    dv.table(["Sessão", "Duração"], pomodoros.map(p => [...]));
    ```

    <!-- Bloco de Atualização (invisível) -->
    ```meta-bind-js-view
    {data} as dataDummy
    hidden
    ---
    // Lógica de cálculo...
    const tempoTotalFormatado = ...;
    if (dv.current().tempo_foco_total !== tempoTotalFormatado) {
        await this.app.fileManager.processFrontMatter(...);
    }
    ```

    **Aprendizado Crucial:** Não misture a responsabilidade de exibir dados com a de modificar dados no mesmo bloco de script. Use a ferramenta certa para cada trabalho: `dataviewjs` para visualização, `meta-bind-js-view` para cálculos reativos que resultam em escrita de metadados.


### **Entrada de Aprendizado #4: Chamada Incorreta de API no QuickAdd**

*   **O Erro:**
    Ao tentar executar uma macro a partir de um User Script, a chamada `qa.executeMacro("Nome da Macro")` resultou no erro `TypeError: qa.executeMacro is not a function`.

*   **A Causa Raiz:**
    Uso de um nome de método inexistente na API do QuickAdd. A suposição de que o método se chamaria `executeMacro` estava incorreta. A consulta à documentação do plugin é um passo indispensável que foi omitido, levando ao erro.

*   **A Solução/Padrão de Ouro:**
    Utilizar o método correto fornecido pela API do QuickAdd para executar qualquer tipo de "Choice" (seja Template, Capture, ou Macro). O método correto é `qa.executeChoice("Nome da Choice")`.

    **Código que FALHA (método incorreto):**
    ```javascript
    await qa.executeMacro("Minha Macro");
    ```

    **Código que FUNCIONA (método correto):**
    ```javascript
    // Pré-requisito: Deve existir uma "Choice" do tipo "Macro" com este nome
    // nas configurações do QuickAdd.
    await qa.executeChoice("Minha Macro");
    ```

    **Aprendizado Crucial:** Nunca assuma o nome de um método de API de um plugin. Sempre valide com a documentação oficial ou com o que já foi provado funcional em scripts anteriores. A API do QuickAdd opera no nível de "Choices", não diretamente em "Macros". A distinção é sutil, mas fundamental para a estabilidade do sistema.

### **Entrada de Aprendizado #5: Falha na Extração de Texto com Regex Simples**

*   **O Erro:**
    Em queries `dataviewjs`, ao tentar limpar o texto de um log que continha apenas campos estruturados como `(Situação:: ...)(Erro:: ...)(Aprendizado:: ...)` usando `.replace(...)` para remover os campos, a string resultante ficava vazia e o item de lista não era exibido corretamente.

*   **A Causa Raiz:**
    A abordagem de "remover o que não quero" é frágil. A abordagem correta é "extrair o que eu quero". O script estava removendo toda a informação útil, sem deixar nada para exibir.

*   **A Solução/Padrão de Ouro:**
    Em vez de usar `String.prototype.replace()`, usar `String.prototype.match()` com grupos de captura para extrair o conteúdo específico de dentro dos campos estruturados. Em seguida, montar uma nova string formatada com os dados extraídos.

    **Código que FALHA (remove tudo):**
    ```javascript
    let textoLimpo = l.text
        .replace(/\(Situação::.*?\)/g, '')
        .replace(/\(Erro::.*?\)/g, '')
        .replace(/\(Aprendizado::.*?\)/g, '');
    ```
    **Código que FUNCIONA (extrai e formata):**
    ```javascript
    const situacaoMatch = l.text.match(/\(Situação::(.*?)\)/);
    const erroMatch = l.text.match(/\(Erro::(.*?)\)/);
    const aprendizadoMatch = l.text.match(/\(Aprendizado::(.*?)\)/);
    
    const situacao = situacaoMatch ? situacaoMatch[1].trim() : "N/D";
    const erro = erroMatch ? erroMatch[1].trim() : "N/D";
    const aprendizado = aprendizadoMatch ? aprendizadoMatch[1].trim() : "N/D";
    
    return `**Situação:** ${situacao} | **Erro:** ${erro} | **Aprendizado:** ${aprendizado}`;
    ```

    **Aprendizado Crucial:** Para dados estruturados dentro de uma string, a extração via `match()` com grupos de captura é infinitamente mais robusta e flexível do que a remoção via `replace()`.

---

### **Entrada de Aprendizado #6: Query Dataview em Contexto Errado (Listas vs. Tarefas)**

*   **O Erro:**
    Uma query `dataviewjs` destinada a encontrar e exibir desafios (`- [ ] ...`) não retornava resultados, mesmo quando os desafios existiam no arquivo.

*   **A Causa Raiz:**
    A query estava buscando os dados na coleção errada. Itens de lista comuns são indexados em `dv.current().file.lists`, enquanto tarefas (com checkboxes) são indexadas em `dv.current().file.tasks`. O script procurava em `.lists` por itens que só existiam em `.tasks`.

*   **A Solução/Padrão de Ouro:**
    Sempre usar a coleção correta da API do Dataview para o tipo de dado desejado.
    *   Para itens de lista simples (`- ...`): Usar `dv.page("...").file.lists`.
    *   Para tarefas (`- [ ] ...`): Usar `dv.page("...").file.tasks`.

    **Código que FALHA (busca em `.lists`):**
    ```javascript
    const desafios = dv.current().file.lists.where(l => l.text.includes("#desafio"));
    ```
    **Código que FUNCIONA (busca em `.tasks`):**
    ```javascript
    const desafios = dv.current().file.tasks.where(t => t.text.includes("#desafio"));
    dv.taskList(desafios); // Renderiza como tarefas interativas
    ```

    **Aprendizado Crucial:** A API do Dataview é específica sobre o tipo de elemento. Conhecer a diferença entre `.lists` e `.tasks` é fundamental para a precisão das queries.

---

### **Entrada de Aprendizado #7: Complexidade Desnecessária em `optionQuery` (Meta Bind)**

*   **O Erro:**
    Um seletor `INPUT[suggester]` usando uma `optionQuery` com múltiplas condições (ex: `optionQuery("#tag AND \"caminho/pasta\"")`) não retornava nenhum resultado, embora os arquivos existissem e cumprissem ambas as condições.

*   **A Causa Raiz:**
    Embora sintaticamente possível, a combinação de múltiplos filtros dentro da `optionQuery` pode ser instável ou ter um comportamento inesperado dependendo do contexto de execução. Isso adiciona um ponto de falha desnecessário.

*   **A Solução/Padrão de Ouro:**
    Simplificar a query ao máximo, confiando na organização estrutural do vault como a principal "fonte da verdade". Em vez de verificar a pasta E a tag, se a própria estrutura de pastas já garante que todos os arquivos ali são do tipo correto, a verificação da tag se torna redundante e pode ser removida.

    **Código que PODE FALHAR:**
    ```markdown
    `INPUT[suggester(optionQuery("#missao AND \"Missões/Ativas\"")):missao_ativa]`
    ```
    **Código que FUNCIONA (mais robusto):**
    ```markdown
    `INPUT[suggester(optionQuery("Missões/Ativas")):missao_ativa]`
    ```

    **Aprendizado Crucial:** Delegue a lógica de filtragem para a estrutura de pastas sempre que possível. Queries mais simples são menos propensas a erros de sintaxe e de interpretação pelo motor do Dataview. A organização do vault é uma ferramenta de query tão poderosa quanto a própria query.


### **Entrada de Aprendizado #8: Falha Silenciosa em Queries `dataviewjs` por Lógica Incompleta**

*   **O Erro:**
    Uma query `dataviewjs` complexa (como a de "Gatilhos de Gênio") não renderizava nenhuma saída, nem mesmo uma mensagem de erro ou "sem resultados", apesar de haver dados válidos no vault.

*   **A Causa Raiz:**
    A lógica interna do script era excessivamente complexa e continha pontos de falha que não resultavam em um erro de exceção, mas sim em um `return` prematuro ou em um array vazio, fazendo com que o `dv.list()` ou `dv.table()` nunca fosse chamado. No caso específico, a lógica para calcular o limiar de percentil e depois filtrar com base nele era frágil.

*   **A Solução/Padrão de Ouro:**
    Quando uma query complexa falhar, simplifique a abordagem, replicando um padrão mais simples que já se provou funcional. Em vez de calcular um limiar dinâmico, a solução robusta foi criar uma tabela que itera sobre um período fixo (últimos 7 dias) e exibe os fatores correlacionados para cada dia, deixando a análise da "tendência" para o observador humano.

    **Código que FALHA (complexo e frágil):**
    ```javascript
    // Lógica com múltiplos dv.pages() e cálculo de percentil que pode falhar silenciosamente
    const pontuacoes = dv.pages(...).pontos_genio_dia.values.sort(...);
    const limiar = pontuacoes[...];
    const diasDeGenio = dv.pages(...).where(p => p.pontos_genio_dia >= limiar);
    // ... se qualquer passo acima retornar vazio, nada é renderizado.
    ```

    **Código que FUNCIONA (simples e direto):**
    ```javascript
    // Lógica que mapeia um período fixo e exibe dados para cada entrada.
    dv.table(["Dia", "Pontos", "Gatilhos"], 
        dv.pages(...).where(...).sort(...).map(p => {
            // Lógica de verificação simples para cada linha
            const gatilhos = [];
            if (p.habito_x) gatilhos.push("Hábito X");
            return [p.file.link, p.pontos_genio_dia, gatilhos.join(", ")];
        })
    );
    ```

    **Aprendizado Crucial:** "Inteligência" excessiva em uma query de visualização pode ser um ponto de falha. Uma apresentação de dados brutos bem estruturada é, muitas vezes, mais robusta e útil do que uma análise complexa e automatizada que pode falhar silenciosamente.

---

### **Entrada de Aprendizado #9: Inconsistência de Dados entre Criação e Template**

*   **O Erro:**
    Um script QuickAdd (`criarIdeiaProjeto.js`) criava uma nota, mas o conteúdo final não correspondia ao esperado. Placeholders como `%%OBJETIVO%%` não eram preenchidos, e a data de criação não era registrada.

*   **A Causa Raiz:**
    O script e o template estavam dessincronizados. O script não estava sendo instruído a coletar todas as informações necessárias (`objetivo`) nem a injetar dados que ele já possuía (como a data/hora de criação) nos placeholders correspondentes do template.

*   **A Solução/Padrão de Ouro:**
    O script responsável pela criação de uma nota a partir de um template deve ser a **única fonte da verdade** para os dados iniciais. Ele deve:
    1.  Coletar **TODOS** os inputs necessários do usuário via `qa.inputPrompt`.
    2.  Gerar **TODOS** os dados dinâmicos (datas, horas, tags) dentro do próprio script.
    3.  Realizar uma substituição de texto (`.replace()`) para **CADA** placeholder (`%%...%%`) existente no arquivo de template.
    4.  Para dados que precisam ser reativos (como o título do projeto que espelha o nome da pasta), usar queries `dataview` inline (`= this.file.parent.name`) diretamente no template, em vez de depender de substituição por script.

    **Aprendizado Crucial:** Um template e o script que o utiliza formam um "contrato". Cada `%%placeholder%%` no template exige uma linha `.replace()` correspondente no script. A falha em cumprir este contrato resulta em dados incompletos.

---

### **Entrada de Aprendizado #10: Sacrifício da UX por uma Solução Técnica**

*   **O Erro:**
    Ao tentar implementar a seleção múltipla de arquivos, a solução inicial usou `qa.checkboxPrompt`, que funcionava, mas oferecia uma péssima experiência de usuário (lista estática, sem busca, caminhos longos).

*   **A Causa Raiz:**
    Escolher uma solução que era tecnicamente funcional, mas ignorava os requisitos de usabilidade do sistema.

*   **A Solução/Padrão de Ouro:**
    Quando uma função nativa de um plugin não atende aos requisitos de UX, construa um fluxo de trabalho personalizado combinando os pontos fortes de várias funções. A solução final foi criar um **loop interativo** dentro do `inlineJS` do botão:
    1.  Usa `qa.suggester` para sua excelente interface de busca.
    2.  Armazena a seleção em um array temporário.
    3.  Filtra o `suggester` na próxima iteração para remover itens já selecionados.
    4.  Pergunta ao usuário se deseja continuar.
    5.  Ao final, processa o array completo de seleções.

    **Aprendizado Crucial:** A solução SOTA não é apenas a que funciona, mas a que funciona da **melhor maneira para o usuário**. Se uma ferramenta não faz exatamente o que você precisa, use a criatividade para combinar múltiplas ferramentas e construir a experiência desejada. Um bom sistema prioriza a UX.

### **Entrada de Aprendizado #11: Falha na Renderização de Botões Inline Adjacentes**

*   **O Erro:**
    Ao colocar dois `BUTTON[id]` um ao lado do outro na mesma linha, o segundo botão não era renderizado como interativo, aparecendo como texto simples ou com o erro `Button ID not Found`.

*   **A Causa Raiz:**
    Uma limitação ou bug no parser do Meta Bind que o impede de processar múltiplos blocos de definição `meta-bind-button` complexos (com `inlineJS`) que são chamados na mesma linha de renderização. O processamento do primeiro botão parece interferir ou bloquear o reconhecimento do segundo.

*   **A Solução/Padrão de Ouro:**
    Pivotar a UX para contornar a limitação do plugin. Em vez de múltiplos botões lado a lado para ações diferentes, a solução é unificar a interação em um **único botão "Gerenciador"**. Este botão principal aciona um `inlineJS` que, por sua vez, usa um seletor do QuickAdd (`qa.suggester`) para apresentar ao usuário as diferentes ações disponíveis ("Adicionar Fase", "Adicionar Tarefa").

    **Exemplo da Solução no Template:**
    ```markdown
    ```meta-bind-button
    label: "⚙️ Gerenciar Fases & Tarefas"
    style: primary
    actions:
      - type: inlineJS
        code: |
          const acoes = { "➕ Adicionar Nova Fase": "add_fase", ... };
          const escolha = await qa.suggester(Object.keys(acoes), Object.values(acoes));
          if (escolha === "add_fase") {
            // Lógica para adicionar fase...
          } else if (escolha === "add_tarefa") {
            // Lógica para adicionar tarefa...
          }
    ```

    **Aprendizado Crucial:** Quando uma abordagem de layout encontra resistência técnica inexplicável de um plugin, não insista em soluções de CSS frágeis. A abordagem SOTA é **repensar a interação do usuário (UX)** para um padrão mais simples e que utilize uma combinação de APIs comprovadamente estável (neste caso, um único `meta-bind-button` chamando o `quickadd.api`).

---

### **Entrada de Aprendizado #12: Erro de Sintaxe YAML com Strings Multilinha em `inlineJS`**

*   **O Erro:**
    Ao tentar construir uma string multilinha dentro de um `inlineJS` de um botão Meta Bind, ocorria o erro `YAMLParseError: A block sequence may not be used as an implicit map key`.

*   **A Causa Raiz:**
    O parser YAML do Meta Bind interpreta caracteres como `-` ou `{}` no início de novas linhas dentro da string JavaScript como sintaxe YAML, quebrando a estrutura do campo `code:`.

*   **A Solução/Padrão de Ouro:**
    Para blocos de código `inlineJS` multilinha, sempre usar o indicador de bloco escalar literal `|` em YAML. Isso instrui o parser a tratar todo o bloco de texto seguinte como uma única string literal, ignorando todos os caracteres especiais.

    **Código que FALHA:**
    ```yaml
    actions:
      - type: inlineJS
        code: 
          const x = `
          - item de lista
          `;
    ```

    **Código que FUNCIONA:**
    ```yaml
    actions:
      - type: inlineJS
        code: |
          const x = `
          - item de lista
          `;
    ```

    **Aprendizado Crucial:** Conhecer a sintaxe YAML, especialmente como lidar com strings de bloco, é fundamental ao trabalhar com plugins que a utilizam para configuração, como o Meta Bind. `code: |` é o padrão para scripts `inlineJS` complexos.

---

### **Entrada de Aprendizado #13: Contagem Incorreta de Elementos com `match()` em Regex**

*   **O Erro:**
    Um script para numerar "Fases" estava retornando um número incorreto (ex: começando em 6 em vez de 1), porque contava ocorrências da palavra "Fase" dentro de blocos de código.

*   **A Causa Raiz:**
    A função `fileContent.match(/### Fase/g)` é "burra" e não tem noção da estrutura do Markdown. Ela conta todas as ocorrências da string no arquivo, resultando em uma contagem inflada.

*   **A Solução/Padrão de Ouro:**
    Para contar elementos estruturais em um arquivo Markdown, a abordagem mais robusta é ler o arquivo, dividi-lo em linhas (`.split('\n')`), e iterar sobre o array de linhas, aplicando a lógica de contagem apenas às linhas que correspondem exatamente ao padrão estrutural desejado.

    **Código que FALHA (Regex ingênuo):**
    ```javascript
    const numeroFase = (fileContent.match(/### Fase/g) || []).length + 1;
    ```
    **Código que FUNCIONA (Iteração de Linha):**
    ```javascript
    const lines = fileContent.split('\n');
    let contadorFases = 0;
    for (const line of lines) {
        if (line.trim().startsWith("### Fase")) {
            contadorFases++;
        }
    }
    const numeroFase = contadorFases + 1;
    ```
    **Aprendizado Crucial:** Para tarefas que dependem da estrutura do documento (como contar cabeçalhos), a análise linha por linha é mais precisa e menos propensa a falsos positivos do que uma busca global por Regex.

### **Entrada de Aprendizado #14: Falha na Lógica de Contagem com `string.match()`**

*   **O Erro:**
    Um script que deveria numerar seções de "Fase" sequencialmente (Fase 1, Fase 2, ...) estava começando com um número incorreto (ex: Fase 6).

*   **A Causa Raiz:**
    O método de contagem `(fileContent.match(/### Fase/g) || []).length` era ingênuo e não contextual. Ele contava todas as ocorrências da string "### Fase" em todo o arquivo, incluindo dentro de blocos de código `dataviewjs` de acompanhamento, o que inflava a contagem.

*   **A Solução/Padrão de Ouro:**
    Para contar elementos estruturais de forma precisa, a análise linha por linha é superior. A solução foi ler o conteúdo do arquivo, dividi-lo em um array de linhas e iterar, incrementando um contador apenas quando uma linha, após a remoção de espaços em branco, **começa** com a string estrutural desejada.

    **Código que FALHA (Regex ingênuo):**
    ```javascript
    const numFases = (fileContent.match(/### Fase/g) || []).length + 1;
    ```
    **Código que FUNCIONA (Iteração de Linha Precisa):**
    ```javascript
    const lines = fileContent.split('\n');
    let contadorFases = 0;
    for (const line of lines) {
        if (line.trim().startsWith("### Fase")) {
            contadorFases++;
        }
    }
    const numeroFase = contadorFases + 1;
    ```
    **Aprendizado Crucial:** A robustez na análise de conteúdo de arquivos muitas vezes vem da simplicidade da iteração linha por linha, que é imune a contextos de blocos de código, em vez de expressões regulares globais que podem capturar falsos positivos.

---

### **Entrada de Aprendizado #15: Falha na Geração de Tags com Caracteres Especiais**

*   **O Erro:**
    Ao criar uma tarefa, se o nome da Fase continha uma vírgula (ex: "Planejamento, engenharia reversa"), a tag hierárquica gerada quebrava (`#missao/.../planejamento,_engenharia_reversa/...`).

*   **A Causa Raiz:**
    A função de "sanitização" do nome para criar a tag só substituía espaços, mas não outros caracteres problemáticos como vírgulas.

*   **A Solução/Padrão de Ouro:**
    Criar uma função de sanitização dedicada e reutilizável que lida com todos os casos previstos. A função deve ser aplicada a todas as partes variáveis da tag antes de sua concatenação.

    **Código que FALHA (sanitização incompleta):**
    ```javascript
    const nomeFaseSanitizado = ultimaFaseNome.replace(/ /g, '_').toLowerCase();
    ```
    **Código que FUNCIONA (função de sanitização robusta):**
    ```javascript
    const sanitizar = (str) => str.replace(/ /g, '_').replace(/,/g, '').toLowerCase();
    const nomeFaseSanitizado = sanitizar(ultimaFaseNome);
    const nomeTarefaSanitizado = sanitizar(nomeTarefa);
    ```
    **Aprendizado Crucial:** Ao gerar dados programaticamente para serem usados por outros sistemas (como o sistema de tags do Obsidian), a sanitização de input deve ser explícita e abrangente, prevendo os caracteres que podem quebrar a estrutura do sistema de destino.

---

### **Entrada de Aprendizado #16: O Padrão Definitivo para Botões Interativos (O Fim do Loop)**

*   **O Erro:**
    Uma longa série de falhas ao tentar alinhar múltiplos botões `meta-bind-button` lado a lado, incluindo erros de CSS, erros de parse YAML e `Button ID not Found`.

*   **A Causa Raiz:**
    Uma limitação fundamental (ou bug) no plugin Meta Bind que impede a renderização correta de múltiplos blocos de código de botão (` ```meta-bind-button ``` `) quando seus gatilhos inline (`BUTTON[...]`) são colocados na mesma linha. As tentativas de contornar isso com CSS ou HTML simples falharam porque não abordaram o problema central na renderização do plugin.

*   **A Solução/Padrão de Ouro:**
    **Pivotar a UX para um padrão comprovadamente robusto.** Em vez de múltiplos botões visuais, a solução é usar um **único botão "Gerenciador"** que aciona um `inlineJS`. Este script, por sua vez, usa a API do QuickAdd (`qa.suggester`) para apresentar ao usuário uma lista de ações possíveis.

    **Estrutura da Solução:**
    1.  **Um único `meta-bind-button`:**
        ```markdown
        ```meta-bind-button
        label: "⚙️ Gerenciar..."
        style: primary
        actions:
          - type: inlineJS
            code: |
              // Script que usa qa.suggester para mostrar opções...
        ```
    2.  **Lógica no `inlineJS`:** O script apresenta as opções ("Adicionar Fase", "Adicionar Tarefa") e executa a lógica correspondente com base na seleção do usuário.

    **Aprendizado Crucial:** A lição mais importante da nossa colaboração. Quando uma abordagem de UI/Layout encontra resistência técnica profunda e inexplicável de um plugin, **não insista em consertar o layout**. A solução SOTA é **redesenhar a interação** para um padrão mais simples que utilize uma combinação de APIs que já provamos ser estável. A robustez funcional sempre tem precedência sobre uma preferência de layout específica e frágil.

### **Entrada de Aprendizado #17: O Padrão YAML para Strings Multilinha e Caracteres Especiais**

*   **O Erro:**
    `YAMLParseError: Source contains multiple documents` ou `Not a YAML token` em botões do Meta Bind.
*   **A Causa Raiz:**
    O parser YAML do Meta Bind é extremamente sensível. Ele interpreta caracteres como `---`, `##`, `>` ou mesmo comentários `//` na mesma linha de `code: |` como parte da sintaxe YAML, quebrando a análise do bloco de código `inlineJS`.
*   **A Solução/Padrão de Ouro (Padrão #18 Reforçado):**
    A única abordagem 100% robusta para inserir scripts `inlineJS` multilinha ou complexos no YAML do Meta Bind é:
    1.  Usar o indicador de bloco escalar literal `|` (Ex: `code: |`). A linha deve conter **apenas** isso.
    2.  Para gerar strings de Markdown complexas dentro do JavaScript, abandonar os template literals (` `` `) e usar a **concatenação de strings simples** (`'string 1\n' + 'string 2\n'`). Isso remove toda a ambiguidade para o parser.
    3.  Para evitar conflitos com o parser de Markdown, usar `***` como separador horizontal em vez de `---` dentro das strings geradas.

---

### **Entrada de Aprendizado #18: O Padrão Dataview para Valores Padrão**

*   **O Erro:**
    `Dataview: PARSING FAILED` ao tentar usar operadores JavaScript como `||` em queries DQL inline (`= ...`).
*   **A Causa Raiz:**
    Mistura de paradigmas de linguagem. O motor DQL não entende operadores JavaScript para lógica de valores.
*   **A Solução/Padrão de Ouro:**
    Usar a função nativa do DQL `default(campo, valor_padrao)`. É a forma canônica e robusta de fornecer um valor padrão quando um campo pode ser nulo.
    *   **Exemplo:** `= default(this.data_inicio, "Não iniciado")`

---

### **Entrada de Aprendizado #19: Acesso Defensivo a APIs em Contextos Reativos**

*   **O Erro:**
    Falha silenciosa ou `TypeError: Cannot read properties of undefined` em `meta-bind-js-view` ou `dataviewjs`.
*   **A Causa Raiz:**
    Problemas de timing. Scripts reativos podem executar antes que as APIs de outros plugins (como `QuickAdd`) ou o cache do Dataview (`dv.current().file`) estejam totalmente prontos e populados.
*   **A Solução/Padrão de Ouro (Padrão #32 Reforçado):**
    1.  **Sempre verifique a existência do objeto do plugin** antes de chamar sua API (ex: `const qaPlugin = this.app.plugins.plugins.quickadd; if (!qaPlugin) return; const qa = qaPlugin.api;`).
    2.  Para obter o arquivo atual em scripts reativos, **priorize `this.app.workspace.getActiveFile()`** sobre `dv.current().file`, pois o primeiro é síncrono e reflete o estado da UI, enquanto o segundo depende do cache assíncrono do Dataview.
    3.  Sempre envolva o uso de objetos retornados por APIs em verificações `if (objeto) { ... }`.

---

### **Entrada de Aprendizado #20: O Padrão Correto para Extração com Regex**

*   **O Erro:**
    Cálculos resultando em `NaN` ao tentar usar `parseInt()` em um resultado de `String.prototype.match()`.
*   **A Causa Raiz:**
    `match()` retorna um **array**. O primeiro elemento (`match[0]`) é a correspondência completa, e os seguintes (`match[1]`, `match[2]`, ...) são os grupos de captura. Tentar fazer `parseInt` no array inteiro falha.
*   **A Solução/Padrão de Ouro (Padrão #30 Reforçado):**
    Para extrair um valor numérico de uma regex com um grupo de captura (ex: `/\((\d+)\)/`), o acesso correto é sempre ao índice do grupo: `parseInt(match[1])`.

---

### **Entrada de Aprendizado #21: O Padrão Correto para GROUP BY no DQL**

*   **O Erro:**
    `Dataview: Cannot call type 'null' as a function` ou `PARSING FAILED` ao usar lógica condicional no `GROUP BY`.
*   **A Causa Raiz:**
    O `GROUP BY` no DQL não suporta o operador ternário (`condição ? sim : não`). Além disso, tentar executar uma função (como `.toFormat()`) em um campo que pode ser nulo (`file.day`) causa um `TypeError` que interrompe a operação de agrupamento.
*   **A Solução/Padrão de Ouro:**
    1.  Para lógica condicional, usar a função nativa `choice(condição, valor_se_sim, valor_se_nao)`.
    2.  Para máxima robustez e para evitar o erro de `null`, a abordagem mais simples e infalível é agrupar pela propriedade mais fundamental que sempre existe: `GROUP BY file.link`. O nome do arquivo (que no nosso caso é a data) é usado como o display text por padrão.

### **Entrada de Aprendizado #22: O Problema da Lógica Recorrecente em Templates**

*   **O Erro:**
    Ao usar um botão para inserir um novo bloco de "Fase" em uma nota, o script também inseria o marcador `<!-- FASES_DA_MISSAO_AQUI -->`, resultando em marcadores duplicados.
*   **A Causa Raiz:**
    A lógica estava falha. O `blocoFinal` que era inserido continha tanto o conteúdo da nova fase quanto o marcador para a *próxima* inserção.
*   **A Solução/Padrão de Ouro (Padrão #33 Reforçado):**
    O Padrão de Marcador de Injeção precisa de uma lógica clara de substituição:
    1.  O template inicial contém **um** marcador: `<!-- PLACEHOLDER -->`.
    2.  O script gera o **conteúdo novo** a ser inserido.
    3.  A string completa para a substituição deve ser: `[Conteúdo Novo] + \n + [Marcador]`.
    4.  A operação no arquivo deve ser: `fileContent.replace('<!-- PLACEHOLDER -->', stringDeSubstituicao)`.
    5.  Isso garante que o marcador antigo seja consumido e um novo seja posicionado corretamente para a próxima ação, criando um ciclo de inserção limpo e sem duplicação.

---

### **Entrada de Aprendizado #23: A Fragilidade da Extração por Regex Complexa**

*   **O Erro:**
    Queries `dataviewjs` para extrair dados de logs estruturados (como "Aprendizado de Erro") retornavam `N/D` ou falhavam em capturar o texto completo se o conteúdo contivesse caracteres especiais como parênteses.
*   **A Causa Raiz:**
    Tentativas de usar regex complexas com `lookahead` (`(?=...)`) ou múltiplas substituições em cadeia se mostraram frágeis e inconsistentes com o motor de regex do Dataview.
*   **A Solução/Padrão de Ouro (Padrão #37 Reforçado):**
    A abordagem mais robusta e à prova de falhas para parsing de campos `(Chave:: Valor)` é a mais simples:
    1.  Usar `match()` individuais para cada campo que se deseja extrair: `const situacaoMatch = l.text.match(/\(Situação::(.*?)\)/);`.
    2.  O grupo de captura `(.*?)` é suficiente na maioria dos casos, desde que cada campo esteja em seus próprios delimitadores.
    3.  Esta abordagem é transparente, fácil de depurar e não depende de funcionalidades de regex avançadas que podem não ser suportadas.

---

### **Entrada de Aprendizado #24: A Regra de Ouro da Sintaxe YAML para Links**

*   **O Erro:**
    Um `dataviewjs` em um arquivo de Métricas falhava ao tentar ler a propriedade `.path` de um link para o arquivo HUB, mesmo o link estando presente no frontmatter.
*   **A Causa Raiz:**
    A sintaxe no frontmatter estava `missao_hub: "[[caminho/arquivo.md]]"`. As aspas (`" "`) fazem o parser YAML tratar o valor como uma **string de texto**, não como um **objeto Link**. Uma string não tem a propriedade `.path`.
*   **A Solução/Padrão de Ouro:**
    A sintaxe correta para um link no frontmatter YAML, para que o Dataview o reconheça como um objeto `Link`, é **sem aspas**:
    ```yaml
    missao_hub: [[caminho/para/o/arquivo.md]]
    ```
    O script de criação deve garantir que ele gere o YAML nesta formatação exata.

---

### **Entrada de Aprendizado #25: Movimentação de Pastas e Limitações do Sistema de Arquivos**

*   **O Erro:**
    Ao tentar mover a pasta de uma missão (ex: da Incubadora para Ativos), o script falhava com o erro `EPERM: operation not permitted, rename...`.
*   **A Causa Raiz:**
    Uma limitação do sistema operacional (especialmente Windows). Não é possível renomear ou mover uma pasta se um arquivo dentro dela (ou de suas subpastas) estiver aberto na aplicação (neste caso, o próprio `00 - HUB.md` onde o botão foi clicado).
*   **A Solução/Padrão de Ouro (Padrão #35 Reforçado):**
    Nunca tente mover uma pasta que possa conter arquivos abertos. A solução robusta é:
    1.  Criar a estrutura de pastas de destino completa.
    2.  Implementar uma **função recursiva** que itera sobre todos os arquivos e subpastas da origem.
    3.  Mover cada **arquivo individualmente** para o seu local correspondente no destino.
    4.  Após todos os arquivos terem sido movidos, a pasta de origem original estará vazia e poderá ser deletada com segurança (`app.vault.delete(pastaOrigem, true)`).



### **Entrada de Aprendizado #26: O Padrão de Sanitização Universal**

*   **O Erro:**
    Múltiplos scripts (criação de tarefas, criação de pastas de métricas, busca de logs) geravam versões ligeiramente diferentes de nomes sanitizados para tags e pastas a partir do mesmo título de mídia (ex: `o-livro` vs. `o_livro` vs. `o_livro_!!!`). Isso causava falhas de busca, onde um script não conseguia encontrar o que o outro havia criado.

*   **A Causa Raiz:**
    Uso de múltiplas funções de sanitização inconsistentes espalhadas pelo sistema. Cada uma tratava espaços, hífens, acentos e caracteres especiais de forma diferente.

*   **A Solução/Padrão de Ouro:**
    Definir e usar uma **única e universal função de sanitização** em **todos** os pontos do sistema que geram ou buscam nomes de arquivos, pastas ou tags a partir de um input do usuário.

    **Código do Padrão (JavaScript):**
    ```javascript
    const sanitizarParaTag = (str) => {
        if (!str) return "";
        return str
            .normalize("NFD").replace(/[\u0300-\u036f]/g, "") // 1. Remove acentos
            .toLowerCase()                                  // 2. Converte para minúsculas
            .trim()                                         // 3. Remove espaços no início/fim
            .replace(/[-\s]+/g, '_')                        // 4. Substitui hífens E espaços por um único underscore
            .replace(/[^\w_]+/g, '');                       // 5. Remove todos os caracteres restantes que não são letras, números ou underscore
    };
    ```
    **Aprendizado Crucial:** A consistência na transformação de dados é fundamental em um sistema distribuído. Deve haver uma "fonte única da verdade" não apenas para os dados, mas também para as **funções que formatam esses dados** para interação entre componentes.

---

### **Entrada de Aprendizado #27: A Arquitetura Híbrida de Criação de Métricas**

*   **O Erro:**
    Um gráfico do Tracker exibia o erro `Folder ... doesn't exist` para um novo projeto de leitura que ainda não tinha logs de Pomodoro.

*   **A Causa Raiz:**
    O script agregador `dataviewjs` só criava a pasta de métricas diárias (`Logs_Metricas/.../[Nome do Livro]`) de forma **reativa**, ou seja, apenas quando encontrava um log de Pomodoro para processar.

*   **A Solução/Padrão de Ouro:**
    Adotar uma arquitetura híbrida "proativa-reativa":
    1.  **Criação Proativa (no script de criação, ex: `criarLivro.js`):** A **pasta** de métricas (`.../[Nome do Livro]/`) é criada no momento da criação do projeto. Isso garante que o Tracker sempre encontre um caminho válido.
    2.  **Criação Reativa (no script agregador, ex: `dataviewjs` nas Métricas):** Os **arquivos** de log diário (`.../2025-09-11.md`) são criados dentro da pasta já existente pelo script agregador, na primeira vez que ele processa um Pomodoro para aquele dia.

    **Aprendizado Crucial:** Garanta a existência da infraestrutura (pastas) de forma proativa para evitar erros fatais em plugins de visualização. Deixe a criação dos dados em si (arquivos) para o momento em que os dados realmente existem, de forma reativa.

---

### **Entrada de Aprendizado #28: Acesso a Metadados Inline em Itens de Lista Simples**

*   **O Erro:**
    Uma query `dataviewjs` falhava ao tentar ler um metadado de um log de Pomodoro (que é um item de lista, `- ...`) usando a sintaxe `p['begin']`, resultando em `undefined`.

*   **A Causa Raiz:**
    A suposição de que o Dataview parseia automaticamente metadados no formato `(chave:: valor)` para **qualquer item de lista** estava incorreta. Essa funcionalidade é mais robusta e garantida para tarefas do plugin Tasks (`- [ ] ...`). Para itens de lista simples, a informação permanece como parte da string `p.text`.

*   **A Solução/Padrão de Ouro:**
    Quando o acesso direto (ex: `p['chave']`) falhar, retorne ao nosso padrão mais fundamental de robustez: **extração explícita via Expressão Regular** a partir do texto bruto do item (`p.text`).

    **Código do Padrão (JavaScript):**
    ```javascript
    // Em vez de: const beginDT = p['begin'];
    // Use:
    const beginMatch = p.text.match(/\(begin::\s*(\d{4}-\d{2}-\d{2}\s\d{2}:\d{2}:\d{2})\)/);
    const beginMoment = beginMatch ? moment(beginMatch[1], "YYYY-MM-DD HH:mm:ss") : null;
    ```
    **Aprendizado Crucial:** Não confie no parsing implícito do Dataview para estruturas de dados complexas dentro de itens de lista simples. A extração de texto bruto com Regex é universalmente compatível e mais resiliente a mudanças no motor do Dataview.

---

### **Entrada de Aprendizado #29: O Abandono da Reatividade para Ações de Escrita**

*   **O Erro:**
    Um script `dataviewjs` invisível, projetado para processar logs e criar/atualizar arquivos de métricas, falhava silenciosamente em executar a operação de escrita de arquivos.

*   **A Causa Raiz:**
    Conflito de ciclo de vida. O ambiente de renderização do `dataviewjs` é otimizado para **leitura** e não é um ambiente estável para operações de **escrita** de arquivos (`app.fileManager.processFrontMatter`). A tentativa de escrever enquanto o Dataview pode estar lendo cria condições de corrida e falhas silenciosas.

*   **A Solução/Padrão de Ouro:**
    Centralizar **toda a lógica de processamento de dados e escrita de arquivos** em um gatilho manual e explícito: um **`meta-bind-button` com `type: inlineJS`**.

    **Aprendizado Crucial:** A reatividade é para visualização. A modificação de dados deve ser o resultado de uma intenção explícita do usuário (um clique). A arquitetura mais robusta separa completamente a **visualização reativa** (gráficos do Tracker, tabelas Dataview) da **modificação de dados sob demanda** (acionada por um botão).


### **Entrada de Aprendizado #30: Precisão de Chaves em Configurações YAML do Tracker**

*   **O Erro:**
    Gráficos do Tracker não renderizavam, exibindo erros como `'title' is not an available key` ou `'colorByValue' is not an available key`.

*   **A Causa Raiz:**
    Uso de chaves de configuração que, embora semanticamente corretas, não correspondiam **exatamente** à sintaxe documentada para aquele tipo de gráfico específico. Por exemplo, usar `title` dentro de um bloco `month:` (onde não é permitido) ou usar `colorByValue` em vez do correto `circleColorByValue`.

*   **A Solução/Padrão de Ouro:**
    Não fazer suposições sobre os nomes dos parâmetros entre diferentes tipos de output do mesmo plugin. A sintaxe YAML do Tracker é extremamente literal e não perdoa erros de digitação ou nomes de chaves incorretos. A consulta à documentação para cada tipo de gráfico (`line`, `bar`, `month`, etc.) é mandatória.

    **Exemplo de Erro:**
    ```yaml
    month:
        colorByValue: true # Incorreto
    ```

    **Código Correto:**
    ```yaml
    month:
        circleColorByValue: true # Correto
    ```
    **Aprendizado Crucial:** A robustez do código Tracker depende da precisão absoluta. Um único caractere ou palavra errada em uma chave de configuração invalida todo o bloco. Verificação dupla contra a documentação é o padrão.


### **Entrada de Aprendizado #31: A Condição de Corrida de Estado e a Solução Reativa**

*   **O Erro:**
    Um script (`Timer.ts`) que dependia de um estado contextual (`sotaContext`) falhava em obter a versão mais recente desse estado ao ser acionado. A função `start()` era chamada com um contexto obsoleto (`tipo: 'nenhum'`), fazendo com que a lógica subsequente em `SotaSync.ts` abortasse silenciosamente, resultando em timestamps não sendo salvos no frontmatter e logs de sessão com dados incorretos (`pagina::N/A`).

*   **A Causa Raiz:**
    Uma condição de corrida (race condition) entre a atualização do estado contextual e a sua utilização. O `SotaContext` atualizava um `store` Svelte, mas o objeto de estado interno do `Timer` não era reativamente ligado a esse `store`. Ele mantinha uma cópia obsoleta do estado que só era atualizada em sua inicialização, não em tempo real.

*   **A Solução/Padrão de Ouro (Arquitetura Reativa):**
    A solução robusta é garantir que os componentes do sistema que dependem de um estado compartilhado **se inscrevam (subscribe)** a esse estado, em vez de lerem seu valor uma única vez.
    1.  **Centralizar o Estado:** Manter o estado compartilhado em um `store` Svelte (`sotaContextStore`).
    2.  **Inscrever os Dependentes:** No construtor da classe dependente (`Timer.ts`), criar um `subscriber` para o `store`.
    3.  **Atualização Imediata:** O callback do `subscriber` deve chamar um método interno (`setSotaContext`) que atualiza a propriedade de estado interna da classe (`this.storeInternal.update(...)`) sempre que o `store` emitir um novo valor.

    **Exemplo de Código (no construtor do `Timer.ts`):**
    ```typescript
    constructor(plugin: PomodoroTimerPlugin) {
        // ... inicialização ...

        // **CORREÇÃO CRÍTICA DO FLUXO DE ESTADO**
        // O Timer agora "escuta" ativamente as mudanças de contexto.
        const sotaContextUnsubscriber = sotaContextStore.subscribe((context) => {
            sotaLog("Timer", "sotaContextStore.subscribe: Contexto recebido.", context);
            this.setSota-context(context);
        });
        this.unsubscribers.push(sotaContextUnsubscriber);
    }
    ```

    **Aprendizado Crucial:** Para sistemas com estado dinâmico (como o contexto da nota ativa), uma arquitetura reativa baseada em `stores` e `subscribers` é fundamental para evitar condições de corrida. A lógica não deve "pedir" o estado, mas sim "reagir" às suas mudanças. Isso garante que todos os componentes operem sempre com a versão mais recente e consistente dos dados.   


    ### **Entrada de Aprendizado #32: O Padrão de Recalculo Atômico "Log-Centric"**

*   **O Erro:**
    Um script de processamento de dados (`processarLogsLeitura.js`) falhava de duas maneiras críticas:
    1.  Causava um erro intermitente e fatal (`TypeError: e.cache is not a function`) ao tentar usar queries Dataview para encontrar arquivos relevantes enquanto também realizava operações de escrita em loop.
    2.  Quando executava, agregava incorretamente dados de múltiplos dias em um único arquivo de métrica diária, corrompendo a integridade dos dados.

*   **A Causa Raiz:**
    A arquitetura era "file-centric" e dependia de forma instável do cache do Dataview. A causa raiz foi multifacetada:
    1.  **Condição de Corrida:** A execução de `dv.pages().where(...)` para encontrar arquivos relevantes enquanto o script modificava outros arquivos (`app.fileManager.processFrontMatter`) criava uma condição de corrida que corrompia o estado interno do cache do Dataview.
    2.  **Fonte da Verdade Incorreta:** O script derivava o "dia" do nome do arquivo da nota diária, em vez de usar a data `(log_date::...)` contida dentro de cada linha de log. Isso causava a agregação de todos os logs no primeiro dia processado.
    3.  **Lógica Incremental Frágil:** A tentativa de somar novos dados aos existentes (`+=`) não era idempotente, criando risco de duplicação de dados se o botão fosse clicado várias vezes.

*   **A Solução/Padrão de Ouro:**
    Adotar uma arquitetura de **Recalculo Total Atômico "Log-Centric"**, que é imune aos problemas acima.
    1.  **Descoberta de Arquivos com API Pura:** Para encontrar os arquivos relevantes, abandonar completamente as queries Dataview de conteúdo. Usar a API nativa `app.vault.getMarkdownFiles()` e filtrar por caminho com `string.startsWith()`. Isso desacopla a descoberta de arquivos do cache do Dataview.
    2.  **Agregação "Log-Centric":** Primeiro, varrer todos os arquivos diários relevantes e agregar **todas as linhas de log** para a mídia em questão em um único array. Em seguida, usar `reduce` para agrupar esses logs em um objeto onde as chaves são as datas extraídas do metadado `(log_date::...)` de cada log. A data do log se torna a fonte da verdade.
    3.  **Processamento Atômico por Dia:** Iterar sobre os dias **agrupados**. Para cada dia, calcular todas as métricas do zero, olhando apenas para o array de logs daquele dia. Isso garante isolamento total dos dados.
    4.  **Escrita Idempotente (Sobrescrita):** Ao salvar no arquivo de métrica diário, **sobrescrever** os valores (`fm.campo = valor_total_do_dia`) em vez de incrementá-los. Isso garante que múltiplas execuções do script sempre resultarão no mesmo estado correto, tornando o sistema autocorretivo.

    **Exemplo de Código (Agregação Log-Centric):**
    ```javascript
    // Etapa 1 e 2: Coletar todos os logs e agrupá-los pela data interna.
    const todosOsLogsDoLivro = [];
    // ... loop com app.vault.read() para popular o array ...

    const logsPorDia = todosOsLogsDoLivro.reduce((acc, log) => {
        const dateMatch = log.match(/\(log_date::\s*(\d{4}-\d{2}-\d{2})\)/);
        if (dateMatch) {
            const dia = dateMatch[1];
            if (!acc[dia]) acc[dia] = [];
            acc[dia].push(log);
        }
        return acc;
    }, {});
    
    // Etapa 3: Iterar sobre os dias agrupados.
    for (const dia in logsPorDia) {
        // ... Lógica de cálculo isolada ...
        // Etapa 4: Sobrescrever dados no frontmatter.
    }
    ```

---

### Entrada de Aprendizado #33: O Princípio da Replicação de Padrões Validados

*   **O Erro:**
    Ao tentar modificar scripts existentes que geravam blocos de código para outros plugins (como `chartsview`), a reescrita da lógica de geração de strings introduziu repetidamente erros de sintaxe (`YAMLParseError`), mesmo quando a lógica de negócio (como a busca de dados) estava correta. Isso causou múltiplos ciclos de depuração para resolver um problema que já havia sido solucionado em outros scripts.

*   **A Causa Raiz:**
    O erro foi tentar "reinventar a roda" ou "otimizar" a geração de código (neste caso, strings YAML) em vez de aderir estritamente a um padrão que já havia sido provado funcional e robusto. A complexidade da sintaxe e da indentação de plugins como Charts View e Meta Bind é extremamente alta, e a geração dinâmica de strings é inerentemente frágil e propensa a erros de whitespace.

*   **A Solução/Padrão de Ouro (Diretiva SOTA):**
    **NUNCA REESCREVA UM PADRÃO DE GERAÇÃO DE CÓDIGO QUE JÁ FUNCIONA. REPLIQUE E ADAPTE.**
    1.  **Identifique o Padrão Validado:** Antes de modificar ou criar um script que gera um bloco de código, a primeira etapa é localizar um script existente no sistema que gera um bloco similar e que **funciona sem erros**.
    2.  **Copie a Estrutura Monolítica:** Copie a estrutura de geração de código (geralmente uma string template monolítica) do script validado. Esta estrutura já passou pelo teste de robustez.
    3.  **Modifique Cirurgicamente:** Realize apenas as modificações mínimas e necessárias na lógica de negócio (ex: alterar a fonte de dados, ajustar uma variável como `folderPath`). A estrutura sintática do bloco de código gerado deve permanecer o mais intacta possível.

    **Exemplo Prático (Correção do `YAMLParseError`):**
    *   **Abordagem Falha:** Tentar construir a string YAML do `chartsview` dinamicamente, linha por linha, usando `.join('\n')` e concatenação.
    *   **Abordagem SOTA:** Copiar um bloco `chartsview` inteiro que já funciona para uma template string (` `` `) dentro do script. A única parte dinâmica é um placeholder (ex: `%%FOLDER_PATH%%`). O script então apenas seleciona o template correto e usa `.replace()` para injetar a variável.

    **Aprendizado Crucial:** A velocidade e a robustez do desenvolvimento no sistema SOTA vêm da replicação de padrões validados, não da inovação constante em áreas sensíveis à sintaxe. A prioridade máxima é identificar o que já funciona e usá-lo como base para qualquer nova funcionalidade ou correção. Qualquer desvio de um padrão validado deve ser justificado e testado com extremo rigor.

    ### **Entrada de Aprendizado #34: Erro de Compilação com APIs de Plugins Externos**

*   **O Erro:**
    Ao tentar usar a API de um plugin externo (como o QuickAdd) a partir de um script TypeScript, o compilador gerava o erro `error TS2339: Property 'suggester' does not exist on type '{}'`. Isso ocorria mesmo com verificações de tempo de execução (`if (plugin.api)`) presentes.

*   **A Causa Raiz:**
    O problema é de **inferência de tipo em tempo de compilação**, não de disponibilidade em tempo de execução. O compilador do TypeScript não tem acesso às definições de tipo de uma API que é carregada dinamicamente por outro plugin. Ele vê a propriedade `.api` como um objeto genérico e vazio (`{}`), e, portanto, proíbe o acesso a qualquer propriedade que não esteja formalmente definida nesse tipo.

*   **A Solução/Padrão de Ouro:**
    Para resolver isso, devemos "ensinar" ao TypeScript a estrutura da API externa. A abordagem robusta é criar uma **interface TypeScript** mínima com os métodos que pretendemos usar e, em seguida, aplicar uma **asserção de tipo (`as`)** para informar ao compilador que o objeto da API corresponde a essa interface.

    **Exemplo de Código (no arquivo que chama a API):**
    ```typescript
    // 1. Definir uma interface com a "forma" da API externa.
    interface IQuickAddApi {
        suggester(displayItems: any[], actualItems: any[]): Promise<any>;
        inputPrompt(header: string): Promise<string>;
    }

    // ... dentro de uma função ...

    // 2. Obter o plugin e sua API de forma defensiva.
    const qaPlugin = this.app.plugins.plugins.quickadd;
    if (!qaPlugin?.api) {
        new Notice("ERRO: API do QuickAdd não está disponível.");
        return;
    }

    // 3. Usar a asserção de tipo 'as' para informar o compilador.
    const qa = qaPlugin.api as IQuickAddApi;

    // 4. Agora, o acesso aos métodos é seguro e tipado.
    const escolha = await qa.suggester(...);
    const input = await qa.inputPrompt(...);
    ```

*   **Aprendizado Crucial:** Verificações de tempo de execução (`if (x)`) resolvem problemas de `null` ou `undefined` quando o código está rodando. Interfaces e asserções de tipo (`interface X`, `... as X`) resolvem problemas de ambiguidade para o compilador *antes* que o código rode. Para interagir com APIs dinâmicas em TypeScript, a segunda abordagem é mandatória para um build limpo.


### Erro #34: Dupla Submissão de Modal com a Tecla 'Enter'

**O Erro:**
Em um modal personalizado (como o `FocusRatingModal`), confirmar a entrada de dados pressionando a tecla `Enter` fazia com que a lógica de submissão fosse executada duas vezes, resultando em logs duplicados e o modal reaparecendo momentaneamente. A confirmação via clique do mouse funcionava corretamente.

**A Causa Raiz:**
Propagação de evento (`Event Bubbling`). O `EventListener` para `keydown` no campo de input capturava o `Enter`, executava a lógica (`this.close()`) mas não interrompia o evento. O evento `Enter` continuava a "borbulhar" pelo DOM e era capturado por um listener padrão do modal ou do botão, que o interpretava como um "clique" de confirmação, disparando a mesma lógica pela segunda vez.

**A Solução/Padrão de Ouro:**
Ao manipular eventos de UI manualmente, especialmente eventos de teclado como `Enter`, é mandatório parar sua propagação para evitar efeitos colaterais indesejados. Isso é feito usando os métodos `preventDefault()` e `stopPropagation()`.

**Implementação no `src/Timer.ts` (dentro da classe `FocusRatingModal`):**

```typescript
// ANTES (Com o bug)
inputEl.addEventListener("keydown", (evt) => {
    if (evt.key === "Enter") {
        this.result = inputEl.value;
        this.close();
    }
});

// DEPOIS (Padrão de Ouro)
inputEl.addEventListener("keydown", (evt) => {
    if (evt.key === "Enter") {
        evt.preventDefault();  // Impede a ação padrão do navegador (ex: submissão de formulário)
        evt.stopPropagation(); // Impede que o evento seja capturado por outros listeners
        this.result = inputEl.value;
        this.close();
    }
});
```

**Diretriz Arquitetural:** Sempre que um `EventListener` personalizado for adicionado para acionar uma ação que também pode ser acionada por um clique, especialmente em formulários ou modais, utilize `preventDefault()` e `stopPropagation()` para garantir que a ação seja executada **uma e apenas uma vez**, prevenindo comportamentos de dupla execução.


### **Entrada de Aprendizado #35: A Falha Cíclica de Interação entre Plugins e o Padrão "Vanilla Obsidian API"**

*   **O Erro:**
    Uma série de erros persistentes ao tentar criar uma nota diária programaticamente a partir de um script (QuickAdd/Meta Bind). As falhas se manifestaram como "API do Templater não está pronta", "Nenhuma configuração de Journal encontrada" e erros de tipagem, mesmo quando a lógica parecia correta.

*   **A Causa Raiz (Diagnóstico Final):**
    A causa raiz fundamental foi a **tentativa de interagir com as APIs internas ou com os arquivos de `settings` de outros plugins (Templater, Journals) em um contexto de execução onde sua disponibilidade e estado não são garantidos**. Isso é uma condição de corrida (race condition) clássica no ecossistema de plugins do Obsidian. O acesso direto a `plugin.settings` ou a APIs não explicitamente projetadas para uso externo (`tp.file.create_new`) se provou 100% instável.

*   **A Solução/Padrão de Ouro:**
    Abandonar completamente as dependências de APIs internas e configurações dinâmicas para funções críticas do sistema. A solução mais robusta é o padrão **"Vanilla Obsidian API"**:
    1.  **Caminhos Explícitos ("Hardcoded"):** Para funcionalidades centrais, como a criação de notas diárias, os caminhos para templates e pastas de destino devem ser definidos como constantes explícitas no topo do script. Isso troca a flexibilidade dinâmica por 100% de previsibilidade e robustez.
    2.  **API Nativa para Operações de Arquivo:** Usar exclusivamente a API nativa do Obsidian, que é sempre estável e disponível:
        *   `app.vault.getAbstractFileByPath(path)` para verificar a existência de um arquivo.
        *   `app.vault.createFolder(path)` para criar pastas.
        *   `app.vault.read(templateFile)` para obter o conteúdo de um template.
        *   `app.vault.create(filePath, content)` para criar o novo arquivo.
    3.  **Confiança no Fluxo Natural do Obsidian:** Após criar um arquivo a partir de um template, não é necessário acionar programaticamente o `Templater` com comandos (`executeCommandById`). Se o usuário tiver o `Templater` configurado para observar novos arquivos (seja nativamente ou via `Journals`), o Obsidian gerenciará esse fluxo de eventos naturalmente. O trabalho do nosso script termina na criação do arquivo.

    **Aprendizado Crucial:** A tentativa de criar um sistema "inteligente" que se adapta dinamicamente às configurações de outros plugins introduziu uma complexidade frágil e não testável. A solução SOTA, neste caso, foi a mais simples e direta, priorizando a estabilidade e a independência sobre a flexibilidade. Para funções de infraestrutura, a previsibilidade é mais valiosa do que a adaptabilidade dinâmica.


### **Entrada de Aprendizado #36: O Padrão de Ouro para Gráficos Modulares ("Gerador de Bloco")**

**O Problema:** Os templates de dashboard estavam se tornando poluídos com dezenas ou centenas de linhas de código `chartsview` monolítico. A lógica de busca de dados e a configuração de aparência estavam misturadas e repetidas em múltiplos arquivos, tornando a manutenção difícil e propensa a erros.

**A Causa Raiz:** Uma série de tentativas de modularização falhou devido a uma compreensão incompleta das limitações e do ciclo de vida dos plugins `Charts View` e `Dataview`. As abordagens falhas incluíam:
*   Tentar fazer o `dataviewjs` retornar um objeto de configuração completo para um bloco `chartsview` que não esperava isso.
*   Erros de sintaxe YAML ao tentar injetar código JavaScript.
*   Erros de escopo do JavaScript (`AsyncFunction is not defined`, `Illegal return statement`) ao tentar executar scripts externos.
*   Tentar usar APIs específicas de um plugin (`dv.container`) em um ambiente onde elas não existiam.

**A Solução/Padrão de Ouro: "Gerador de Bloco via `dv.view`"**

A solução mais robusta, que alcança 100% de modularização, é contraintuitiva: **não usamos o bloco ` ```chartsview ``` ` diretamente no template**. Em vez disso, usamos um bloco `dataviewjs` que constrói dinamicamente a string de um bloco `chartsview` e a insere na página.

Esta arquitetura é composta por 3 partes:

**Parte 1: O Script de View Modular (O "Gerador de YAML")**

Este é o cérebro da operação. Ele vive no backend (`99 - BACKEND/Scripts/Views/Charts/`) e tem uma única responsabilidade: gerar uma **string de texto** que contém um bloco de código `chartsview` completo e funcional.

*   **Estrutura CORRETA (`viewFocoVsPausa.js`):**

    ```javascript
    // O script é envolto em uma IIFE que retorna a função principal.
    // Isso resolve todos os problemas de escopo com 'eval'.
    (() => {
        return async function renderChart(dv, input) {
            try {
                // 1. Lógica de busca de dados (usa 'dv' e 'input')
                const chartData = [...];

                // 2. Lógica de apresentação (usa 'input.view_mode', etc.)
                const viewMode = input.view_mode || 'column';
                let specificOptions = (viewMode === 'line') ? `...` : `...`;

                // 3. Constrói a STRING COMPLETA do bloco de código
                const yamlString = `
    \`\`\`chartsview
    type: ${viewMode === 'line' ? 'Line' : 'Column'}
    data: ${JSON.stringify(chartData)}
    options:
      ${specificOptions}
      // ... resto das opções ...
    \`\`\`
    `;
                // 4. Retorna a string final
                return yamlString.trim();

            } catch (e) {
                // Retorna um bloco de erro em caso de falha
                return `\`\`\`chartsview\ntype: Line\noptions:\n  title: { text: "ERRO: ${e.message}" }\n\`\`\``;
            }
        }
    })();
    ```

*   **❌ O Erro a Evitar #1:** Fazer o script retornar um objeto JavaScript (`return { type, data, options }`). O plugin `Charts View` não sabe o que fazer com isso quando chamado desta forma.
*   **❌ O Erro a Evitar #2:** Ter um `return` no escopo global do arquivo. Isso causa um `SyntaxError: Illegal return statement` quando executado via `eval`. A estrutura `(() => { return function(...) })()` evita isso.

**Parte 2: O Bloco Invocador (No Template do Dashboard)**

Este é um bloco `dataviewjs` minimalista e reutilizável. Sua única função é carregar, executar o script gerador e "imprimir" o resultado na página.

*   **Estrutura CORRETA (no template):**

    ```dataviewjs
    // --- Bloco Invocador SOTA vFinal ---
    try {
        const scriptPath = "99 - BACKEND/Scripts/Views/Charts/viewFocoVsPausa.js";
        const scriptContent = await dv.io.load(scriptPath);
        if (!scriptContent) throw new Error(`Script não encontrado`);

        // eval() executa a IIFE e nos retorna a função renderChart
        const renderChart = eval(scriptContent);
        if (typeof renderChart !== 'function') throw new Error("Script não retornou uma função.");

        // Passa o contexto da página atual para o script
        const input = { 
            hub_uid: dv.current().hub_uid,
            view_mode: dv.current().view_mode_foco_pausa 
        };
        
        // O script retorna a string completa do bloco de código
        const chartBlockString = await renderChart(dv, input);
        
        // dv.paragraph "imprime" o bloco de código na nota para o Obsidian e o Charts View processarem
        dv.paragraph(chartBlockString);

    } catch (e) {
        dv.paragraph(`❌ **Erro ao renderizar gráfico:** ${e.message}`);
    }
    ```

*   **❌ O Erro a Evitar:** Usar ` ```chartsview ``` ` como invólucro. Essa abordagem se provou instável e cheia de erros de parsing e de escopo. A abordagem correta é usar ` ```dataviewjs ``` ` para ter controle total sobre o processo.

**Parte 3: O Botão de Controle de Estado (No Template do Dashboard)**

Este botão não interage diretamente com o gráfico. Ele simplesmente modifica o *estado* (um campo no frontmatter) e força a re-renderização, o que faz o Bloco Invocador rodar novamente com o novo estado.

*   **Estrutura CORRETA (no template, após o invocador):**

    ```meta-bind-button
    label: "📊 Alternar Visualização"
    style: default
    actions:
      - type: inlineJS
        code: |
          const activeFile = this.app.workspace.getActiveFile();
          if (!activeFile) return;

          // 1. Modifica o estado no frontmatter
          await this.app.fileManager.processFrontMatter(activeFile, (fm) => {
              const currentMode = fm.view_mode_foco_pausa || 'column';
              fm.view_mode_foco_pausa = (currentMode === 'column' ? 'line' : 'column');
          });
          
          // 2. Dispara a re-renderização de todas as views Dataview na página
          setTimeout(() => { this.app.workspace.trigger("dataview:refresh-views"); }, 150);
    ```

**Aprendizado Crucial:** A modularização completa com `Charts View` é um processo em duas etapas:
1.  Um `dataviewjs` **gera** a string de um bloco `chartsview`.
2.  O Obsidian/Dataview **renderiza** essa string, o que aciona o plugin `Charts View`.

Qualquer tentativa de fazer o `dataviewjs` *dentro* de um bloco `chartsview` retornar a configuração completa falhará. O padrão "Gerador de Bloco" é a arquitetura SOTA definitiva para este plugin, proporcionando máxima manutenibilidade, reutilização e poder de customização.