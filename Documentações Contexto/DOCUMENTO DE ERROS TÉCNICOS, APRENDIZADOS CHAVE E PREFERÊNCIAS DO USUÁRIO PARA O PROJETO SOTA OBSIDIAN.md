

---

**DOCUMENTO DE ERROS TÉCNICOS, APRENDIZADOS CHAVE E PREFERÊNCIAS DO USUÁRIO PARA O PROJETO "SOTA OBSIDIAN"**

**Preâmbulo:**
Este documento destina-se a registrar os principais desafios técnicos encontrados, as soluções e abordagens que se mostraram eficazes, e as preferências de comunicação e implementação do usuário (Madrev) durante o desenvolvimento do sistema "State of the Art Obsidian Systems". O objetivo é fornecer um contexto valioso para futuras interações e para a IA que auxiliará na implementação.

**I. Desafios Técnicos Comuns e Soluções/Aprendizados:**

1.  **Erro de Parsing em Blocos `meta-bind-js-view` (`ERROR [MB_PARSING] - Failed to parse. Cause: expected '{' or whitespace`):**
    *   **Problema:** Ocorria quando a primeira linha significativa na seção de configuração do bloco (antes do `---`) não era uma declaração de input `{campo_lido} as variavel_local`.
    *   **Solução/Aprendizado:** Para blocos `meta-bind-js-view` que precisam calcular e salvar um valor no frontmatter (mesmo que não leiam um input direto do frontmatter para iniciar seu cálculo), é **obrigatório** ter uma linha de "bind de input dummy" como a primeira declaração no cabeçalho. Exemplo: `{data} as dataNotaDummyForParsing`. A variável local criada (`dataNotaDummyForParsing`) não precisa ser usada no script JavaScript subsequente. Comentários (`//`) também não são permitidos nesta seção de cabeçalho.

2.  **Erro `ReferenceError: dv is not defined` ou `TypeError: dv.current is not a function` em `meta-bind-js-view`:**
    *   **Problema:** Scripts dentro de `meta-bind-js-view` não têm acesso global direto à API do Dataview (`dv`) ou à função `dv.current()` da mesma forma que blocos ` ```dataviewjs ``` ` nativos.
    *   **Solução/Aprendizado:**
        *   Acessar a API do Dataview explicitamente: `const dv = this.app.plugins.plugins["dataview"]?.api;`.
        *   Sempre verificar se `dv` foi obtido com sucesso: `if (!dv) { console.error(...); return VALOR_PADRAO; }`.
        *   Para obter dados da página atual:
            ```javascript
            const filePath = this.currentFilePath || (this.app.workspace.getActiveFile() ? this.app.workspace.getActiveFile().path : null);
            if (!filePath) { /* tratar erro */ }
            const paginaAtual = dv.page(filePath); 
            ```
        *   Acessar campos do frontmatter da página atual via `paginaAtual.nome_do_campo`.
        *   Acessar `moment.js` via `const moment = this.app.plugins.plugins.templater?.tp.date.moment || window.moment;` e verificar sua disponibilidade.

3.  **Erro `TypeError: X.toFormat is not a function` vs. `X.format is not a function`:**
    *   **Problema:** Confusão entre os métodos de formatação de data de objetos Luxon DateTime (retornados por `dv.date()` ou `paginaAtual.file.day`) e objetos Moment.js.
    *   **Solução/Aprendizado:**
        *   Objetos Luxon DateTime (Dataview) usam: `luxonDate.toFormat("YYYY-MM-DD")`.
        *   Objetos Moment.js (Templater, ou `moment()` global) usam: `momentDate.format("YYYY-MM-DD")`.
        *   É crucial saber qual tipo de objeto de data está sendo manipulado para usar o método de formatação correto. Para converter entre eles, pode-se usar `moment(luxonDate.toJSDate())` ou `dv.date(momentDate.toDate())`.

4.  **Problemas de Reatividade na Exibição de Valores Calculados por `meta-bind-js-view`:**
    *   **Problema:** Um `VIEW[{campo_frontmatter}][text]` do Meta Bind ou um Dataview inline `$=dv.current().campo_frontmatter` nem sempre atualizava *imediatamente* após um script `meta-bind-js-view` (com `save to`) atualizar o `campo_frontmatter`. A atualização frequentemente exigia fechar/reabrir a nota.
    *   **Solução/Aprendizado:**
        *   **Para exibição de valores simples do frontmatter:** Dataview inline (`$=dv.current().campo_frontmatter` ou `$=this.campo_frontmatter`) provou ser mais consistentemente reativo para exibir valores que foram atualizados no frontmatter por um script Meta Bind.
        *   **Para blocos `meta-bind-js-view` que apenas calculam e salvam (são `hidden`):** Garantir que eles modifiquem o frontmatter corretamente. A reatividade da *exibição* será responsabilidade do Dataview inline.
        *   Se a reatividade imediata for absolutamente crítica e as abordagens acima falharem, um botão "Recalcular Stats" que força a reexecução dos scripts pode ser uma alternativa, mas o objetivo é a atualização automática.

