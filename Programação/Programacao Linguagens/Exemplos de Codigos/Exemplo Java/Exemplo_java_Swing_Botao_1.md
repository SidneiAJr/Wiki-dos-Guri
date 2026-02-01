# Exemplo de Codigo de Botão
```Java
private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
    String usuario = jt_usuario.getText().trim();
    String senha   = new String(jp_senha.getPassword()).trim();

    // Verifica se ambos os campos estão preenchidos
    if(usuario.isEmpty() || senha.isEmpty()){
        JOptionPane.showMessageDialog(
            this,
            "Por favor, preencha usuário e senha!",
            "Aviso!",
            JOptionPane.WARNING_MESSAGE
        );
        return;
    }

    // Validação de login
    switch(usuario){

        case "Dazai":
            if(senha.equals("Dazai")){
                JOptionPane.showMessageDialog(this, "Bem-vindo ao Sistema Dazai");
                lb_saida.setText("Bem-vindo Dazai");
                new Dazai().setVisible(true);
            } else {
                JOptionPane.showMessageDialog(this, "Senha incorreta!");
            }
            break;

        case "Shimatsu":
            if(senha.equals("Shimatsu")){
                JOptionPane.showMessageDialog(this, "Bem-vindo ao Sistema Shimatsu");
                lb_saida.setText("Bem-vindo Shimatsu");
                new Shimatsu().setVisible(true);
            } else {
                JOptionPane.showMessageDialog(this, "Senha incorreta!");
            }
            break;

        case "Koko":
            if(senha.equals("Koko")){
                JOptionPane.showMessageDialog(this, "Bem-vindo ao Sistema Koko");
                lb_saida.setText("Bem-vindo Koko");
                new Koko().setVisible(true);
            } else {
                JOptionPane.showMessageDialog(this, "Senha incorreta!");
            }
            break;

        default:
            JOptionPane.showMessageDialog(
                this,
                "Usuário não encontrado!",
                "Erro",
                JOptionPane.ERROR_MESSAGE
            );
            break;
    }
}

```
## Botão "Limpar" (Resetar campos)
```java
private void jButton3ActionPerformed(java.awt.event.ActionEvent evt) {                                         
    // Limpa os campos de usuário e senha
    jp_senha.setText("");
    jt_usuario.setText("");
}
```

## Botão "Cancelar" (voltar pra tela de login)

```java
private void jButton2ActionPerformed(java.awt.event.ActionEvent evt) {                                         
    // Fecha a tela atual
    this.dispose();

    // Abre a tela de login novamente
    new Login_classe().setVisible(true);
}
}
```

## 📘 Explicação do Código 
🎯 Objetivo

Esse código implementa a lógica de um formulário de login com Java Swing, validando usuário e senha e abrindo telas diferentes conforme o usuário autenticado.

## ✅ Funcionalidades

Captura usuário e senha da interface

Valida credenciais via switch

Exibe mensagens com JOptionPane

Abre janelas específicas para cada usuário

Botão para limpar os campos

Botão para cancelar e voltar ao login

## 🧠 Conceitos Aplicados

Programação orientada a eventos (ActionListener)

Manipulação de componentes Swing (JTextField, JPasswordField)

Estrutura de decisão switch

Instanciação de janelas em Java GUI

## 🚨 Observações Técnicas

Está usando autenticação fixa (hardcoded) — bom para estudo


