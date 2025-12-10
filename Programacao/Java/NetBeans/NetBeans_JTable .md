# 📊 Tutorial de Uso do JTable no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE**.

## 🧱 Passo 2: Criar o JFrame
Crie um JFrame como de costume.

## 📋 Passo 3: Inserir o JTable
1. Na aba **Palette**, escolha **Table** (`JTable`).  
2. Arraste para o JFrame.  
3. Normalmente o NetBeans coloca o JTable dentro de um **JScrollPane** automaticamente.

## ⚙️ Passo 4: Configurar Propriedades
1. Clique na tabela e abra **Properties**.  
2. Em **model**, clique nos `...` e defina colunas e linhas iniciais.

Exemplo:
| Nome | Idade | Cidade |
|------|--------|--------|

## 💡 Passo 5: Alterar Dados via Código
```java
DefaultTableModel modelo = (DefaultTableModel) tblPessoas.getModel();
modelo.addRow(new Object[]{"João", 25, "São Paulo"});
