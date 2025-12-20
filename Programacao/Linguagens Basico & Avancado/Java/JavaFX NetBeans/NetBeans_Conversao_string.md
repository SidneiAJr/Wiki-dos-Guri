# 🧭 Tutorial — Métodos de Conversão e Seleção no JavaFX (NetBeans)

Objetivo: aprender como usar os métodos mais comuns de componentes JavaFX e Swing, entendendo o que cada um faz e como aplicar no código.

## 🧩 2. Métodos Importantes

## getText()

Usado para pegar o texto digitado em um campo (TextField, TextArea, etc.).

## 🎯 setText(String texto)

Usado para definir um texto em um campo ou label.

## ✅ isSelected()

Verifica se um botão de seleção (como CheckBox ou RadioButton) está marcado.

## 🔘 setSelected(boolean valor)

Marca ou desmarca uma CheckBox ou RadioButton via código.

## 📋 getSelectedItem()

Usado em ComboBox ou ListView pra saber qual item foi selecionado.


## 🔢 .setModel(new javax.swing.SpinnerNumberModel()) (Swing, não JavaFX)

Se estiver usando JSpinner (Swing), define o modelo numérico do spinner.

## 💬 getValue()

Pega o valor atual de um Spinner.

## 🚫 isEmpty()

Verifica se um campo de texto está vazio.

## 💡 Resumo rápido

| Método           | Tipo                      | Uso                          |
|------------------|---------------------------|-------------------------------|
| `getText()`      | `TextField` / `TextArea`  | Pega o texto                  |
| `setText()`      | `Label` / `TextField`     | Define o texto                |
| `isSelected()`   | `CheckBox` / `RadioButton`| Verifica se está marcado      |
| `setSelected()`  | `CheckBox` / `RadioButton`| Marca/desmarca                |
| `getSelectedItem()` | `ComboBox` / `ListView`| Item selecionado              |
| `setModel()`     | `Swing (JSpinner)`        | Define modelo numérico        |
| `getValue()`     | `Spinner (JavaFX)`        | Retorna valor atual           |
| `isEmpty()`      | `TextField`               | Verifica se está vazio        |
