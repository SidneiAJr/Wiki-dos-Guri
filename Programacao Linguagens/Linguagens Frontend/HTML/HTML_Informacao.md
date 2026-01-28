# 📖 Guia Completo de Tags HTML

O HTML é dividido em **grupos de elementos** com finalidades diferentes.  
A seguir, explicamos **cada grupo e suas principais tags**, mostrando **como e quando usar**.

---

## 🧱 1. Estrutura Básica da Página

Esses elementos formam o **esqueleto de qualquer documento HTML**:

| Tag | Função | Explicação |
|-----|--------|------------|
| `<!DOCTYPE html>` | Tipo de documento | Define a versão do HTML usada pelo navegador. |
| `<html>` | Elemento raiz | Envolve todo o conteúdo da página. |
| `<head>` | Metadados | Contém informações não visíveis, como CSS, JS, meta tags. |
| `<body>` | Conteúdo visível | Contém textos, imagens, vídeos e outros elementos que aparecem na tela. |
| `<title>` | Título da aba | Exibe o título da página no navegador. |
| `<meta>` | Metadados | Define charset, viewport, descrição e outras informações. |
| `<link>` | Conexão externa | Conecta arquivos externos como CSS ou ícones. |
| `<script>` | Código JS | Inclui scripts JavaScript. |

---

## 🧭 2. Estrutura de Conteúdo (Seções e Layout)

Organizam o conteúdo em **blocos lógicos**, importantes para **SEO e acessibilidade**:

| Tag | Função | Explicação |
|-----|--------|------------|
| `<header>` | Cabeçalho | Normalmente contém logo, título e menus principais. |
| `<nav>` | Navegação | Agrupa links importantes de navegação. |
| `<main>` | Conteúdo principal | Marca a área central do site. |
| `<section>` | Seção temática | Agrupa conteúdo relacionado por assunto. |
| `<article>` | Artigo independente | Bloco autônomo de conteúdo, como post de blog. |
| `<aside>` | Conteúdo lateral | Informações complementares, como anúncios ou menus secundários. |
| `<footer>` | Rodapé | Informações finais, copyright, links de contato. |
| `<div>` | Contêiner genérico | Elemento neutro para agrupar outros elementos, usado com CSS. |

---

## 📝 3. Textos e Formatação

Tags que controlam **tipografia e estilo semântico do texto**:

| Tag | Função | Explicação |
|-----|--------|------------|
| `<h1>` a `<h6>` | Títulos | Define hierarquia de títulos; `<h1>` é o mais importante. |
| `<p>` | Parágrafo | Cria blocos de texto. |
| `<br>` | Quebra de linha | Insere linha em branco sem iniciar um parágrafo. |
| `<hr>` | Linha horizontal | Separador de conteúdo. |
| `<strong>` | Negrito semântico | Destaca texto importante. |
| `<em>` | Itálico semântico | Indica ênfase ou destaque. |
| `<mark>` | Marca texto | Realça texto, como marcador de destaque. |
| `<small>` | Texto menor | Usado para notas ou informações secundárias. |
| `<blockquote>` | Citação longa | Bloco de citação textual. |
| `<code>` | Código inline | Trechos de código em linha. |
| `<pre>` | Texto pré-formatado | Mantém espaços e quebras de linha. |
| `<abbr>` | Abreviação | Define siglas e abreviações, mostrando tooltip. |
| `<sup>` / `<sub>` | Sobrescrito / Subscrito | Para expoentes e índices. |

---

## 🔗 4. Links e Navegação

Permitem **ligar páginas e criar âncoras**:

| Tag / Atributo | Função | Explicação |
|----------------|--------|------------|
| `<a>` | Link | Cria um link clicável (`href`). |
| `<nav>` | Navegação | Agrupa links principais. |
| `target="_blank"` | Abrir em nova aba | Abre link em outra aba do navegador. |
| `id` + `href="#id"` | Âncora interna | Permite navegar para uma seção específica da página. |

---

## 🖼️ 5. Imagens, Mídia e Gráficos

Exibem **conteúdos visuais**:

| Tag | Função | Explicação |
|-----|--------|------------|
| `<img>` | Imagem | Insere imagens (atributo `src` obrigatório). |
| `<picture>` | Imagens responsivas | Permite diferentes formatos ou tamanhos de imagem. |
| `<video>` | Vídeo | Reproduz vídeos com controles opcionais. |
| `<audio>` | Áudio | Reproduz sons. |
| `<source>` | Múltiplos formatos | Define diferentes fontes para `<video>` ou `<audio>`. |
| `<canvas>` | Área de desenho | Desenho via JavaScript. |
| `<svg>` | Gráfico vetorial | Imagens escaláveis sem perda de qualidade. |

---

