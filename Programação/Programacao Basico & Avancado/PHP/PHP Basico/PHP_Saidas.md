# PHP | Saídas: `print` e `echo`

Em PHP temos duas construções principais para exibir dados na tela: **`echo`** e **`print`**.
Ambas servem para saída de texto, porém possuem diferenças importantes.

---

## 🔹 `echo`

`echo` é a forma mais comum e rápida de imprimir algo no PHP.

### ✔ Características:

* Pode **exibir múltiplos valores** ao mesmo tempo
* **Não retorna valor**
* É **mais rápido** que `print`
* É uma **construção da linguagem**, não uma função

### 🔸 Exemplo:

```php
echo "Olá mundo!";
echo "Meu nome é ", "PHP ", 8, ".0!";
```

---

## 🔹 `print`

`print` funciona de forma parecida, mas possui algumas diferenças.

### ✔ Características:

* **Retorna o valor `1`**, permitindo ser usado em expressões
* **Exibe apenas um valor por vez**
* É um pouco mais **lento** que `echo` (diferença mínima)
* Também é uma **construção da linguagem**

### 🔸 Exemplo:

```php
print "Olá mundo!";
$teste = print "Imprimindo com print";
echo $teste; // retorna 1
```

---

## 🔥 Diferenças principais

| Característica              | echo                  | print                |
| --------------------------- | --------------------- | -------------------- |
| Aceita múltiplos argumentos | ✔ Sim                 | ❌ Não                |
| Retorna valor               | ❌ Não                 | ✔ Sim (retorna 1)    |
| Velocidade                  | Levemente mais rápido | Levemente mais lento |
| Uso comum                   | Muito usado           | Menos comum          |

---

## 📌 Conclusão

Na maioria dos casos, **`echo` é a melhor escolha**, por ser simples e flexível.
`print` é útil apenas quando você precisa que a instrução **retorne um valor**.

---

Se quiser adicionar exemplos práticos ou exercícios, posso criar também!