5.  **Filtragem de Itens de Lista/Tasks por Seção (`item.section.subpath` ou `t.section.subpath`):**
    *   **Problema:** A propriedade `section.subpath` pode ser inconsistente ou difícil de usar de forma confiável para filtrar itens que estão diretamente sob uma heading H2 (como `## LOGS DO DIA`), especialmente para `tasks` ou quando a query é feita via `dv.query()` de dentro de um script JS.
    *   **Solução/Aprendizado:**
        *   Para logs que *não são tasks* (ex: Ideias, Reflexões), a query DataviewJS usando `paginaAtual.file.lists.filter(l => l.section && typeof l.section.subpath === 'string' && l.section.subpath.trim() === "NOME_DA_SECAO_SEM_HASHES")` funcionou bem.
        *   Para logs que *são tasks* (ex: Desafios), foi mais robusto remover o filtro de seção explícito na query DataviewJS e confiar nas tags de tipo e período (ex: `#desafio/dificuldade` e `#periodo/manha`), assumindo que esses logs/tasks só serão criados na seção correta pelo QuickAdd.

6.  **Formatação de Logs pelo QuickAdd e Leitura pelo Dataview:**
    *   **Aprendizado:** Definir um formato de log padronizado e rico em metadados (com data completa, hora, tags de tipo, tags de período e campos inline Dataview para o Pomodoro) é crucial.
    *   O QuickAdd (via User Script) é excelente para inserir esses logs formatados.
    *   O DataviewJS (ou DQL mais simples) é usado para *ler e exibir* esses logs nas seções corretas do Daily Note.

7.  **Scripts Dedicados vs. Scripts Genéricos com Variáveis no QuickAdd:**
    *   **Problema:** Passar variáveis de uma Macro QuickAdd para um User Script genérico (se o script não exporta uma estrutura `settings`) pode ser pouco intuitivo na interface do QuickAdd.
    *   **Solução/Aprendizado:** Usar scripts User Script dedicados para cada ação específica (ex: `logAguaScript.js`, `logRefeicaoBoaScript.js`) onde as constantes são definidas dentro do próprio script é mais robusto e fácil de gerenciar do que tentar passar muitas variáveis via configuração de passo de macro.

**II. Preferências do Usuário (Madrev) para Colaboração:**

1.  **Comunicação e Iteração:**
    *   **Abordagem Passo a Passo:** Apresentar UMA sub-etapa/funcionalidade por vez. Aguardar o teste e o feedback do usuário (geralmente com prints) antes de prosseguir.
    *   **Confirmação Explícita:** Sempre finalizar uma resposta com uma pergunta clara sobre se podemos continuar ou se há dúvidas.
    *   **Sinal Verde:** Aguardar o "sinal verde" do usuário antes de gerar novas seções do plano de implementação ou grandes blocos de código para uma nova fase.
    *   **Discussão e Refinamento:** O usuário valoriza discutir, refinar ideias e "tampar buracos" antes da implementação. Estar aberto a múltiplas iterações de design.

2.  **Fornecimento de Código:**
    *   **Scripts Completos:** Sempre fornecer scripts e blocos de código COMPLETOS, mesmo que apenas uma pequena parte tenha sido alterada. Não usar "..." ou referências a "como fizemos antes" para partes do código. O usuário prefere copiar e colar o bloco inteiro.
    *   **Clareza e Comentários (no código final):** Embora comentários no cabeçalho do `meta-bind-js-view` causem erro, comentários *dentro* da seção JavaScript (após o `---`) são bem-vindos para explicar a lógica.

3.  **Foco na Visão "State of the Art":**
    *   **Não Simplificar Demais por Padrão:** O usuário busca o "MELHOR SISTEMA", "EXCEPCIONAL", "REVOLUCIONÁRIO". Evitar a mentalidade de "para começar" ou "visão de futuro" para funcionalidades que podem ser implementadas agora, mesmo que complexas. Abraçar a complexidade se ela levar a um sistema melhor.
    *   **Automação Máxima:** Sempre buscar a solução mais automatizada e inteligente.
    *   **Dados Precisos e Granulares:** Garantir que todos os logs e métricas tenham data e hora para análises futuras pela IA e pelo próprio usuário.

4.  **Gamificação e Stats de Vida:**
    *   Este é um componente central. A lógica de pontuação, os diferentes "stats" (Saúde, Gênio, Mediocridade, Memória, Energia, Eficiências) e a futura dashboard gamificada são prioritários.

5.  **Respeito ao Conhecimento do Usuário:**
    *   O usuário está aprendendo e testando ativamente. Ele frequentemente identifica problemas ou inconsistências e fornece feedback valioso. Valorizar essa colaboração.

**III. Avisos Gerais para a IA que Continuará o Projeto:**

*   **Revise o "MANIFESTO DO PROJETO SOTA OBSIDIAN" completo** (que será fornecido) para entender todos os requisitos e a arquitetura planejada.
*   **Consulte este documento de "Erros e Aprendizados"** para evitar repetir problemas já solucionados.
*   **Siga as "Preferências do Usuário para Colaboração"** estritamente para uma interação produtiva.
*   **Priorize a funcionalidade e a robustez dos scripts.** A estética (CSS) será refinada em uma fase posterior.
*   **Mantenha o console do desenvolvedor do Obsidian em mente** como a principal ferramenta de depuração para scripts DataviewJS e Meta Bind JS.
*   **Lembre-se dos caminhos de pasta específicos do usuário** para templates, scripts e logs.
*   **Contexto é Rei:** O usuário valoriza que a IA lembre e utilize todas as informações e decisões tomadas anteriormente.
