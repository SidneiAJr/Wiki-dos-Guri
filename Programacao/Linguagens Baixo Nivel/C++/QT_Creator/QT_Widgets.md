# 🧩 Widgets para Entrada de Dados — Qt Creator (C++)

Além do `QLineEdit`, existem diversos outros **widgets** no Qt que permitem capturar diferentes tipos de entrada de dados, ideais para formulários e interfaces interativas.

---

## 🔢 1️⃣ QSpinBox — Entrada Numérica (Inteiros)

O **QSpinBox** é um widget usado para capturar **números inteiros**.  
Ele exibe setas de incremento e decremento, facilitando a escolha de valores numéricos dentro de um intervalo definido.

### 🧰 Exemplo de uso:
```cpp
QSpinBox *spinBox = new QSpinBox(this);
spinBox->setRange(0, 100);      // Define o intervalo permitido
spinBox->setValue(10);          // Valor inicial
spinBox->setSingleStep(5);      // Passo de incremento
```

## 🧮 2️⃣ QDoubleSpinBox — Entrada de Números Decimais

O QDoubleSpinBox funciona de forma semelhante ao QSpinBox,
mas aceita valores de ponto flutuante (decimais) — ideal para medidas, preços ou percentuais.

🧰 Exemplo de uso:
```cpp
QDoubleSpinBox *doubleBox = new QDoubleSpinBox(this);
doubleBox->setRange(0.0, 10.0);
doubleBox->setDecimals(2);       // Número de casas decimais
doubleBox->setSingleStep(0.1);
```

## 📋 3️⃣ QComboBox — Caixa de Seleção

O QComboBox permite ao usuário escolher uma opção de uma lista suspensa.
Você pode adicionar itens manualmente ou preencher o combo dinamicamente com dados.

🧰 Exemplo de uso:
```cpp
QComboBox *comboBox = new QComboBox(this);
comboBox->addItem("Opção 1");
comboBox->addItem("Opção 2");
comboBox->addItem("Opção 3");

// Capturar item selecionado
QString selecionado = comboBox->currentText();

```


