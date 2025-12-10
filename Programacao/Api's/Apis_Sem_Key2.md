# 🌐 Lista de APIs sem Chave — Parte 2

Essa é a continuação da lista de **APIs públicas que não exigem autenticação (sem key/token)**.  
Ideais para **testes, estudos, prototipagem** e demonstrações de código.

> ⚠️ Mesmo sem chave, algumas têm *rate limit* (limite de requisições).  
> Sempre verifica os termos de uso antes de usar em produção.

---

## 💡 Geral / Utilidades

| Nome | Descrição | Endpoint |
|------|------------|-----------|
| **DuckDuckGo Instant Answer API** | Retorna respostas rápidas, definições e dados úteis sem rastrear o usuário. | `https://api.duckduckgo.com/?q=serendipity&format=json` |
| **Free Dictionary API** | Dicionário completo com significados, pronúncias e exemplos (em inglês). | `https://api.dictionaryapi.dev/api/v2/entries/en/code` |
| **Bored API** | Sugere atividades aleatórias para combater o tédio. | `https://www.boredapi.com/api/activity` |
| **Advice Slip** | Gera conselhos aleatórios. | `https://api.adviceslip.com/advice` |
| **Numbers API** | Fatos interessantes sobre números. | `http://numbersapi.com/random/math` |

---

## 🖼️ Imagens / Mídia

| Nome | Descrição | Endpoint |
|------|------------|-----------|
| **Picsum Photos** | Gera imagens de placeholder aleatórias, útil pra testes de layout. | `https://picsum.photos/400/300` |
| **Dog CEO API** | Retorna fotos aleatórias de cachorros. | `https://dog.ceo/api/breeds/image/random` |
| **The Cat API** | Fotos aleatórias de gatos 🐱 | `https://api.thecatapi.com/v1/images/search` |
| **PlaceIMG** | Imagens de categorias específicas (nature, tech, etc.). | `https://placeimg.com/640/480/tech` |

---

## 🌎 Dados Públicos e Localização

| Nome | Descrição | Endpoint |
|------|------------|-----------|
| **Zippopotam.us** | Retorna informações de CEP/ZIP para vários países. | `https://api.zippopotam.us/us/33162` |
| **Open Notify** | Dados em tempo real da ISS (Estação Espacial Internacional). | `http://api.open-notify.org/iss-now.json` |
| **Nationalize.io** | Estima nacionalidade provável a partir de um nome. | `https://api.nationalize.io?name=nathaniel` |
| **Agify.io** | Estima idade provável com base em um nome. | `https://api.agify.io?name=meelad` |
| **Genderize.io** | Estima gênero provável a partir de um nome. | `https://api.genderize.io?name=lucas` |

---

## 💰 Criptomoedas e Economia

| Nome | Descrição | Endpoint |
|------|------------|-----------|
| **CoinGecko API** | Retorna preços e dados de criptomoedas em tempo real. | `https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd` |
| **ExchangeRate.host** | Conversor de moedas gratuito sem chave. | `https://api.exchangerate.host/latest?base=USD&symbols=BRL,EUR` |

---

## 🧠 Ciência, Clima e Educação

| Nome | Descrição | Endpoint |
|------|------------|-----------|
| **Open Meteo** | Dados meteorológicos e previsões do tempo. | `https://api.open-meteo.com/v1/forecast?latitude=-23.5&longitude=-46.6&current_weather=true` |
| **Open AQ** | Qualidade do ar em tempo real em várias cidades. | `https://api.openaq.org/v2/latest` |
| **Open Data NASA** | Acesso a diversos dados públicos da NASA. | `https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY` *(usa chave demo pública)* |

---

## 🧩 APIs para Testes e Desenvolvimento

| Nome | Descrição | Endpoint |
|------|------------|-----------|
| **JSONPlaceholder** | API fake para testar requisições. | `https://jsonplaceholder.typicode.com/posts` |
| **HTTPBin** | Testa métodos e headers HTTP. | `https://httpbin.org/get` |
| **ReqRes** | Endpoints REST de exemplo. | `https://reqres.in/api/users` |
| **Public APIs Directory** | Lista completa de APIs públicas categorizadas. | `https://api.publicapis.org/entries` |

---

