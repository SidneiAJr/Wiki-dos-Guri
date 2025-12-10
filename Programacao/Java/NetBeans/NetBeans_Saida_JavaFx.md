# 🧠 Tutorial de Componentes de Saída no NetBeans (Java Swing)

## 📘 Introdução
Neste tutorial, você vai aprender sobre os principais **componentes de saída** usados em **Java Swing**, dentro do **NetBeans IDE**.  
Esses componentes servem para **mostrar informações, mensagens ou resultados** ao usuário.

---

## 🏷️ 1. JLabel

### 💡 O que é
O `JLabel` é um rótulo de texto usado para **mostrar informações simples** na tela.

### 🧩 Exemplo
```java
JLabel label = new JLabel("Resultado:");
label.setText("Soma = 10");
```

### JTextArea
💡 O que é

O JTextArea é uma área de texto com múltiplas linhas, usada para exibir textos longos (mensagens, relatórios, logs, etc.).

```Java
1️⃣ Saída de valores financeiros
jt_saida1.setText(
    "Valor Pix: R$ " + String.format("%.2f", valorPix) + "\n" +
    "Parcela Mensal: R$ " + String.format("%.2f", parcelaMensal) + "\n" +
    "Total Pago: R$ " + String.format("%.2f", totalPago) + "\n" +
    "Valor Antecipado: R$ " + String.format("%.2f", valorPresente) + "\n" +
    "Desconto ao Antecipar: R$ " + String.format("%.2f", desconto)
);
```


### JTextField
💡 O que é

O JTextField é geralmente usado para entrada de texto, mas também pode ser usado para mostrar resultados curtos (uma única linha).

### JOptionPane
💡 O que é

O JOptionPane é usado para mostrar mensagens em janelas pop-up.
Perfeito para avisos, erros ou confirmações.

### JTable
💡 O que é

O JTable serve para mostrar dados organizados em linhas e colunas, como uma planilha ou tabela de resultados.

### 7. JTextPane e JEditorPane
💡 O que são

Esses componentes são versões mais avançadas do JTextArea.
Eles permitem formatação de texto (cores, negrito, HTML, etc.).

## 🧠 Resumo Geral

| 🧩 **Componente** | 💬 **Tipo de Saída** | 🎯 **Ideal para** | 🧾 **Exemplo** |
|--------------------|----------------------|------------------|----------------|
| `JLabel` | Texto simples | Mostrar mensagens curtas | “Resultado: 10” |
| `JTextField` | Uma linha | Exibir valores rápidos | “Usuário: João” |
| `JTextArea` | Múltiplas linhas | Logs e textos longos | Texto com várias linhas |
| `JOptionPane` | Pop-up | Avisos e confirmações | “Sucesso!” |
| `JTable` | Tabela | Dados organizados | Lista de registros |
| `JList` | Lista | Itens selecionáveis | “Item 1, Item 2…” |
| `JTextPane` / `JEditorPane` | Texto formatado | HTML e cores | Texto estilizado |

