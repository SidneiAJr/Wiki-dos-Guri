# PHP | Saídas Alternativas

Além das instruções básicas `echo` e `print`, o PHP possui diversas outras formas de saída — seja para debug, formatação, controle de buffer ou até envio de arquivos.
Este documento reúne todas as principais alternativas.

---

## 🔹 1. Saídas para Debug

### **`print_r()`**

Exibe variáveis, arrays e objetos de forma legível.

```php
print_r($array);
```

---

### **`var_dump()`**

Mostra tipo, tamanho e estrutura da variável.
É a forma mais completa de debug.

```php
var_dump($dados);
```

---

### **`var_export()`**

Exibe a variável em formato de **código PHP válido**.

```php
var_export($objeto);
```

---

## 🔹 2. Saídas com Formatação

### **`printf()`**

Imprime texto formatado (modelo estilo C).

```php
printf("Nome: %s | Idade: %d anos", $nome, $idade);
```

---

### **`sprintf()`**

Mesma formatação do `printf()`, porém **retorna a string ao invés de imprimir**.

```php
$mensagem = sprintf("Preço: R$ %.2f", 19.90);
echo $mensagem;
```

---

## 🔹 3. Saída Direta de Arquivos

### **`readfile()`**

Lê e envia o conteúdo de um arquivo diretamente ao navegador.

```php
readfile("texto.txt");
```

---

### **`fpassthru()`**

Lê o restante de um arquivo já aberto e envia para saída.

```php
$fp = fopen("log.txt", "r");
fpassthru($fp);
fclose($fp);
```

---

## 🔹 4. Saída Controlada (Output Buffering)

O PHP permite controlar o envio de conteúdo usando buffers.

### **`ob_start()`**

Inicia o buffer de saída.

```php
ob_start();
echo "Isso ficará no buffer";
```

---

### **`ob_get_clean()`**

Pega o conteúdo do buffer **e limpa**.

```php
$dados = ob_get_clean();
```

---

### **`flush()` / `ob_flush()`**

Força o envio do conteúdo ao navegador.

---

## 🔹 5. Saída e Encerramento do Script

### **`die()`**

Exibe uma mensagem e encerra imediatamente o script.

```php
die("Erro fatal!");
```

---

### **`exit()`**

Funciona como `die()` — pode exibir uma string antes de encerrar.

```php
exit("Encerrando execução...");
```

---

## ✔ Resumo Geral

| Categoria       | Funções                                                 |
| --------------- | ------------------------------------------------------- |
| Debug           | `print_r()`, `var_dump()`, `var_export()`               |
| Formatação      | `printf()`, `sprintf()`                                 |
| Arquivos        | `readfile()`, `fpassthru()`                             |
| Buffer          | `ob_start()`, `ob_get_clean()`, `flush()`, `ob_flush()` |
| Encerrar script | `die()`, `exit()`                                       |

---

Se quiser, posso criar também o **arquivo de Saídas Básicas (echo e print)** com o mesmo estilo para combinar com esse.
Quer? 😎
