# 📁 PHP | Upload Seguro de Arquivos

O upload de arquivos é uma das partes mais perigosas de qualquer aplicação web.
Se não for bem feito, permite envio de arquivos maliciosos, execução remota e invasões.

Abaixo está um guia completo e padronizado para fazer upload de forma segura.

````php
<?php

// Pasta onde os arquivos serão salvos
$diretorio = "uploads/";

// Verifica se o formulário foi enviado
if ($_SERVER["REQUEST_METHOD"] === "POST") {

    // Verifica se existe arquivo enviado
    if (isset($_FILES['arquivo']) && $_FILES['arquivo']['error'] === 0) {

        $arquivo = $_FILES['arquivo'];

        // ============================
        // 1) Proteger tamanho do arquivo (max 2MB)
        // ============================
        $tamanhoMaximo = 2 * 1024 * 1024; // 2MB
        if ($arquivo['size'] > $tamanhoMaximo) {
            die("Arquivo muito grande! Máximo permitido: 2MB");
        }

        // ============================
        // 2) Restrição de extensões permitidas
        // ============================
        $extensoesPermitidas = ['jpg', 'jpeg', 'png', 'pdf'];
        $extensao = strtolower(pathinfo($arquivo['name'], PATHINFO_EXTENSION));

        if (!in_array($extensao, $extensoesPermitidas)) {
            die("Tipo de arquivo não permitido!");
        }

        // ============================
        // 3) Verificação real do tipo MIME
        // ============================
        $finfo = finfo_open(FILEINFO_MIME_TYPE);
        $mimeReal = finfo_file($finfo, $arquivo['tmp_name']);
        finfo_close($finfo);

        $mimesPermitidos = [
            "image/jpeg",
            "image/png",
            "application/pdf"
        ];

        if (!in_array($mimeReal, $mimesPermitidos)) {
            die("Arquivo inválido ou adulterado!");
        }

        // ============================
        // 4) Geração de nome único
        // ============================
        $novoNome = uniqid("file_", true) . "." . $extensao;

        // ============================
        // 5) Movendo arquivo de forma segura
        // ============================
        if (move_uploaded_file($arquivo['tmp_name'], $diretorio . $novoNome)) {
            echo "Upload realizado com sucesso!";
        } else {
            echo "Erro ao mover o arquivo!";
        }

    } else {
        echo "Nenhum arquivo enviado!";
    }
}
?>
````
## 📤 📑 Formulário HTML para Upload
```html
<form action="" method="POST" enctype="multipart/form-data">
    <label for="arquivo">Selecione um arquivo:</label>
    <input type="file" name="arquivo" id="arquivo" required>
    <button type="submit">Enviar</button>
</form>
````

| Regra                                         | Por quê?                                         |
| --------------------------------------------- | ------------------------------------------------ |
| **Nunca confiar no nome/extensão do arquivo** | O usuário pode renomear um `.exe` para `.png`.   |
| **Verificar MIME real com `finfo`**           | Confirma o verdadeiro tipo do arquivo.           |
| **Limitador de tamanho**                      | Evita DoS enviando arquivos enormes.             |
| **Criar novo nome para o arquivo**            | Evita sobrescrever arquivos existentes.          |
| **Salvar arquivos fora da pasta pública**     | Impede execução remota.                          |
| **Bloquear `.php` e scripts**                 | Evita que o atacante envie código para executar. |
