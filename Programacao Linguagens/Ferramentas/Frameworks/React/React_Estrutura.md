# 🧩 Estrutura e Funcionamento dos Arquivos no React

Quando criamos um projeto React (usando `create-react-app` ou `expo init`), o ambiente vem com uma estrutura padrão de arquivos e pastas.  
Cada parte tem um papel essencial no funcionamento da aplicação.

Abaixo está uma explicação detalhada dos principais diretórios e arquivos.

---

## 📁 node_modules/

Essa pasta contém **todas as dependências e bibliotecas** que o projeto usa.  
Ela é gerada automaticamente quando você instala pacotes com `npm install` ou `yarn`.  

⚠️ Você **nunca deve editar nada** dentro de `node_modules`.  
Se for apagada, pode ser recriada a qualquer momento executando o comando de instalação novamente.

---

## 📁 src/

A pasta **src** (source) é o **coração da aplicação**.  
Aqui ficam todos os arquivos de código que você realmente desenvolve: componentes, estilos, imagens e lógicas do app.

Dentro de `src`, normalmente encontramos:

- **App.js / App.jsx:**  
  É o **componente principal** da aplicação.  
  Serve como ponto de partida da interface, onde outros componentes são importados e exibidos.

- **index.js / index.jsx:**  
  É o **arquivo que inicializa o React** e conecta o código à tela do usuário.  
  No React web, ele liga o React ao elemento HTML principal (`root`).  
  No React Native, ele define qual componente será carregado primeiro.

- **assets/**  
  Contém **imagens, ícones, fontes e vídeos** utilizados no projeto.

- **components/**  
  Guarda os **componentes reutilizáveis**, como botões, cabeçalhos, cards, formulários etc.

- **screens/** ou **pages/**  
  Onde ficam as **telas principais** do aplicativo (como “Home”, “Login”, “Perfil”).  
  Cada tela é composta por vários componentes menores.

- **styles/**  
  Reúne os arquivos de **estilo (CSS, SCSS ou StyleSheet)**, deixando o código mais organizado.

- **services/**  
  Pasta usada para armazenar **funções de conexão com APIs**, autenticação ou banco de dados.

- **hooks/**  
  Contém **funções personalizadas (React Hooks)** criadas para reaproveitar lógicas em diferentes partes do app.

---

## 📁 public/ (React Web)

A pasta **public** só existe em projetos React Web.  
Ela guarda os **arquivos estáticos** que o navegador precisa acessar diretamente — sem passar pelo JavaScript.

Principais arquivos:
- **index.html:**  
  O arquivo HTML base da aplicação.  
  Dentro dele existe uma `<div id="root">` onde o React “injeta” a interface renderizada.

- **favicon.ico / logo.png:**  
  Ícones e imagens exibidos na aba do navegador.

---

## 📄 package.json

Um dos arquivos mais importantes do projeto.  
Ele descreve **tudo que o projeto precisa para funcionar**, incluindo:

- Nome e versão do projeto  
- Lista de dependências e versões instaladas  
- Scripts de inicialização, build e testes (`npm start`, `npm run build`, etc.)  
- Configurações do ambiente

O `package.json` é como a **identidade do projeto React**.

---

## 📄 package-lock.json ou yarn.lock

Esses arquivos **registram as versões exatas** das dependências instaladas.  
Eles garantem que, ao instalar o projeto em outro computador, todas as bibliotecas fiquem exatamente iguais.

---

## 📄 App.js / App.jsx

É o **componente principal** da aplicação React.  
Ele é o ponto de entrada da interface e contém os elementos que serão exibidos na tela.

No React Native, o `App.js` é o arquivo que o Expo (ou Metro bundler) executa primeiro.

---

## 📄 index.js / index.jsx

Arquivo responsável por **inicializar o React**.  
É aqui que o aplicativo começa de fato a “rodar”, conectando o código JavaScript à renderização visual (DOM no React web ou tela nativa no React Native).

---

## 📄 .gitignore

Lista de arquivos e pastas que devem ser **ignorados pelo Git**.  
Por exemplo: `node_modules/`, chaves de API, arquivos temporários, etc.  
Isso evita que dados desnecessários sejam enviados para o repositório.

---

## 📄 README.md

Arquivo de documentação do projeto.  
É o primeiro texto exibido no GitHub e serve para descrever:
- O objetivo do projeto  
- Como instalar e rodar  
- Tecnologias usadas  
- Créditos e licença

---

## 📁 .expo/ (somente em projetos Expo)

Essa pasta é criada automaticamente quando você usa o **Expo** no React Native.  
Ela armazena configurações internas, como cache, chaves e histórico do projeto.  
Normalmente, você **não precisa editar** nada nela.

---

## 🧩 Fluxo de Funcionamento do React

1. O **index.js** inicializa o React e carrega o componente principal (`App.js`).  
2. O **App.js** define a interface principal e importa outros componentes.  
3. Os componentes exibem informações e interagem com o usuário.  
4. Toda atualização visual é controlada pelo **estado (state)** e pelo **Virtual DOM**, garantindo performance.  

---

## 💡 Resumo Final

| Elemento | Função |
|-----------|--------|
| `node_modules/` | Armazena todas as dependências do projeto |
| `src/` | Contém todo o código-fonte da aplicação |
| `App.js` | Componente principal, ponto central da interface |
| `index.js` | Inicia o React e conecta à interface |
| `public/` | Arquivos estáticos acessados diretamente (React web) |
| `package.json` | Configurações, dependências e scripts do projeto |
| `.gitignore` | Define o que não será versionado pelo Git |
| `README.md` | Documentação principal do projeto |
| `.expo/` | Configurações internas do Expo (React Native) |

---

