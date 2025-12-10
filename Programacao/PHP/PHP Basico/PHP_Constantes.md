# PHP – Constantes

Constantes são valores que **não podem ser alterados** depois de definidos.

---

## 🧱 Criando Constantes

### ✔ Usando define()

```php
define("PI", 3.14);
echo PI;

const TAXA = 0.2;
echo TAXA;
```

## Diferenças entre const e define()

| Característica                    | const | define() |
| --------------------------------- | ----- | -------- |
| Pode ser usada dentro de classes? | ✔     | ❌        |
| Avaliada em tempo de compilação   | ✔     | ❌        |
| Aceita expressões complexas       | ❌     | ✔        |
| Escopo                            | fixo  | global   |

## Constantes Mágicas do PHP

| Constante       | Descrição                   |
| --------------- | --------------------------- |
| `__FILE__`      | caminho completo do arquivo |
| `__DIR__`       | diretório atual             |
| `__LINE__`      | linha atual                 |
| `__FUNCTION__`  | nome da função              |
| `__CLASS__`     | nome da classe              |
| `__METHOD__`    | método atual                |
| `__TRAIT__`     | trait atual                 |
| `__NAMESPACE__` | namespace atual             |

