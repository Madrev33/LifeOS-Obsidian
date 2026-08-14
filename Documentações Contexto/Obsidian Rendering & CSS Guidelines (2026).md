# 📘 Obsidian Rendering & CSS Guidelines (2025/2026)
**Autor:** Madrev Assistant
**Data:** Janeiro 2026
**Contexto:** Migração de Scripts DataviewJS para Engine v1.8+

---

## 1. O Que Mudou? (A Raiz dos Problemas)

A partir das versões recentes (1.7 -> 1.8+), o Obsidian alterou drasticamente como lida com o DOM (Document Object Model) para otimizar performance.

### 🚨 Principais Mudanças:
1.  **Strict Containerization:** O `dv.container` não é mais um bloco "infinito" e solto. Ele agora é restrito pelo layout pai. Se você não definir largura explícita, ele pode colapsar (altura 0) ou esticar infinitamente (largura 100% da viewport).
2.  **Flexbox Agressivo:** O Obsidian agora usa Flexbox nativamente em quase todas as views. Seus scripts antigos que assumiam `display: block` padrão muitas vezes quebram o alinhamento.
3.  **Variáveis Semânticas:** Cores hardcoded (`#FFFFFF`, `#000000`) agora quebram a UX porque o Obsidian força o modo escuro/claro via variáveis CSS. Se usar hex, seu texto some no fundo errado.

---

## 2. As Novas Regras de Ouro (Best Practices)

### Regra #1: Contenha seu Grid (`max-width`)
Em monitores largos (Ultrawide), um Grid com `1fr` vai esticar os cards e criar "buracos" enormes entre eles.
*   **Solução:** Sempre envolva seu dashboard em um Wrapper com `max-width`.

### Regra #2: Grid > Flexbox (Para Dashboards)
Evite `display: flex` para alinhar cards. O Flexbox é ruim para manter a grade alinhada quando os itens têm alturas diferentes.
*   **Solução:** Use `display: grid` com `minmax` e `auto-fill`.

### Regra #3: Separe Gaps (`row-gap` vs `column-gap`)
O `gap` genérico aplica o mesmo espaço vertical e horizontal. Visualmente, isso parece errado porque o olho humano percebe listas verticais de forma diferente.
*   **Solução:** Use `column-gap` menor (lateral) e `row-gap` maior (respiro vertical).

---

## 3. Certo vs. Errado (Exemplos Práticos)

### ❌ Caso 1: Cores e Temas
**Errado:** Texto preto fixo (fica invisível no Dark Mode).
```javascript
// ❌ ERRADO
element.style.color = "#333333"; 
element.style.background = "#ffffff";
```

**Certo:** Uso de variáveis semânticas do Obsidian.

```javascript
// ✅ CERTO
element.style.color = "var(--text-normal)";
element.style.background = "var(--background-primary-alt)";
element.style.border = "1px solid var(--background-modifier-border)";
```


---

### ❌ Caso 2: Layout de Grid (O problema do "Espaço Gigante")

**Errado:** Grid que divide a tela em 4 partes iguais, não importa o tamanho do monitor.

```css
/* ❌ ERRADO: Em tela grande, os cards ficam com 500px de largura e muito distantes */
.grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr); 
    gap: 20px;
}
```

**Certo:** Grid responsivo travado e denso.

```css
/* ✅ CERTO: Wrapper trava a largura total, Grid preenche inteligentemente */
.wrapper {
    width: 100%;
    max-width: 900px; /* Trava a largura total */
    margin: 0 auto;   /* Centraliza */
}
.grid {
    display: grid;
    /* Cards têm no minimo 200px, preenchendo o espaço disponível */
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 10px;
}
```


---

### ❌ Caso 3: Tipografia e Responsividade

**Errado:** Tamanhos fixos em pixels.

```css
/* ❌ ERRADO */
.titulo { font-size: 18px; }
.card { height: 300px; }
```

**Certo:** Unidades relativas e Line Clamp (corte de texto).

```css
/* ✅ CERTO */
.titulo { font-size: 1.1em; } /* Escala com a config do usuário */
.preview {
    /* Corta o texto após 3 linhas para não estourar o card verticalmente */
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
```


---

## 4. Cheat Sheet de Variáveis CSS (Obsidian 1.8+)

Use estas variáveis para garantir que seus scripts nunca quebrem quando você mudar de tema.


| Categoria | Variável CSS | Descrição |
| :-- | :-- | :-- |
| **Fundos** | `var(--background-primary)` | Fundo principal da nota |
|  | `var(--background-primary-alt)` | Fundo de cards/blocos (levemente diferente) |
|  | `var(--background-modifier-border)` | Cor de bordas sutis |
| **Texto** | `var(--text-normal)` | Cor padrão do texto |
|  | `var(--text-muted)` | Texto secundário/cinza (legendas) |
|  | `var(--text-faint)` | Texto muito apagado (placeholders) |
|  | `var(--text-on-accent)` | Texto branco sobre botões coloridos |
| **Cores** | `var(--interactive-accent)` | Cor principal do tema (Roxo padrão) |
|  | `var(--text-error)` | Vermelho (Erros) |
|  | `var(--color-green)` | Verde (Sucesso - requer tema compatível ou RGB) |


---

## 5. Estrutura Padrão para Scripts DataviewJS

Para evitar problemas de renderização assíncrona ("flickering" ou layout quebrado ao carregar), use sempre esta estrutura:

```javascript
async function renderView() {
    const container = dv.container;
    
    // 1. Limpeza e Reset (Crucial para re-renders)
    container.innerHTML = "";
    container.style.width = "100%"; // Força ocupação total
    
    // 2. CSS Scoped (Injetado dinamicamente)
    const style = document.createElement('style');
    style.textContent = `
        .meu-script-wrapper { max-width: 900px; margin: 0 auto; }
        /* ... resto do CSS ... */
    `;
    container.appendChild(style);

    // 3. Wrapper Principal
    const wrapper = document.createElement('div');
    wrapper.className = 'meu-script-wrapper';
    
    // 4. Lógica e Renderização
    // ... seu código ...

    container.appendChild(wrapper);
}

await renderView();
```
