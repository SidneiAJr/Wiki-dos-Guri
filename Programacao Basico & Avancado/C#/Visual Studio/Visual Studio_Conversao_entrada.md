# 🔄 Conversões de Tipos em C# (toString, ToDouble, Parse, Convert)

## 📖 Introdução

Em **C#**, é muito comum precisar **converter valores entre tipos diferentes** — por exemplo, transformar um número em texto, um texto em número, ou mudar o tipo de dado (como de `int` para `double`).  
Essas operações são conhecidas como **conversões de tipo** ou **casting**.

O C# oferece várias formas seguras de fazer essas conversões, e cada uma tem um propósito específico.  
Saber quando e como usar cada uma evita erros de execução e garante que o programa funcione corretamente.

---

## 🧩 Tipos de Conversões em C#

As conversões em C# podem ser divididas em **duas categorias principais**:

1. **Conversões Implícitas:**  
   Acontecem automaticamente, sem precisar de comando explícito.  
   Ocorrem quando não há risco de perda de dados.  
   Exemplo: converter um `int` em `double`.

2. **Conversões Explícitas:**  
   Precisam ser feitas manualmente, porque podem causar **perda de precisão** ou **erros de formato**.  
   Exemplo: converter um `string` em `int`.

---

## 🔹 Conversões Implícitas

Essas conversões acontecem **automaticamente** quando o compilador sabe que o valor pode ser convertido sem risco.

**Exemplo de casos comuns:**
- `int` → `long`  
- `float` → `double`  
- `char` → `int`

**Características:**
- Não exigem comando de conversão.  
- Não causam exceções.  
- Mantêm o valor original intacto.  

---

## 🔸 Conversões Explícitas (Casting)

Quando há risco de perda de dados ou erro, o programador precisa **forçar a conversão**.  
Isso é chamado de **casting**.

**Exemplo de situações:**
- `double` → `int`  
- `decimal` → `float`  
- `object` → tipo específico

**Observações:**
- O valor pode ser **truncado** (parte decimal perdida).  
- É usado quando o programador tem certeza da compatibilidade entre os tipos.  

---

## 🧮 Métodos de Conversão Mais Comuns

A seguir estão os métodos mais usados para converter valores em C# de forma controlada e segura.

---

### 🟩 `ToString()`
Converte um valor de **qualquer tipo** para **texto** (`string`).  
Usado para exibir números, datas, booleanos, etc.  

**Exemplos de uso:**
- Mostrar valores numéricos na interface.  
- Exibir mensagens concatenando texto com números.  
- Converter resultados antes de exibir em `Label`, `TextBox` ou `Console`.

**Observações:**
- Retorna sempre um valor do tipo `string`.  
- Nunca lança exceção (mesmo que o valor seja nulo).  

---

### 🟦 `Convert.ToInt32()` / `Convert.ToDouble()` / `Convert.ToDecimal()`
Usados para converter **qualquer tipo compatível** em número.  
Esses métodos são mais seguros que `Parse()`, pois aceitam valores nulos e tratam erros com mais segurança.

**Diferenças:**
- `Convert.ToInt32()` → converte para inteiro.  
- `Convert.ToDouble()` → converte para ponto flutuante.  
- `Convert.ToDecimal()` → converte para decimal de alta precisão.  

**Vantagens:**
- Aceita `null` sem lançar erro.  
- Lança exceções se o valor não puder ser convertido.  
- Ideal para entradas vindas de formulários (`TextBox`, por exemplo).  

---

### 🟨 `Parse()`
Converte uma **string** em um tipo numérico.  
É direto e rápido, mas exige que o conteúdo da string seja **válido**, ou ocorrerá erro.

**Usos típicos:**
- Converter texto digitado em campos para números.  
- Leitura de dados de arquivos ou inputs.  

**Cuidados:**
- Se o texto estiver vazio, nulo ou com letras, o programa lança uma exceção.  
- Ideal usar junto com **validação** antes da conversão.  

---

### 🟧 `TryParse()`
É a forma **segura** do `Parse()`.  
Ele **tenta converter** o valor e **retorna verdadeiro ou falso**, sem lançar erro caso a conversão falhe.

**Usos comuns:**
- Ler dados de usuários sem travar o programa.  
- Validar se o texto digitado é realmente numérico.  
- Tratar conversões sem precisar de `try/catch`.  

**Características:**
- Retorna `true` se a conversão for bem-sucedida.  
- Retorna `false` se não for possível converter.  
- Evita exceções e é ideal para entrada de dados do usuário.  

---

## 🧠 Comparativo Geral

| Método                | Tipo de Conversão | Lança Erro? | Aceita `null`? | Ideal Para |
|------------------------|------------------|--------------|----------------|-------------|
| **ToString()**         | Qualquer → Texto | ❌ Não       | ✅ Sim          | Exibição e logs |
| **Convert.ToDouble()** | Texto/Número → Double | ⚠️ Sim se inválido | ✅ Sim | Entradas genéricas |
| **Parse()**            | Texto → Número   | ⚠️ Sim       | ❌ Não          | Quando o formato é garantido |
| **TryParse()**         | Texto → Número   | ❌ Não       | ✅ Sim          | Entradas de usuário |
| **Casting (int)**      | Numérico → Outro | ⚠️ Sim       | ❌ Não          | Conversões numéricas diretas |

---

## 💡 Boas Práticas

- Sempre use **TryParse()** quando estiver lendo valores digitados pelo usuário.  
- Use **Convert** para conversões gerais entre tipos compatíveis.  
- Use **ToString()** apenas para exibir informações, nunca para cálculos.  
- Evite `Parse()` em dados não validados — ele gera exceções.  
- Em campos de interface, valide o texto antes de tentar converter.  
- Se precisar formatar números (como casas decimais ou moeda), use parâmetros dentro de `ToString()` com formatação.  

---

## 🧮 Exemplos Práticos (Explicativos)

- Converter número em texto: **ToString()**  
  > “Serve para mostrar valores numéricos na interface.”  

- Converter texto em número: **Parse()** ou **TryParse()**  
  > “Usado quando o usuário digita um valor em um campo.”  

- Converter entre tipos numéricos: **(int)**, **Convert.ToDouble()**, etc.  
  > “Ideal para cálculos e operações matemáticas.”  

---

## ⚙️ Situações Comuns no Windows Forms

1. O usuário digita um valor em um **TextBox** (string).  
2. O sistema precisa converter esse valor para **int** ou **double** para fazer cálculos.  
3. Depois de processar, o resultado é convertido novamente em **string** para ser exibido em um **Label** ou **TextBox** de saída.

Esse ciclo é extremamente comum em sistemas de cadastro, cálculo, formulários e interfaces gráficas.

---

## 🔗 Referências

- Documentação oficial do C#:  
  [https://learn.microsoft.com/dotnet/csharp/programming-guide/types/casting-and-type-conversions](https://learn.microsoft.com/dotnet/csharp/programming-guide/types/casting-and-type-conversions)  
- Métodos de conversão em C#:  
  [https://learn.microsoft.com/dotnet/api/system.convert](https://learn.microsoft.com/dotnet/api/system.convert)

---

## ✅ Conclusão

As conversões em C# são essenciais para tratar corretamente os dados entre interface e lógica de negócio.  
Com o uso correto de `ToString()`, `Convert`, `Parse` e `TryParse`, é possível garantir **segurança**, **eficiência** e **clareza** no tratamento de informações.  

Dominar essas conversões é um passo importante para criar aplicações robustas e sem erros.
