# Exemplo de codigo Java Swing Botao

```java
private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
    // Quando o botão é clicado, cria uma nova instância da tela de Login
    Login_classe login = new Login_classe();

    // Torna a nova tela de login visível para o usuário
    login.setVisible(true);
}    
```

# 📘 Explicação pra colocar no teu GitHub
## 🎯 Função do código

Esse método é acionado ao clicar no botão (provavelmente botão "Login" ou "Voltar para Login") e simplesmente abre a tela de login da aplicação.

## 🧠 O que ele faz

Cria um objeto da classe Login_classe

Exibe essa tela usando setVisible(true)

## ✅ Quando isso é usado

Esse tipo de lógica é comum quando o sistema precisa:

Retornar para a tela inicial

Reabrir a tela de login após sair de outra tela

Navegar entre formulários no Java Swing
