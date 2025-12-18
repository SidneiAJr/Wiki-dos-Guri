# # 📡 Consumo de API – Pokédex com JavaScript

## URL da API:
```js
const url = "https://pokeapi.co/api/v2/pokemon"
```

## Função da API:

```js
// URL base da API pública PokeAPI
// Essa API fornece dados de todos os Pokémon
const url = "https://pokeapi.co/api/v2/pokemon"

// Função assíncrona responsável por buscar o Pokémon
// Pode buscar pelo NOME ou pelo ID
async function procurarNome() {

    // Pega o valor digitado no input de nome
    // trim() remove espaços extras
    // toLowerCase() garante compatibilidade com a API
    const nomePokemon = document
        .getElementById('nome')
        .value
        .trim()
        .toLowerCase()

    // Pega o valor digitado no input de ID
    const idPokemon = document
        .getElementById('idPokemon')
        .value
        .trim()

    // Define o valor de busca:
    // se o ID existir, usa o ID
    // senão, usa o nome
    const busca = idPokemon || nomePokemon

    try {
        // Validação: se nenhum campo foi preenchido
        if (!busca) {
            alert("Digite o nome OU o ID do Pokémon")
            return // Interrompe a função
        }

        // Faz a requisição HTTP para a API
        // Exemplo final: https://pokeapi.co/api/v2/pokemon/pikachu
        const resposta = await fetch(`${url}/${busca}`)

        // Se a resposta não for OK (404, 500 etc),
        // dispara um erro manualmente
        if (!resposta.ok) {
            throw new Error("Pokémon não encontrado")
        }

        // Converte a resposta da API para JSON
        const dados = await resposta.json()

        // Extrai os tipos do Pokémon
        // Ex: ["electric"]
        // map() percorre os tipos
        // join(", ") junta tudo em uma string
        const tipos = dados.types
            .map(t => t.type.name)
            .join(", ")

        // Busca a imagem animada da geração 5 (Black & White)
        // Essa sprite nem sempre existe para todos os Pokémon
        const img =
            dados.sprites
                .versions['generation-v']
                ['black-white']
                .animated
                .front_default

        // Seleciona a div onde os dados serão exibidos
        let saida = document.getElementById("img")

        // Insere o HTML dinamicamente na página
        saida.innerHTML = `
            <img src="${img}" id="pok" alt="${dados.name}"><br>
            <strong>ID Pokémon:</strong> ${dados.id}<br>
            <strong>Nome:</strong> ${dados.name}<br>
            <strong>Tipo:</strong> ${tipos}
        `

    } catch (erro) {
        // Caso aconteça qualquer erro:
        // - Pokémon inexistente
        // - erro de rede
        // - problema na API
        alert("Pokémon não encontrado ⚠️")

        // Mostra o erro detalhado no console (para dev)
        console.error(erro)
    }
}
```

## Bloco Try e catch 
- Try Tenta
- Catch se a tentativa der erro retorna erro


## Saida no HTMl via DOM
```js
 let saida = document.getElementById("img")
        saida.innerHTML = `
            <img src="${img}" id="pok"alt="${dados.name}"><br>
            <strong>ID Pokémon:</strong> ${dados.id}<br>
            <strong>Nome:</strong> ${dados.name}<br>
            <strong>Tipo:</strong> ${tipos}
        `
```
