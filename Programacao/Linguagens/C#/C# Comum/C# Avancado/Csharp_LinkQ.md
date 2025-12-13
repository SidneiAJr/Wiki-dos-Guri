# 🔎 C# | LINQ (Language Integrated Query)

## O que é LINQ?

LINQ significa **Language Integrated Query**.

É um recurso do C# que permite **consultar, filtrar, transformar e manipular dados** de forma simples e legível, usando código C#.

👉 Pense no LINQ como um **SQL dentro do C#**, mas aplicado a:

- Listas
- Arrays
- Coleções
- Bancos de dados (Entity Framework)
- Objetos em memória

---

## Por que LINQ é importante?

Antes do LINQ, o código ficava:

- Verboso
- Cheio de `for`
- Difícil de ler
- Difícil de manter

Com LINQ, o código fica:

✔️ Mais limpo  
✔️ Mais legível  
✔️ Mais expressivo  
✔️ Mais fácil de manter  

---

## Onde o LINQ é usado?

LINQ pode ser usado em:

- `List<T>`
- `Array`
- `Dictionary`
- Resultados de banco de dados (EF Core)
- Qualquer coleção que implemente `IEnumerable`

---

## Como o LINQ funciona?

O LINQ trabalha com **métodos encadeados** (method chaining).

Fluxo mental:


---

## Principais Operações do LINQ

### 🔍 Where — Filtrar dados

Usado para **filtrar elementos** de uma coleção.

Exemplo mental:
> "Quero só os itens que atendem a uma condição"

Responsabilidade:
- Não altera a coleção original
- Retorna uma nova coleção

---

### 🔄 Select — Transformar dados

Usado para **transformar elementos**.

Exemplo mental:
> "Quero pegar só um campo"
> "Quero transformar um objeto em outro"

Responsabilidade:
- Mapeamento de dados
- Projeção

---

### ❓ Any — Existe pelo menos um?

Verifica se **existe algum elemento** que atende a uma condição.

Retorna:
- `true` ou `false`

Muito usado para:
- Validações
- Permissões
- Regras de negócio

---

### ❗ All — Todos atendem?

Verifica se **todos os elementos** atendem a uma condição.

Diferença importante:
- `Any` → pelo menos um
- `All` → todos

---

### 🥇 First / FirstOrDefault

Retorna o **primeiro elemento** da coleção.

Diferença:
- `First` → erro se não existir
- `FirstOrDefault` → retorna `null` ou valor padrão

---

### 🧍 Single / SingleOrDefault

Usado quando **só pode existir um elemento**.

Diferença:
- `Single` → erro se tiver 0 ou mais de 1
- `SingleOrDefault` → aceita 0, mas não aceita mais de 1

Muito usado para:
- Buscar por ID
- Regras onde unicidade é obrigatória

---

### 🔢 Count — Contar elementos

Retorna a **quantidade de itens**.

Pode ser usado:
- Com condição
- Sem condição

---

### 📊 OrderBy / OrderByDescending

Ordena os dados.

- `OrderBy` → crescente
- `OrderByDescending` → decrescente

Não altera a coleção original.

---

### 🧩 GroupBy — Agrupar dados

Agrupa elementos com base em uma chave.

Exemplo mental:
> "Agrupar pessoas por cidade"
> "Agrupar produtos por categoria"

Muito usado em:
- Relatórios
- Estatísticas
- Dashboards

---

## LINQ não modifica dados

Importante entender:

📌 LINQ **não altera a coleção original**  
📌 Sempre retorna uma **nova sequência**

Isso evita efeitos colaterais.

---

## LINQ é execução tardia (Lazy)

LINQ só executa **quando o resultado é realmente usado**.

Ou seja:
- A consulta é montada
- Mas só executa quando você itera ou consome

Isso melhora performance.

---

## LINQ + Lambda

LINQ trabalha fortemente com **expressões lambda**.

Lambda representa:
- Uma função curta
- Sem nome
- Direta

LINQ + Lambda = C# moderno

---

## LINQ em memória vs LINQ no banco

Diferença importante:

### LINQ em memória
- Executa no C#
- Usa CPU da aplicação

### LINQ no banco (Entity Framework)
- Traduz para SQL
- Executa no banco
- Muito mais eficiente para grandes volumes

---

## Erros comuns com LINQ

❌ Usar LINQ dentro de loop  
❌ Buscar tudo do banco e filtrar depois  
❌ Usar `Single` sem garantir unicidade  
❌ Criar consultas complexas demais  

---

## Quando usar LINQ?

✔️ Manipular coleções  
✔️ Consultar dados  
✔️ Regras de negócio  
✔️ Backend moderno  

❌ Não usar quando lógica for simples demais  
❌ Não abusar sem pensar em performance  

---

## Resumo rápido

- LINQ é uma forma poderosa de consultar dados
- Deixa o código limpo e legível
- É essencial em C# moderno
- Muito usado em backend, APIs e sistemas reais

---

