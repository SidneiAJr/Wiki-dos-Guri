# C# – Regex (Expressões Regulares)

## 1. O que é Regex?
Regex é um padrão usado para pesquisar, validar e manipular textos.  
Permite identificar formatos complexos como:
- emails  
- números  
- datas  
- placas  
- CEP  
- padrões customizados  

Usado via classe `System.Text.RegularExpressions.Regex`.

---

## 2. Quando usar Regex?

### ✔ Usos comuns:
- Validação de formulários  
- Busca e extração de partes de texto  
- Substituição de padrões  
- Sanitização de entrada  
- Verificação de formatos  

---

## 3. Principais Componentes da Sintaxe Regex

### ✔ Metacaracteres básicos
- `.` → qualquer caractere  
- `^` → início  
- `$` → fim  
- `*` → zero ou mais  
- `+` → um ou mais  
- `?` → opcional  
- `|` → OU lógico  

---

### ✔ Grupos
- `( ... )` → grupo  
- `(?: ... )` → grupo sem captura  

---

### ✔ Conjuntos
- `[abc]` → um desses  
- `[^abc]` → exceto esses  
- `[0-9]` → intervalo  

---

### ✔ Quantificadores
- `{n}` → exatamente n  
- `{n,}` → n ou mais  
- `{n,m}` → entre n e m  

---

### ✔ Caracteres especiais
- `\d` → dígito  
- `\D` → não dígito  
- `\w` → letra/número/underscore  
- `\W` → inverso  
- `\s` → espaço  
- `\S` → não espaço  

---

## 4. Operações principais

### ✔ IsMatch  
Verifica se o texto combina com o padrão.

### ✔ Match / Matches  
Extrai um ou vários resultados.

### ✔ Replace  
Substitui partes do texto baseado no padrão.

### ✔ Split  
Divide a string usando regex como delimitador.

---

## 5. Flags (Opções)
- IgnoreCase  
- Multiline  
- Singleline  
- Compiled  
- CultureInvariant  

---

## 6. Boas práticas

- Use `@` em strings verbatim para regex  
- Não exagere em regex quando `Contains` resolve  
- Evite padrões muito complexos se puder dividir  
- Documente regex difíceis  
- Teste com ferramentas como Regex101  

---

## 7. Exemplos comuns (padrões)

### ✔ E-mail  
`^[^\s@]+@[^\s@]+\.[^\s@]+$`

### ✔ Número inteiro  
`^\d+$`

### ✔ CEP  
`^\d{5}-?\d{3}$`

### ✔ CPF simples  
`^\d{3}\.\d{3}\.\d{3}-\d{2}$`

### ✔ Telefone  
`^\(?\d{2}\)?\s?\d{4,5}-?\d{4}$`

---
