# 🎮 JavaFX + JDBC + MySQL (CRUD) — Versão Mastigada

Este documento vai **quebrar o teu projeto de cadastro de jogos** em partes pequenas, explicando **o que faz cada parte**, **pra que serve** e **o que pode dar errado**. Tudo na vibe raiz, sem frescura.

---

## 🧠 Visão Geral

O que teu projeto faz:

1. Abrir uma tela JavaFX com formulário de jogos
2. Escolher imagem do jogo
3. Mostrar preview da imagem
4. Conectar no MySQL via JDBC
5. Inserir / Listar / Atualizar / Deletar jogos
6. Atualizar tabela na interface

Tudo usando **Swing + JDBC** (puro).

---

## 1️⃣ Imports (as ferramentas)

```java
import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.List;
import javax.swing.JOptionPane;
import javax.swing.table.DefaultTableModel;
import javax.swing.JFileChooser;
import javax.swing.ImageIcon;
```

### O que cada um faz:

* **Connection / PreparedStatement / ResultSet / SQLException** → trabalhar com o MySQL
* **JOptionPane** → mostrar mensagens pro usuário
* **DefaultTableModel** → organizar dados da JTable
* **JFileChooser / ImageIcon** → selecionar e mostrar imagem

📌 Regra prática:

* Tudo do banco → JDBC
* Tudo da tela → Swing

---

## 2️⃣ Tela Java (formulário)

### Campos principais

* `jt_titulo` → título do jogo
* `jt_plataforma` → plataforma
* `jt_preco` → preço
* `jt_imagem` → caminho da imagem (não editável)
* `jPanel2` → painel onde aparece o preview da capa

### Botões

* **Novo** → limpa o formulário
* **Salvar | Editar** → salva/atualiza o banco
* **Excluir** → remove do banco
* **Atualizar** → atualiza a JTable
* **Escolher Imagem** → abre JFileChooser e mostra preview

---

## 3️⃣ Botão "Escolher Imagem"

```java
private void btn_escolherimgActionPerformed(java.awt.event.ActionEvent evt) {
    JFileChooser fileChooser = new JFileChooser();
    fileChooser.setDialogTitle("Escolher Imagem");
    fileChooser.setAcceptAllFileFilterUsed(false);
    fileChooser.addChoosableFileFilter(new javax.swing.filechooser.FileNameExtensionFilter("Imagens", "jpg", "jpeg", "png", "gif"));

    int resultado = fileChooser.showOpenDialog(this);
    if (resultado == JFileChooser.APPROVE_OPTION) {
        String caminhoImagem = fileChooser.getSelectedFile().getAbsolutePath();
        jt_imagem.setText(caminhoImagem);

        // Preview
        ImageIcon icon = new ImageIcon(caminhoImagem);
        java.awt.Image img = icon.getImage().getScaledInstance(jPanel2.getWidth(), jPanel2.getHeight(), java.awt.Image.SCALE_SMOOTH);
        icon = new ImageIcon(img);
        jPanel2.removeAll();
        jPanel2.add(new javax.swing.JLabel(icon));
        jPanel2.revalidate();
        jPanel2.repaint();
    }
}
```

### O que faz:

1. Abre janela pra escolher arquivo
2. Filtra só imagens
3. Pega caminho da imagem
4. Coloca caminho no `jt_imagem`
5. Mostra a capa no painel `jPanel2`

❌ Erro comum: não chamar `revalidate()` e `repaint()`, aí o preview não aparece.

---

## 4️⃣ Botão "Salvar | Editar"

```java
private void btn_salvarActionPerformed(ActionEvent evt) {
    try {
        Jogo jogo = new Jogo();
        jogo.setTitulo(jt_titulo.getText());
        jogo.setPlataforma(jt_plataforma.getText());
        jogo.setPreco(Double.parseDouble(jt_preco.getText()));
        jogo.setImagemPath(jt_imagem.getText());

        JogoDAO dao = new JogoDAO();
        dao.Inserir(jogo);

        JOptionPane.showMessageDialog(this, "Jogo salvo com sucesso!");
        atualizarTabela();
    } catch (NumberFormatException e) {
        JOptionPane.showMessageDialog(this, "Preço inválido!");
    } catch(Exception e) {
        JOptionPane.showMessageDialog(this, "Erro ao salvar: " + e.getMessage());
    }
}
```

### O que faz:

1. Cria objeto Jogo
2. Pega dados do formulário
3. Salva no banco via DAO
4. Atualiza tabela

❌ Erro comum: digitar letra no campo de preço → NumberFormatException.

---

## 5️⃣ Atualizar JTable

```java
private void atualizarTabela() {
    JogoDAO dao = new JogoDAO();
    List<Jogo> lista = dao.Listar();

    DefaultTableModel model = new DefaultTableModel();
    model.addColumn("ID");
    model.addColumn("Título");
    model.addColumn("Plataforma");
    model.addColumn("Preço");
    model.addColumn("Imagem");

    for(Jogo jogo : lista){
        model.addRow(new Object[]{jogo.getId(), jogo.getTitulo(), jogo.getPlataforma(), jogo.getPreco(), jogo.getImagemPath()});
    }

    tb_info.setModel(model);

    // Oculta coluna ID
    tb_info.getColumnModel().getColumn(0).setMinWidth(0);
    tb_info.getColumnModel().getColumn(0).setMaxWidth(0);
    tb_info.getColumnModel().getColumn(0).setWidth(0);
}
```

❌ Erro comum: não atualizar a tabela depois de salvar → dados não aparecem.

---

## 6️⃣ Botão "Excluir"

```java
private void btn_excluirActionPerformed(ActionEvent evt) {
    int linha = tb_info.getSelectedRow();
    if(linha == -1){ JOptionPane.showMessageDialog(this, "Selecione um jogo!"); return; }
    int id = (int) tb_info.getValueAt(linha, 0);
    new JogoDAO().Excluir(id);
    JOptionPane.showMessageDialog(this, "Jogo excluído!");
    atualizarTabela();
}
```

### O que faz:

1. Pega linha selecionada
2. Pega ID do jogo
3. Chama DAO para excluir
4. Atualiza tabela

❌ Erro comum: esquecer de atualizar tabela ou não selecionar linha.

---

## 7️⃣ DAO — Banco de Dados

* **Inserir** → `INSERT INTO jogo (titulo,plataforma,preco,imagem_path) VALUES (?,?,?,?)`
* **Atualizar** → `UPDATE jogo SET titulo=?,plataforma=?,preco=?,imagem_path=? WHERE id=?`
* **Listar** → `SELECT * FROM jogo ORDER BY titulo`
* **Excluir** → `DELETE FROM jogo WHERE id=?`

📌 Tudo parametrizado com `PreparedStatement` → seguro e evita SQL Injection.

---

## 8️⃣ Padrão mental do CRUD

1. Formulário → preencher dados
2. DAO → mandar pro banco
3. Atualizar tabela → mostrar na tela
4. Preview → mostrar imagem no painel
5. Tratar erros (try/catch)

⚡ Dica: Sempre chame `atualizarTabela()` depois de inserir, atualizar ou excluir.

---

## ✅ Conclusão

* Java Swing + JDBC + MySQL = CRUD completo
* Preview de imagem = UX melhor
* `PreparedStatement` = seguro
* Estrutura clara: Formulário → DAO → Tabela → Preview

