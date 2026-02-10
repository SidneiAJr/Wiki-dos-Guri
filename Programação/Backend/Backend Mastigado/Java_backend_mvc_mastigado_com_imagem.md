# TelaProdutosForm.java — Comentado Parte por Parte

> Este arquivo representa a **View (Swing)** de um CRUD em padrão **MVC**, responsável apenas pela interface gráfica e pela orquestração das ações do usuário.
> Toda lógica de banco fica no **DAO** e toda regra de dados no **Model**.

---

## 📦 Package

```java
package View;
```

Define que esta classe pertence à camada **View** do projeto.

---

## 📚 Imports

```java
import dao.JogoDAO;            // DAO: comunicação com o banco (CRUD)
import java.util.List;         // List para carregar dados da tabela
import javax.swing.JOptionPane;// Caixas de diálogo (alertas, erros, sucesso)
import model.Jogo;             // Model (entidade Jogo)
import javax.swing.table.DefaultTableModel; // Modelo da JTable
import util.ImageStorage;      // Classe utilitária para salvar imagens
import java.awt.Image;         // Manipulação de imagens
import java.io.File;           // Arquivos do sistema
import javax.swing.ImageIcon;  // Ícones/imagens no Swing
import javax.swing.JFileChooser;// Janela para escolher arquivos
import javax.swing.ListSelectionModel; // Controle de seleção da JTable
```

---

## 🪟 Classe principal

```java
public class TelaProdutosForm extends javax.swing.JFrame {
```

Esta classe **herda de JFrame**, ou seja, é uma **janela Swing**.
Ela representa a **tela principal do CRUD**.

---

## 🔌 DAO e variáveis de controle

```java
private final JogoDAO dao = new JogoDAO();
```

Instância única do DAO para uso em toda a tela.
Responsável por acessar o banco de dados.

```java
private Integer idSelecionado = null;
```

Controla o estado do formulário:

* `null` → novo cadastro
* valor ≠ null → edição de um registro existente

```java
private File ImagemEscolhida;
```

Armazena temporariamente a imagem escolhida pelo usuário.
Ela **ainda não foi salva** na pasta da aplicação.

---

## 🧱 Construtor da tela

```java
public TelaProdutosForm() {
    initComponents();      // Monta a interface gráfica (NetBeans)
    configurarTabela();    // Configura seleção da JTable
    recarregarTabela();    // Carrega dados do banco
    novo();                // Inicia em modo "novo cadastro"
}
```

---

## 📊 Configuração da JTable

```java
public void configurarTabela(){
```

Define como a tabela se comporta.

```java
    tb_info.setSelectionMode(ListSelectionModel.SINGLE_SELECTION);
```

Permite selecionar **apenas uma linha por vez**.

```java
    tb_info.getSelectionModel().addListSelectionListener(e ->{
```

Listener que dispara quando o usuário seleciona uma linha.

```java
        if(!e.getValueIsAdjusting()){
```

Evita que o evento dispare duas vezes.

```java
            int row = tb_info.getSelectedRow();
```

Obtém o índice da linha selecionada.

```java
            if(row >= 0){
```

Garante que existe uma seleção válida.

```java
                int id = (int) tb_info.getModel().getValueAt(row, 0);
```

Pega o **ID do jogo** (primeira coluna da tabela).

```java
                carregarparaEdicao(id);
```

Carrega os dados do jogo selecionado no formulário.

---

## ✏️ Carregar dados para edição

```java
private void carregarparaEdicao(int id){
```

Busca o jogo no banco e preenche os campos.

```java
    Jogo j = dao.buscarPorId(id);
```

Consulta o banco pelo ID.

```java
    if(j == null) return;
```

Se não encontrar, não faz nada.

```java
    idSelecionado = j.getId();
```

Marca que agora estamos em **modo edição**.

```java
    jt_titulo.setText(j.getTitulo());
    jt_plataforma.setText(j.getPlataforma());
    jt_preco.setText(String.valueOf(j.getPreco()));
```

Preenche os campos do formulário.

```java
    jt_imagem.setText(j.getImagemPath() == null ? "Nenhuma Imagem" : j.getImagemPath());
```

Mostra o caminho da imagem (se existir).

```java
    ImagemEscolhida = null;
```

Não força o usuário a escolher imagem novamente.

```java
    Mostrarimagem(j.getImagemPath(), false);
```

Exibe a imagem já salva no banco.

---

## 🖼️ Escolher imagem

```java
private void escolherImagem(){
```

Abre o seletor de arquivos do sistema.

```java
    JFileChooser chooser = new JFileChooser();
    chooser.setDialogTitle("Escolha Nosso Jogo: ");
```

Configura a janela.

```java
    int result = chooser.showOpenDialog(this);
```

Mostra o diálogo.

```java
    if(result == JFileChooser.APPROVE_OPTION){
```

Executa apenas se o usuário confirmar.

```java
        ImagemEscolhida = chooser.getSelectedFile();
```

Armazena a imagem escolhida.

```java
        Mostrarimagem(ImagemEscolhida.getAbsolutePath(), true);
```

Mostra **pré-visualização** da imagem.

```java
        jt_imagem.setText("Será copiado ao salvar");
```

Avisa que a imagem ainda não foi salva.

---

## 💾 salvarOuAtualizar (núcleo do CRUD)

```java
private void salvarouAtualizar(){
```

Aqui entra toda a lógica de **INSERT / UPDATE**.
(Validação, criação do objeto, chamada do DAO).

> ⚠️ Se este método estiver vazio, **clicar em Salvar não faz nada**.

---

## 🖼️ Mostrar imagem no JLabel

```java
private void Mostrarimagem(String caminho, boolean preview) {
```

Responsável apenas por **exibir imagem** na tela.

```java
    if (caminho == null || caminho.isBlank()){
```

Trata ausência de imagem.

```java
    File imgFile = new File(caminho);
```

Cria referência ao arquivo.

```java
    if (!imgFile.exists()){
```

Evita erro se o arquivo não existir.

```java
    ImageIcon icon = new ImageIcon(caminho);
```

Carrega a imagem.

```java
    Image img = icon.getImage().getScaledInstance(
        lbl_capa.getWidth(), lbl_capa.getHeight(), Image.SCALE_SMOOTH);
```

Redimensiona para caber no JLabel.

```java
    lbl_capa.setIcon(new ImageIcon(img));
```

Exibe a imagem.

```java
    lbl_capa.setToolTipText(preview ? "Pré-visualização" : "Imagem salva");
```

Diferencia preview de imagem definitiva.

---

## 🔄 Recarregar tabela

```java
public void recarregarTabela(){}
```

Responsável por buscar os dados no DAO e atualizar a JTable.

---

## 🆕 Novo cadastro

```java
private void novo(){
```

Reseta o formulário para novo registro.

```java
    idSelecionado = null;
```

Sai do modo edição.

```java
    ImagemEscolhida = null;
```

Descarta imagem temporária.

```java
    jt_titulo.setText("");
    jt_preco.setText("");
    jt_plataforma.setText("");
```

Limpa os campos.

```java
    lbl_capa.setIcon(null);
    lbl_capa.setText("Selecione um Item:");
```

Limpa a imagem exibida.

```java
    tb_info.clearSelection();
```

Remove seleção da tabela.

---

