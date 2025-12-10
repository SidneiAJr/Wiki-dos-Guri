# Suporte de Linguagens Vercel:

## ✅ Suporte nativo da Vercel
⚙️ Frontend Frameworks (Suporte total e automático):

Next.js (feito pela própria Vercel)

React (via frameworks como Create React App)

Vue.js (ex: Nuxt)

Svelte / SvelteKit

Angular

Astro

SolidJS

Hugo, Eleventy (Static Site Generators)

Remix

## 🌐 Suporte a HTML e CSS

Sim, totalmente suportado.

Você pode subir um projeto estático contendo apenas arquivos .html, .css, .js.

Muito útil pra portfólios ou páginas simples.

## ❌ PHP NÃO é suportado nativamente

A Vercel não roda PHP no servidor (não tem Apache nem suporte a execução de código PHP).

Se você subir arquivos .php, eles serão tratados como texto ou baixados como download.

💡 Alternativas se você quiser rodar PHP:

Hospedar seu backend PHP em outro lugar (como Heroku, Render, Hostinger, etc.)

Fazer sua aplicação frontend na Vercel e conectar via API ao seu backend PHP hospedado fora.

Mudar o backend pra algo que a Vercel suporte (Node.js por exemplo).

Basta colocar seu projeto com index.html na raiz e deployar. Vercel serve como hospedagem estática.
