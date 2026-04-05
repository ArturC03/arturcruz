# Padrões e Diretrizes do Projeto Pessoal

Este documento estabelece as regras e os padrões de codificação para o projeto do site pessoal, com o objetivo de manter a simplicidade, a legibilidade, a manutenibilidade e a consistência em todos os ficheiros.

## Princípios Fundamentais

1.  **Simplicidade e Concisão:** O site deve ser uma plataforma direta para partilhar informações específicas sobre a pessoa e o seu estilo pessoal. A complexidade deve ser evitada.
2.  **Legibilidade e Manutenção:** A estrutura e o código devem ser fáceis de ler, compreender e manter a longo prazo.

## Contexto das Páginas do Projeto

O site é composto por várias páginas que servem propósitos distintos, focando-se na apresentação pessoal, artigos de pensamento e contacto.

### `index.html` (Homepage)

*   **Propósito:** É a página principal do site, servindo como introdução a Artur Cruz.
*   **Conteúdo:**
    *   Apresenta Artur como um estudante de ciência de computadores.
    *   Inclui um elemento de navegação principal (`nav`) para `inicio` (index.html), `pensamentos` (takes.html) e `contactos` (contacts.html).
    *   Contém uma breve apresentação pessoal e um toque de humor com a mensagem "Error: Void" para mais informações.
    *   Inclui meta-informação para SEO e partilha social (Open Graph).
    *   O `<title>` da página é "Still Don't Know".

### Páginas em `takes/` (Artigos/Pensamentos)

*   **Propósito:** Estas páginas contêm artigos de blog ou "pensamentos" (takes) mais aprofundados sobre tópicos técnicos ou de interesse pessoal. Cada página é um item individual numa lista.
*   **Exemplo (`takes/css-maquina-estados.html`):**
    *   Explora o conceito de CSS como uma máquina de estados, relacionando pseudo-classes com autómatos finitos em Ciência de Computadores.
    *   Inclui um título específico (`<title>`), data (`.date`), texto detalhado do artigo e meta-informação.
    *   A navegação permite voltar para a página geral de `takes.html` ou para outras secções do site.
*   **Geral:** Cada página de "take" deve ter um título claro e específico, uma data e o conteúdo que explora um tópico em profundidade.

### `takes.html` (Página de Lista de Pensamentos)

*   **Propósito:** Serve como índice ou lista de todos os artigos/pensamentos disponíveis na secção `takes/`.
*   **Conteúdo Inferido:** Espera-se que liste os títulos dos artigos, possivelmente com datas e links diretos para cada um, a partir da navegação encontrada em outras páginas.

### `contacts.html` (Página de Contactos)

*   **Propósito:** Fornecer informações de contacto e/ou formas de entrar em contacto com o autor.
*   **Conteúdo Inferido:** Deverá conter detalhes de contacto, possivelmente links para redes sociais ou um formulário de contacto, com base na convenção de nomes e na navegação.

### `logs.html` (Página de Logs da Vida)

*   **Propósito:** Atua como índice para registos de eventos marcantes da vida do autor, tanto positivos quanto negativos. Serve como um diário mais cru e completo, distinto da página de projetos.
*   **Estrutura de Entradas:** Cada entrada de log segue um padrão de "STATUS [DATA] Título do Log", com tags associadas para categorização (ex: "academico", "profissional", "pessoal").
*   **Navegação:** Cada entrada na página `logs.html` linka para uma página detalhada individual para cada log.

## Padrões de Codificação

### HTML Semântico e Acessível

*   **Estrutura:** Utilizar tags HTML semânticas (`<header>`, `<nav>`, `<main>`, `<footer>`, `<article>`, `<section>`, etc.) para definir a estrutura do conteúdo. Isso melhora a SEO e a acessibilidade.
*   **Acessibilidade (A11y):**
    *   Todos os elementos `<img>` devem ter um atributo `alt` descritivo.
    *   **Cabeçalhos (`<h1>`-`<h6>`):** Manter uma hierarquia de cabeçalhos lógica e correta. No entanto, para páginas com conteúdo extremamente conciso e direto (como a homepage ou páginas de contacto), onde um cabeçalho pode não ser estritamente necessário para a clareza ou para evitar redundância, a sua omissão pode ser considerada para manter a simplicidade, desde que a semântica geral e a acessibilidade sejam preservadas.
    *   Utilizar atributos `aria-*` apenas quando estritamente necessário para melhorar a experiência de utilizadores com tecnologias assistivas, mantendo a simplicidade.
*   **Base:** Incluir sempre `<!DOCTYPE html>` e as meta tags essenciais (`<meta charset="UTF-8">`, `<meta name="viewport" content="width=device-width, initial-scale=1.0">`).
*   **Títulos de Página (`<title>`):** Cada página deve ter um atributo `<title>` claro e descritivo que reflita o seu conteúdo (ex: "Still Don't Know", "CSS como Máquina de Estados | Still Don't Know", "Logs da Vida | Still Don't Know").

### CSS

*   **Variáveis CSS:** Amplamente utilizar variables (`--var-name`) para cores, tipografia, espaçamentos e outros valores reutilizáveis. Isto é crucial para a manutenção e a alternância entre temas (claro/escuro).
*   **Novas Variáveis para Logs:** Introduzidas variáveis para cores de status de logs: `--log-info-color`, `--log-debug-color`, `--log-warn-color`, `--log-fatal-color`.
*   **Comentários:**
    *   Agrupar estilos em secções lógicas com comentários de nível superior (ex: `/* HEADER & NAV */`, `/* LOGS PAGE STYLES */`).
    *   Adicionar comentários concisos para explicar decisões de design específicas, hacks ou partes de código não óbvias.
*   **Formatação e Estilo:**
    *   **Indentação:** Preferencialmente 2 espaços.
    *   **Espaçamento:** Usar uma linha em branco entre blocos de regras (seletores) para separar secções lógicas de estilo, melhorando a legibilidade.
    *   **Nomenclatura:** Usar `kebab-case` para nomes de classes e IDs (ex: `main-text`, `take-entry`, `log-entry`, `log-status`).
    *   **Unidades:** Usar unidades relativas (`em`, `rem`, `%`, `vh`, `vw`) onde apropriado para escalabilidade e acessibilidade, e `px` para definições precisas quando necessário.
*   **Tipografia:** Utilizar `"Fira Code", monospace;` como a fonte principal para todo o texto. Ajustar `line-height` e `letter-spacing` para maximizar a legibilidade.
*   **Design Responsivo:** Utilizar `media queries` de forma eficaz para garantir uma experiência fluida em todos os dispositivos.
*   **Cores:** Utilizar apenas cores CSS padrão (ex: `Black`, `FireBrick`) ou variáveis que mapeiem para elas, mantendo a paleta definida.

### Nomenclatura de Ficheiros e Organização

*   **Nomes de Ficheiros:** Utilizar `kebab-case` para todos os ficheiros (ex: `index.html`, `style.css`, `contacts.html`, `logs.html`).
*   **Organização:** Para um site pessoal simples, manter os ficheiros na raiz é ideal. Se o projeto crescer, considerar subpastas para `css/`, `js/` ou `assets/`, mas sempre priorizando a simplicidade.

---

**Regras Adicionais e Restrições:**
*   O site deve manter-se simples e conciso.
*   Apenas cores CSS padrão são utilizadas (ex: `Black`, `FireBrick`).

---

*Este documento servirá como referência para manter a consistência e a qualidade do código no projeto.*