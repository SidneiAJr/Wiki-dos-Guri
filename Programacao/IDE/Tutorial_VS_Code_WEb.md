# 🌐 Tutorial Avançado para WEB — Atalhos e Emmet no VS Code

O **Emmet** é um recurso embutido no Visual Studio Code que permite escrever HTML e CSS de forma ultra rápida.  
Com ele, você usa **atalhos e expressões curtas** que o editor expande automaticamente em código completo. 🚀

---

## ⚙️ Atalhos Básicos (HTML)

| Comando | Resultado | Descrição |
|----------|------------|------------|
| `div*2` | Cria **2 divs** | Gera duas tags `<div></div>` |
| `p*2` | Cria **2 parágrafos** | Gera `<p></p>` duas vezes |
| `lorem` | Gera um texto fictício (Lorem Ipsum) | Ideal para preencher conteúdo |
| `lorem10` | Gera **10 palavras** de texto Lorem Ipsum |
| `ul>li*3` | Cria uma lista com **3 itens** | `<ul><li></li><li></li><li></li></ul>` |
| `section>div.container>p*2` | Estrutura completa com seção, container e parágrafos |
| `.box` | Cria uma `<div class="box"></div>` |
| `#menu` | Cria uma `<div id="menu"></div>` |
| `a[href="#"]{Clique aqui}` | Gera um link com texto "Clique aqui" |

---

## 💡 Exemplos Rápidos

### 🔹 Criar duas divs
```html
div*2
```

| Ação                                              | Descrição                      |
| ------------------------------------------------- | ------------------------------ |
| `Ctrl + Espaço`                                   | Mostra sugestões do Emmet      |
| `Tab`                                             | Expande o atalho em código     |
| `Ctrl + /`                                        | Comenta / descomenta linha     |
| `Shift + Alt + ↓ / ↑`                             | Duplica a linha acima/abaixo   |
| `Alt + Z`                                         | Quebra de linha automática     |
| `Ctrl + Shift + P` → “Emmet: Expand Abbreviation” | Executa manualmente a expansão |

| Abreviação                                      | Resultado                              |
| ----------------------------------------------- | -------------------------------------- |
| `header>nav>ul>li*3>a{Link $}`                  | Cria um cabeçalho com menu de 3 links  |
| `main>section*2>h2+p`                           | Duas seções com título e parágrafo     |
| `form>input:text+input:password+button{Enviar}` | Cria um formulário simples             |
| `.grid>.item*4`                                 | Cria uma estrutura de grid com 4 itens |

## ⚙️ Atalhos Diretos

| Atalho | Expande para | Descrição |
|---------|---------------|------------|
| `script:src` | `<script src=""></script>` | Cria uma tag de script com atributo `src` para incluir um arquivo JavaScript externo |
| `link:css` | `<link rel="stylesheet" href="">` | Cria um link de estilo CSS externo |
