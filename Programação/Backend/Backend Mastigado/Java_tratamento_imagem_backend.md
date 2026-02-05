# 🧠 Explicação do código (ImageStorage - Java)

Esse código cria uma **classe utilitária em Java** para armazenar imagens em uma pasta local, garantindo que cada imagem tenha um **nome único baseado na data e hora**.

---

## 📦 Imports (bibliotecas usadas)

```java
import java.io.File;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.StandardCopyOption;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
```

* **java.io.File** → manipulação de arquivos e pastas
* **java.nio.file.Files** → operações com arquivos (copiar, mover, deletar)
* **java.nio.file.Path** → representa caminhos de arquivos
* **java.nio.file.StandardCopyOption** → define opções ao copiar arquivos
* **java.time.LocalDateTime** → data e hora atual
* **java.time.format.DateTimeFormatter** → formata data e hora em string

---

## 📂 Pasta de armazenamento

```java
private static final String PASTA_IMAGEM = "imagens";
```

* Define a pasta onde as imagens serão salvas
* Se a pasta não existir, será criada automaticamente

---

## 💾 Método salvarImagem

```java
public static String salvarImagem(File arquivo) {
    File pasta = new File(PASTA_IMAGEM);
    if (!pasta.exists()) {
        pasta.mkdir();
    }

    String nomeArquivo = gerarNomeArquivo(arquivo);
    Path caminhoDestino = Path.of(PASTA_IMAGEM, nomeArquivo);

    try {
        Files.copy(arquivo.toPath(), caminhoDestino, StandardCopyOption.REPLACE_EXISTING);
        return caminhoDestino.toString();
    } catch (IOException e) {
        throw new RuntimeException("Erro ao salvar a imagem: " + e.getMessage(), e);
    }
}
```

* Cria a pasta se não existir
* Gera um **nome único** para o arquivo
* Copia o arquivo para a pasta definida
* Retorna o **caminho completo** do arquivo salvo
* Lança uma exceção em caso de erro

---

## 📝 Método gerarNomeArquivo

```java
private static String gerarNomeArquivo(File arquivo) {
    String extensao = arquivo.getName().substring(arquivo.getName().lastIndexOf("."));
    String timestamp = LocalDateTime.now().format(DateTimeFormatter.ofPattern("yyyyMMddHHmmssSSS"));
    return "imagem_" + timestamp + extensao;
}
```

* Extrai a **extensão do arquivo** (ex: .jpg, .png)
* Gera um **timestamp único** (ano, mês, dia, hora, minuto, segundo, milissegundo)
* Combina timestamp e extensão para criar um **nome de arquivo único**

---


