# 🔤 Strings em PHP – Básico e Avançado

As strings em PHP representam textos.  
PHP possui dezenas de funções nativas para manipulação, transformação e análise de strings.

---

# ⭐ 1. Tipos de Strings

## 🔹 Aspas simples
Interpretam o texto literalmente.  
Não interpretam variáveis.

```php
$nome = 'João';
```

## Aspas duplas
```php
$nome = "João";
$frase = "Olá, $nome!";
```

## Heredoc
```php
$text = <<<TXT
Texto grande com $variavel
TXT;
```

## Nowdoc
```php
$text = <<<'TXT'
Texto literal sem variáveis
TXT;
```

# 2. Funções Básicas de Strings

## strlen():
```php
echo strlen("Olá mundo");
```
## strtoupper() / strtolower()
```php
echo strtoupper("php");
```
## ucfirst() / ucwords()
```php
echo ucwords("curso de php");
```
## trim() / ltrim() / rtrim()

```php
echo trim("   teste   ");
```

## substr()
```php
echo substr("Hello World", 0, 5);
```

## str_replace()
```php
echo str_replace("carro", "moto", "Eu tenho um carro");
```

## strpos()
```php
echo strpos("programação PHP", "PHP");
```

# 4. Comparação de Strings

## strcmp()
```php
echo strcmp("a", "A");
```

## explode()

```php
$partes = explode(",", "a,b,c,d");
```

## implode()

```php
echo implode(" - ", ["a","b","c"]);
```

```php
preg_match("/^[0-9]+$/", "12345");
```

## strip_tags()
```php
echo strip_tags("<h1>Olá</h1>");
```

## htmlspecialchars()
```php
echo htmlspecialchars("<script>alert(1)</script>");
```

## Multibyte (UTF-8)
```php
echo mb_strlen("ação");
echo mb_strtoupper("ação");
```



