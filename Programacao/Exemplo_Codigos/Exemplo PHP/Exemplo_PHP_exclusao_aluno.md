# 🗑️ Exclusão de Alunos via PHP (GET + MySQL + Queries Seguras)

Este script em PHP recebe um **ID pela URL**, verifica se o aluno existe no banco e, caso exista, realiza sua exclusão de forma **segura**, utilizando **prepared statements** para evitar SQL Injection.

---

## 📌 O que o script faz?

1. Recebe o parâmetro `cod` pela URL:

2. Valida:
- Se o parâmetro existe  
- Se é numérico  

3. Conecta ao banco de dados

4. Consulta se o aluno existe

5. Se existir → exclui com segurança (usando *prepared statements*)

6. Retorna mensagens claras ao usuário

---

## 🧩 Código Principal

```php
<?php
// Recebe o parâmetro 'cod' da URL via GET
$idaluno = $_GET["cod"] ?? null;

// Verifica se o parâmetro foi enviado
if (!isset($idaluno)) {
    die("Aluno não informado!");
}

// Verifica se o parâmetro é numérico
if (!is_numeric($idaluno)) {
    die("Parâmetro inválido!");
}

// Inclui arquivo de conexão
require "conexao.php";

// 1️⃣ Verifica se o aluno existe antes de excluir
$sql = $conexao->prepare("SELECT * FROM alunos WHERE id = ?");
$sql->bind_param("i", $idaluno);
$sql->execute();
$result = $sql->get_result();

// Se não existir, exibe mensagem
if ($result->num_rows === 0) {
    echo "Aluno não localizado!";
    exit;
}

// 2️⃣ Deleta o aluno usando query preparada (segura)
$delete = $conexao->prepare("DELETE FROM alunos WHERE id = ?");
$delete->bind_param("i", $idaluno);

if ($delete->execute()) {
    echo "Aluno excluído com sucesso!";
} else {
    echo "Erro ao excluir aluno!";
}

// Fecha a conexão
$conexao->close();
?>
```
