# 🧩 Includes e Requires no PHP

O PHP permite **importar arquivos externos** dentro do código, o que ajuda a **reaproveitar código** e **organizar melhor o projeto**.

---

## 📥 `include`

O comando `include` insere o conteúdo de outro arquivo PHP.  
Se o arquivo **não for encontrado**, o PHP mostra apenas um **aviso**, mas **continua executando o script**.

```php
include 'header.php';
echo "Conteúdo principal";
include 'footer.php';
```

## 📥 `require`

O comando require também insere o conteúdo de outro arquivo,
mas se o arquivo não existir, o PHP interrompe completamente a execução do script.

```php
require 'config.php';
echo "Esse texto nunca será exibido se config.php não existir.";
```

### ♻️ `Versões com _once`

Tanto include quanto require têm versões que garantem que o arquivo seja incluído apenas uma vez,
evitando erros de redefinição de funções ou variáveis.

```php
include_once 'funcoes.php';
require_once 'conexao.php';
```

## 🧱 Diferenças principais:

| Função         | Continua se der erro? | Inclui uma vez só? |
| -------------- | --------------------- | ------------------ |
| `include`      | ✅ Sim                 | ❌ Não              |
| `include_once` | ✅ Sim                 | ✅ Sim              |
| `require`      | ❌ Não                 | ❌ Não              |
| `require_once` | ❌ Não                 | ✅ Sim              |
