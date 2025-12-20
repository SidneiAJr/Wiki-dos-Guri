# C# – Reflection

## 1. O que é Reflection?
Reflection permite inspecionar e manipular tipos, propriedades, métodos e atributos em tempo de execução.

Permite:
- Obter nome de classes e membros  
- Criar objetos dinamicamente  
- Invocar métodos  
- Ler atributos customizados  
- Modificar valores de propriedades  

---

## 2. Para que serve Reflection?

### ✔ Frameworks e bibliotecas
Utilizado em:
- ORMs (Entity Framework)  
- IoC containers  
- Serializadores JSON  
- Testes automatizados  

---

### ✔ Análise de tipos
Descobrir:
- Propriedades  
- Métodos  
- Campos  
- Atributos  

---

### ✔ Automação
Criar instâncias de classes de forma dinâmica.

---

### ✔ Atributos personalizados
Reflection lê e interpreta atributos (annotations) colocados no código.

---

### ✔ Carregamento dinâmico de assemblies
Carregar DLLs externas em tempo de execução.

---

## 3. Tipos Principais Usados

- Type  
- MethodInfo  
- PropertyInfo  
- FieldInfo  
- ConstructorInfo  
- Assembly  

---

## 4. Vantagens e Desvantagens

### ✔ Vantagens
- Extremamente flexível  
- Permite automação avançada  
- Usado em frameworks poderosos  

### ❌ Desvantagens
- Mais lento que código normal  
- Pode quebrar encapsulamento  
- Pode ser complexo demais para iniciantes  

---

## 5. Quando usar Reflection?
Use quando você precisa:
- Trabalhar com objetos desconhecidos  
- Criar ferramentas genéricas  
- Automatizar processos  
- Ler configurações via atributos  

Evite usar quando:
- O mesmo resultado pode ser alcançado diretamente  
- Performance é crítica  

---
