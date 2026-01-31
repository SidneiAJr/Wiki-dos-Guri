# 🕓 Trabalhando com Datas e Horas em PHP

O PHP oferece várias formas de lidar com **datas e horários**, seja para exibir a data atual, calcular intervalos ou formatar valores.

---

## 📅 Função `date()`

A função `date()` retorna a data/hora atual formatada.

```php
echo date("d/m/Y"); // Exemplo: 27/10/2025
echo date("H:i:s"); // Exemplo: 19:45:22
```

📘 Formatos comuns:
| Código | Significado     | Exemplo |
| ------ | --------------- | ------- |
| `d`    | Dia (2 dígitos) | `27`    |
| `m`    | Mês (2 dígitos) | `10`    |
| `Y`    | Ano completo    | `2025`  |
| `H`    | Hora (24h)      | `19`    |
| `i`    | Minuto          | `45`    |
| `s`    | Segundo         | `22`    |
