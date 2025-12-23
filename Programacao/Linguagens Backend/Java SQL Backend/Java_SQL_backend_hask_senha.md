# ☕ Java + JDBC + MySQL + BCrypt (Login e Cadastro) — Versão Mastigada

Este documento **quebra todo o teu código de login/cadastro em partes pequenas**, explicando **o que é**, **pra que serve** e **o que pode dar errado**. Estilo raiz, sem frescura.

---

## 🧠 Visão Geral

O que você está fazendo aqui é basicamente:

1. Conectar no MySQL
2. Criar tabela `usuarios` (se já não existir)
3. Salvar usuário com senha **hashada** usando BCrypt
4. Verificar login comparando senha digitada com hash do banco
5. Perguntar se quer cadastrar caso usuário não exista

Tudo usando **JDBC puro** e **BCrypt** para segurança.

---

## 1️⃣ Imports essenciais

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import javax.swing.JOptionPane;
import org.mindrot.jbcrypt.BCrypt;
```

### O que cada um faz:

* **Connection** → representa a conexão com o banco
* **DriverManager** → abre a conexão JDBC
* **PreparedStatement** → executa SQL com `?` (mais seguro que Statement)
* **ResultSet** → resultado de SELECT
* **SQLException** → captura erros de banco
* **JOptionPane** → mostra janelas de diálogo para usuário
* **BCrypt** → gera e verifica hash de senha

📌 Regra prática: `PreparedStatement` para qualquer INSERT, UPDATE, DELETE ou SELECT com parâmetros.

---

## 2️⃣ Classe utilitária `SenhaUtil` (hash + verify)

```java
public class SenhaUtil {

    // Gera hash da senha (equivalente a password_hash do PHP)
    public static String gerarHash(String senha) {
        return BCrypt.hashpw(senha, BCrypt.gensalt());
    }

    // Verifica senha digitada com hash do banco (equivalente a password_verify)
    public static boolean verificarSenha(String senhaDigitada, String hashBanco) {
        return BCrypt.checkpw(senhaDigitada, hashBanco);
    }
}
```

### O que acontece aqui:

* `gerarHash` → transforma a senha em algo impossível de ler diretamente
* `verificarSenha` → compara a senha digitada com o hash armazenado
* 💡 Importante: **nunca salve senha pura no banco**

---

## 3️⃣ Classe `verificalogin` (login + cadastro)

### Variáveis de conexão:

```java
final String URL = "jdbc:mysql://localhost:3306/meucaixa";
final String USER = "root";
final String PASS = "";
```

* URL → endereço do banco
* USER/PASS → login do MySQL

---

### a) Verificar usuário e senha

```java
public boolean verificarUsuario(){
    String sql = "SELECT senha FROM usuarios WHERE usuario=?";
    try(Connection conexao = DriverManager.getConnection(URL,USER,PASS);
        PreparedStatement stm = conexao.prepareStatement(sql)) {

        String usuario = jt_usuario.getText();
        String senhaDigitada = new String(jt_senha.getPassword());

        stm.setString(1, usuario);
        ResultSet rs = stm.executeQuery();

        if(rs.next()){ // achou usuário
            String hashBanco = rs.getString("senha");
            return SenhaUtil.verificarSenha(senhaDigitada, hashBanco);
        } else {
            return false; // usuário não existe
        }

    } catch(SQLException e){
        e.printStackTrace();
        return false;
    }
}
```

### Explicando:

* SELECT retorna **hash da senha** do banco
* `rs.next()` → verifica se usuário existe
* `verificarSenha` → compara a senha digitada com hash
* ❌ ERRADO: comparar senha digitada direto com `WHERE senha=?` → senha estaria pura no banco

---

### b) Cadastrar usuário (com hash)

```java
public void cadastrar(String usuario, String senha){
    String sql = "INSERT INTO usuarios (usuario, senha) VALUES (?, ?)";

    String senhaHash = SenhaUtil.gerarHash(senha); // gera hash seguro

    try(Connection conexao = DriverManager.getConnection(URL,USER,PASS);
        PreparedStatement stm = conexao.prepareStatement(sql)) {

        stm.setString(1, usuario);
        stm.setString(2, senhaHash); // salva hash no banco
        stm.executeUpdate();

        JOptionPane.showMessageDialog(null, "Usuário cadastrado com sucesso!");

    } catch(SQLException e){
        e.printStackTrace();
    }
}
```

### Explicando:

* `executeUpdate()` → atualiza o banco (INSERT)
* 💡 Importante: **não usar ResultSet aqui**
* Sempre use hash para senha

---

### c) Fluxo login/cadastro (`cadlogar`)

```java
public void cadlogar(){
    String usuario = jt_usuario.getText();
    String senha = new String(jt_senha.getPassword());

    if(verificarUsuario()) {
        JOptionPane.showMessageDialog(null, "Login Sucesso! Abrindo Menu");
        new menu_logado().setVisible(true);
    } else {
        int opcao = JOptionPane.showConfirmDialog(null, "Usuário não cadastrado. Quer cadastrar?");
        if(opcao == JOptionPane.YES_OPTION) {
            cadastrar(usuario, senha); // salva hash no banco
            JOptionPane.showMessageDialog(null, "Usuário cadastrado! Faça login novamente.");
        }
    }
}
```

### Explicando:

* Primeiro tenta logar
* Se usuário não existir → pergunta se quer cadastrar
* `cadastrar(usuario, senha)` → salva hash no banco
* Depois, usuário deve logar de novo

---

## 4️⃣ Botão de login (`jButton1ActionPerformed`)

```java
private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {
    verificalogin login = new verificalogin();
    login.cadlogar(); // fluxo unificado login/cadastro
}
```

### Explicando:

* Instancia a classe interna que trata login/cadastro
* Chama método que decide se loga ou cadastra
* Mantém UI limpa e código organizado

---

## 5️⃣ Boas práticas finais

* **Senha nunca pura no banco** → use BCrypt sempre
* **PreparedStatement** para todo SQL com parâmetros → evita SQL Injection
* **executeUpdate()** para INSERT, UPDATE, DELETE; **executeQuery()** para SELECT
* **rs.next()** obrigatório para SELECT
* **try-with-resources** → fecha conexão automaticamente
* **JOptionPane** → feedback visual ao usuário

---

Se você quiser, posso fazer **uma versão final já pronta inteira do Login + Cadastro + BCrypt**, pronta pra rodar no NetBeans, tudo organizado, sem mexer com JTextField dentro da classe de verificação. Isso deixa o código mais limpo e reutilizável.

Quer que eu faça?
