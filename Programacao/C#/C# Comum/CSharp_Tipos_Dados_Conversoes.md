# C# – Tipos de Dados e Conversões

## 1. Tipos de Dados

### ✔ Tipos por Valor
São armazenados diretamente na memória stack.

- int  
- float  
- double  
- decimal  
- bool  
- char  
- struct  
- enum  

Características:
- Armazenam o próprio valor  
- Não podem ser nulos, a menos que sejam "nullable" (ex: int?)  
- Cópias geram novos valores independentes  

---

### ✔ Tipos por Referência
Armazenados no heap.

- string  
- array  
- class  
- interface  
- delegate  
- object  

Características:
- Armazenam referência para o dado  
- Podem ser nulos  
- Ao copiar, apontam para o mesmo objeto  

---

## 2. Conversões de Tipos

### ✔ Conversão Implícita
Automática e segura.  
Exemplos:
- int → long  
- float → double  
- char → int  

---

### ✔ Conversão Explícita (Casting)
Obrigatória quando:
- Existe risco de perda de dados  
- Conversão é entre tipos incompatíveis  


---

## 3. Conversões com Métodos do .NET

### ✔ Convert  
Faixas seguras de conversão com tratamento interno.

### ✔ Parse  
Converte strings para tipos, mas falha se estiver inválido.

### ✔ TryParse  
Converte strings com segurança, sem lançar exceção.

---

## 4. Nullable Types (Tipos anuláveis)
Permitem que tipos por valor aceitem null.

- int?  
- float?  
- bool?

Operadores importantes:
- ??  
- ?.  
- !  

---

## 5. Boxing e Unboxing

### ✔ Boxing
Tipo por valor convertido para object.

### ✔ Unboxing
object convertido de volta para o tipo original.

---

## 6. Tipos Dinâmicos

### ✔ dynamic
Ignora checagem de tipo em compilação e só valida em runtime.

---

## 7. Tipos Anônimos
Criados sem declarar uma classe, usados principalmente com LINQ.

---

## 8. Tuplas
Armazenam múltiplos valores em uma variável.

Suportam nomear elementos.

---


