# 📁 ImageStorage.java

## Utilitário Java para armazenamento de imagens

Este arquivo define uma **classe utilitária** responsável por salvar imagens no sistema de arquivos, garantindo:

* Organização em uma pasta específica
* Nome de arquivo único
* Uso das APIs modernas do Java (`java.nio` e `java.time`)

Abaixo está a explicação **desmembrada**, clara e didática de cada parte do código.

---

## 📦 Pacote

O arquivo pertence ao pacote `util`.

👉 Isso indica que a classe foi pensada como uma **ferramenta reutilizável**, não como regra de negócio.

---

## 📥 Imports

Aqui são importadas todas as classes necessárias para o funcionamento:

* `File` → representa arquivos e diretórios no sistema
* `IOException` → trata erros de entrada e saída
* `Files` → utilitário moderno para operações com arquivos
* `Path` → representa caminhos de forma mais segura que `File`
* `StandardCopyOption` → define comportamento ao copiar arquivos
* `LocalDateTime` → obtém data e hora atuais
* `DateTimeFormatter` → formata data e hora como texto

👉 Esse conjunto mostra que o código está usando **boas APIs do Java moderno**.

---

## 🧱 Classe ImageStorage

A classe `ImageStorage` é uma **classe utilitária**:

* Não possui atributos de instância
* Todos os métodos são `static`

👉 Ideal para ser chamada diretamente sem precisar criar objeto.

---

## 📂 Constante da pasta de imagens

`PASTA_IMAGEM` define o nome do diretório onde as imagens serão armazenadas.

Por ser `static final`, ela:

* Não muda durante a execução
* Evita strings mágicas espalhadas pelo código
* Facilita manutenção futura

---

## 💾 Método salvarImagem(File arquivo)

Esse é o **método principal** da classe.

### Responsabilidade:

* Receber um arquivo de imagem
* Criar a pasta se necessário
* Gerar um nome único
* Copiar o arquivo
* Retornar o caminho salvo

👉 Ele resolve tudo em um único ponto, mantendo o código limpo.

---

## 📁 Criação da pasta

O código cria um objeto `File` representando a pasta de imagens.

Depois verifica:

* Se a pasta **não existir**, ela é criada automaticamente

👉 Isso evita erro comum de tentar salvar arquivo em pasta inexistente.

---

## 🏷️ Geração do nome do arquivo

O método chama `gerarNomeArquivo(arquivo)` para criar um nome único.

Isso garante:

* Nenhuma sobrescrita acidental
* Organização por data e hora

---

## 📍 Definição do caminho de destino

O caminho final é montado usando `Path.of()`:

* Nome da pasta
* Nome único do arquivo

👉 `Path` é mais seguro e moderno que trabalhar só com `String`.

---

## 📤 Cópia do arquivo

A imagem é copiada usando `Files.copy()`.

Com a opção:

* `REPLACE_EXISTING` → substitui caso exista um arquivo com o mesmo nome

👉 Mesmo sendo raro, isso evita exceções inesperadas.

---

## ❌ Tratamento de erro

Caso ocorra um problema:

* A exceção `IOException` é capturada
* É lançada uma `RuntimeException` com mensagem clara

👉 Facilita debug e não engole o erro silenciosamente.

---

## 🧬 Método gerarNomeArquivo(File arquivo)

Método privado auxiliar.

### O que ele faz:

1. Extrai a extensão do arquivo original
2. Gera um timestamp com data e hora atual
3. Junta tudo em um nome único

Exemplo de nome gerado:

`imagem_20260205113745982.png`

👉 Isso evita conflitos e mantém padrão.

---

## ✅ Conclusão

Esse utilitário:

* É simples
* É reutilizável
* Segue boas práticas
* Usa APIs modernas

Perfeito para:

* Upload de imagens
* Sistemas web
* Projetos educacionais
* APIs REST

Se quiser, dá pra evoluir isso facilmente com:

* Validação de tipo de imagem
* Limite de tamanho
* Subpastas por data
* UUID no nome do arquivo

🔥 Código limpo, didático e com cara de projeto bem pensado.
