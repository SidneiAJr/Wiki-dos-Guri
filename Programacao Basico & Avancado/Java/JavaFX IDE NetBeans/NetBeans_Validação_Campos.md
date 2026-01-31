# 🧠 Validação de Campos em **Java Swing**

A **validação de campos** em Java Swing serve para garantir que o usuário preencheu corretamente as informações antes de prosseguir com alguma ação — como **salvar** ou **enviar um formulário**.

---

## ✨ Diferença entre `isEmpty()` e `isBlank()`

| Método | O que faz | Exemplo de comportamento |
|:-------|:-----------|:-------------------------|
| **`isEmpty()`** | Verifica apenas se a string tem **zero caracteres**. | `"   "` → ❌ *não é vazio* |
| **`isBlank()`** | Verifica se a string está vazia **ou contém apenas espaços em branco**. | `"   "` → ✅ *é considerado vazio* |

🔹 **Dica:** o método `trim()` remove os espaços no início e no fim do texto, ajudando a evitar erros em validações simples.

---

## 🔍 Operadores Lógicos na Validação

### `&&` (E lógico)
> Exige que **todas as condições sejam verdadeiras**.

🧩 **Exemplo:** validar que *todos os campos* estão preenchidos.  
Se **qualquer um** estiver vazio, a condição inteira será **falsa**.

```java
if (!campo1.getText().isBlank() && !campo2.getText().isBlank()) {
    JOptionPane.showMessageDialog(null, "Todos os campos preenchidos!");
}
```

## || (OU lógico)

Verifica se pelo menos uma das condições é verdadeira.

🧩 Exemplo: mostrar uma mensagem se qualquer campo estiver vazio.
Se um campo estiver vazio, a condição já será verdadeira.

```java
if (campo1.getText().isBlank() || campo2.getText().isBlank()) {
    JOptionPane.showMessageDialog(null, "Preencha todos os campos antes de continuar!");
}
```

## 💡 Resumo Prático

Pegamos o texto dos campos com getText() ou getPassword().

Verificamos se estão vazios com isBlank() ou isEmpty().

Combinamos verificações com:

&& → todos os campos

|| → qualquer campo

Exibimos mensagens apropriadas com JOptionPane para orientar o usuário.

## 🧩 Exemplo completo:

```java
if (campoNome.getText().isBlank() || campoEmail.getText().isBlank()) {
    JOptionPane.showMessageDialog(null, "Por favor, preencha todos os campos!");
} else {
    JOptionPane.showMessageDialog(null, "Cadastro realizado com sucesso!");
}
```