## 📋 6. Listas e Tabelas

Organizam **dados e informações**:

| Tag | Função | Explicação |
|-----|--------|------------|
| `<ul>` | Lista não ordenada | Com bolinhas. |
| `<ol>` | Lista ordenada | Com números ou letras. |
| `<li>` | Item de lista | Elemento dentro de listas. |
| `<dl>` | Lista de definição | Lista de termos e descrições. |
| `<dt>` / `<dd>` | Termo / Descrição | Para cada item de definição. |
| `<table>` | Tabela | Estrutura tabular. |
| `<tr>` | Linha da tabela | Contém células. |
| `<td>` | Célula de dados | Contém conteúdo. |
| `<th>` | Cabeçalho de célula | Texto em negrito centralizado. |
| `<thead>` / `<tbody>` / `<tfoot>` | Estrutura | Divide a tabela em cabeçalho, corpo e rodapé. |
| `<caption>` | Título da tabela | Exibe legenda para a tabela. |

---

## 🧍 7. Formulários (Inputs e Controles)

Permitem **interação do usuário**:

| Tag | Função | Explicação |
|-----|--------|------------|
| `<form>` | Agrupa campos | Contêiner principal do formulário. |
| `<label>` | Rótulo | Associa texto a inputs. |
| `<input>` | Campo de entrada | Textos, senhas, checkboxes, radio, etc. |
| `<select>` | Menu suspenso | Lista de opções. |
| `<option>` | Opção | Item dentro do select. |
| `<textarea>` | Campo longo | Área de texto multilinha. |
| `<button>` | Botão | Aciona ações. |
| `<fieldset>` | Agrupamento | Agrupa campos relacionados. |
| `<legend>` | Título do grupo | Nome do fieldset. |
| `<datalist>` | Sugestões | Lista de opções para input. |
| `<output>` | Resultado | Exibe cálculos ou resultados. |
| `<progress>` | Barra de progresso | Indica progresso de uma tarefa. |
| `<meter>` | Medidor | Representa valor dentro de intervalo. |

---

## 🎨 8. Mídia e Interatividade

Elementos que permitem **conteúdos externos e interativos**:

| Tag | Função | Explicação |
|-----|--------|------------|
| `<iframe>` | Embutir página | Insere conteúdo externo (ex: YouTube). |
| `<embed>` | Conteúdo externo | PDFs, vídeos, apps. |
| `<object>` | Objetos multimídia | Conteúdos variados com fallback. |
| `<map>` / `<area>` | Mapas clicáveis | Áreas clicáveis em imagens. |
| `<canvas>` | Desenho JS | Área dinâmica de gráficos e animações. |

---

## ⚙️ 9. Atributos Globais

Podem ser usados **em quase qualquer tag**:

| Atributo | Função | Explicação |
|-----------|--------|------------|
| `id` | Identificação | Único na página; usado em CSS e JS. |
| `class` | Classe CSS | Agrupa elementos para estilo ou script. |
| `style` | Inline CSS | Adiciona estilo direto no elemento. |
| `title` | Tooltip | Mostra dica ao passar mouse. |
| `hidden` | Ocultar | Esconde o elemento. |
| `contenteditable` | Editável | Permite que o usuário edite o conteúdo. |
| `tabindex` | Navegação | Ordem de foco ao usar TAB. |
| `data-*` | Dados personalizados | Armazena informações extras no HTML. |
| `draggable` | Arrastável | Permite mover o elemento com drag & drop. |

---

## 🔒 10. Acessibilidade e SEO

Melhoram **leitura por máquinas, SEO e inclusão**:

| Tag / Atributo | Função | Explicação |
|----------------|--------|------------|
| `alt` | Descrição de imagem | Essencial para leitores de tela. |
| `aria-*` | Acessibilidade | Define roles, estados e propriedades. |
| `<label for="">` | Associa label | Liga label ao input correspondente. |
| `<main>`, `<nav>`, `<header>`, `<footer>` | Estrutura semântica | Ajuda na navegação de leitores de tela. |
| `<meta name="description">` | SEO | Descrição resumida da página. |
| `<meta name="keywords">` | SEO | Palavras-chave (menos relevante hoje, mas usado). |

---

💡 **Resumo e Dicas**  

1. Domine primeiro **estrutura básica e seções** (`html`, `head`, `body`, `header`, `main`, `footer`).  
2. Depois, foque em **conteúdo textual** e **listagens** (`p`, `h1-h6`, `ul`, `ol`, `table`).  
3. Explore **mídia e formulários** (`img`, `video`, `form`, `input`).  
4. Sempre use **atributos globais** e **semântica** para acessibilidade e SEO.  
5. Combine HTML com **CSS e JS** para criar páginas dinâmicas e responsivas.
