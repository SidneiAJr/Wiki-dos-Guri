# ☕ Java + SQL com POO (Swing)

Este documento é um **material de estudo** para entender como funciona a **conexão Java com banco de dados SQL**, usando **POO**, **JDBC** e **Swing**.

⚠️ **Atenção:** Todo o exemplo abaixo é **didático** e **inseguro**, feito apenas para aprendizado.

---

## 📌 Visão Geral do Exemplo

O código aborda:

* Programação Orientada a Objetos (POO)
* Conexão com MySQL via JDBC
* Consulta SQL simples
* Uso de `Statement` e `ResultSet`
* Exibição de dados em interface Swing

---

## 1️⃣ Classe de Conexão (`Con`)

```java
class Con{
    protected String Nome_banco;
    protected String Senha;
    protected String usuario;
```

### O que isso faz

* Define uma classe responsável **somente** pela conexão
* Usa atributos protegidos para armazenar dados do banco

### Conceitos envolvidos

* Encapsulamento
* Responsabilidade única (ainda mal aplicada)

⚠️ **Problema:** guardar senha em atributo é inseguro

---

## 2️⃣ Construtor da Classe

```java
public Con(String Nome_banco, String Senha, String usuario) {
    this.Nome_banco = Nome_banco;
    this.Senha = Senha;
    this.usuario = usuario;
}
```

### O que isso faz

* Inicializa a classe com os dados do banco
* Usa `this` para diferenciar atributo de parâmetro

### Conceitos

* Construtor
* Inicialização de objeto

---

## 3️⃣ Método de Conexão com o Banco

```java
public Connection conex(){
    Connection conn = null;
    try {
        String url = "jdbc:mysql://localhost:3306/" + Nome_banco;
        conn = DriverManager.getConnection(url, usuario, Senha);
    } catch (SQLException e) {
    }
    return conn;
}
```

### O que acontece aqui

1. Cria uma variável `Connection`
2. Monta a URL JDBC
3. Usa `DriverManager` para conectar
4. Retorna a conexão (ou `null` se falhar)

### Conceitos

* JDBC
* Tratamento de exceção
* Conexão com banco

⚠️ **Problemas graves**

* `catch` vazio (engole erro)
* Sem logs
* Sem fechamento da conexão

---

## 4️⃣ Método para Listar Usuários

```java
public void listauser(Connection conn) {
    try {
        Statement stmt = conn.createStatement();
        String sql = "SELECT nome_usuario, id FROM usuario";
        ResultSet rs = stmt.executeQuery(sql);
```

### O que isso faz

* Cria um `Statement`
* Executa uma query SQL
* Armazena o resultado em `ResultSet`

### Conceitos

* SQL
* Statement
* ResultSet

⚠️ **Problema:** vulnerável a SQL Injection

---

## 5️⃣ Percorrendo o ResultSet

```java
while(rs.next()){
    String NomeUsuario = rs.getString("nome_usuario");
    int id = rs.getInt("id");

    Jt_usuarios.append("ID: " + id + " - Nome de Usuário: " + NomeUsuario + "\n");
}
```

### O que acontece

* `rs.next()` percorre linha por linha
* Recupera dados por nome da coluna
* Exibe no componente Swing

### Conceitos

* Loop
* Leitura de dados SQL
* Integração backend → interface

---

## 6️⃣ Tratamento de Erro na Consulta

```java
} catch (SQLException e) {
    jt_saida.setText("Erro ao listar usuários: " + e.getMessage());
}
```

### O que isso faz

* Captura erros SQL
* Mostra mensagem no label

### Boas práticas

* Logar erro
* Não mostrar erro técnico ao usuário final

---

## 7️⃣ Evento do Botão (Swing)

```java
private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {
    Con con = new Con("teste", "root", "root");
    Connection conn = con.conex();
```

### O que acontece

* Cria objeto de conexão
* Tenta conectar ao banco

⚠️ **Problema crítico**

* Usuário e senha hardcoded

---

## 8️⃣ Validação da Conexão

```java
if (conn != null) {
    jt_saida.setText("Bem vindo | Lista de Usuarios Cadastrados!");
    listauser(conn);
} else {
    jt_saida.setText("Falha na conexão!");
}
```

### O que isso faz

* Verifica se a conexão funcionou
* Lista usuários ou mostra erro

---

## 🧠 Resumo Técnico

### O que o código ensina bem

* JDBC básico
* Estrutura POO simples
* SQL + Java
* Integração com Swing

### O que **NÃO** fazer em produção

❌ Senha em código
❌ `Statement`
❌ `catch` vazio
❌ Sem `PreparedStatement`
❌ Sem fechar conexão

---
