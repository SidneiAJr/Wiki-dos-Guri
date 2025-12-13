# ⌨️ Tipos de Entrada no Android

## 🧠 Introdução

Os **tipos de entrada** definem como o teclado virtual (soft keyboard) se comporta e quais caracteres o usuário pode digitar em um campo de texto (`EditText`).  
Esses tipos são configurados com o atributo **`android:inputType`**, usado diretamente no XML do layout.

---

## 🗂️ Tabela de Tipos de Entrada

| **Tipo de Entrada** | **Valor (`android:inputType`)** | **Descrição** |
|----------------------|----------------------------------|----------------|
| **Texto Simples** | `text` | Entrada de texto genérica. |
| **Texto com E-mail** | `textEmailAddress` | Otimizado para entrada de e-mail (inclui “@” e “.com”). |
| **Senha (oculta)** | `textPassword` | Oculta o texto digitado. Ideal para senhas. |
| **Números Inteiros** | `number` | Permite apenas números inteiros. |
| **Número Decimal** | `numberDecimal` | Permite números com ponto decimal. |
| **Número com Sinal** | `numberSigned` | Permite números positivos e negativos. |
| **Telefone** | `phone` | Entrada para número de telefone. |
| **Texto Multilinha** | `textMultiLine` | Permite múltiplas linhas de texto. |
| **URL** | `textUri` | Entrada para endereços de sites (URL). |
| **Nome de Pessoa** | `textPersonName` | Entrada otimizada para nomes próprios. |
| **Endereço Postal** | `textPostalAddress` | Entrada para endereços físicos. |
| **Data e Hora** | `datetime` | Permite digitar data e/ou hora. |
| **Texto em Maiúsculas** | `textCapCharacters` | Força todas as letras em maiúsculas. |
| **Primeira Letra Maiúscula (Palavras)** | `textCapWords` | Primeira letra de cada palavra em maiúscula. |
| **Primeira Letra Maiúscula (Sentenças)** | `textCapSentences` | Primeira letra de cada sentença em maiúscula. |
| **Texto para Pesquisa** | `textSearch` | Campo de texto otimizado para pesquisa. |
| **Senha Visível** | `textVisiblePassword` | Senha exibida no campo (sem ocultar os caracteres). |

---

## 💬 Exemplos e Detalhes

| **Atributo** | **Comportamento** |
|---------------|--------------------|
| `text` | Entrada genérica para qualquer tipo de texto. |
| `textEmailAddress` | Mostra teclado com “@” e “.com”, facilitando o preenchimento de e-mails. |
| `textPassword` | Oculta caracteres digitados (●●●●●). |
| `number` | Mostra teclado numérico, aceitando apenas dígitos. |
| `numberDecimal` | Aceita números com ponto decimal (ex: 3.14). |
| `datetime` | Permite digitação de data e hora. |
| `phone` | Exibe teclado telefônico com parênteses e traços. |

---

## 🧩 Uso no XML

Os valores são aplicados diretamente no layout do app:

```xml
<EditText
    android:id="@+id/inputEmail"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="Digite seu e-mail"
    android:inputType="textEmailAddress" />
