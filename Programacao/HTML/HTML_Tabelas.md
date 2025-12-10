# 📌 Documentação: Tabelas no HTML

O elemento de tabela no HTML é utilizado para **organizar dados em linhas e colunas**.  
Ele é composto por elementos que definem a **estrutura da tabela**, dividindo informações de maneira organizada.

---

## 🧱 Estrutura Básica da Tabela

A tabela é construída a partir dos seguintes elementos:

| Elemento | Função |
|---------|--------|
| `table` | Representa a tabela inteira |
| `tr` | Representa uma linha |
| `td` | Representa uma célula de dados dentro da linha |
| `th` | Representa uma célula de cabeçalho (título de coluna) |

---

## 🎛 Detalhamento dos Elementos

### **1) `table`**
É o elemento principal.  
Tudo que faz parte da tabela precisa estar dentro dele.

---

### **2) `tr` (Table Row)**
Representa **uma linha** da tabela.  
Cada tabela possui uma ou mais linhas.

---

### **3) `td` (Table Data)**
Representa **cada célula** dentro de uma linha.  
É onde ficam os **dados**.

---

### **4) `th` (Table Header)**
Funciona como o `td`, porém é utilizado para **títulos de coluna ou seção**.  
O texto geralmente aparece **em negrito** e **centralizado** por padrão.  
É usado para identificar o que cada coluna representa.

---

## 🔹 Seções Opcionais em uma Tabela

| Seção | Função |
|------|--------|
| `thead` | Agrupa o cabeçalho da tabela |
| `tbody` | Agrupa o conteúdo principal (linhas com dados) |
| `tfoot` | Agrupa o rodapé da tabela (ex.: totais, notas) |

Essas seções **não alteram a aparência**, mas facilitam organização e leitura, especialmente em tabelas grandes.

---

## ✅ Para Que Serve uma Tabela

Use tabelas quando você precisa:

- Comparar informações
- Exibir dados organizados
- Mostrar registros em formato de linha-coluna
- Criar relatórios ou listagens

---

## ⚠️ Quando Não Usar Tabelas

Não utilize tabela para posicionar ou montar layout da página.  
Layout deve ser feito com:

- `div`
- grid
- flexbox
- bootstrap (quando aplicável)

Tabelas são **apenas para dados estruturados**.

---

## 🏁 Resumo Final

| Elemento | Representa |
|---------|------------|
| `table` | A tabela completa |
| `tr` | Uma linha |
| `td` | Uma célula de conteúdo |
| `th` | Uma célula de cabeçalho |

---

