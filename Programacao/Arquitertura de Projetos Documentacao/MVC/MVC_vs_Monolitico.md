# 🧱 Monolítico vs MVC

## O que é uma aplicação Monolítica?

Uma aplicação **monolítica** é aquela onde **tudo fica misturado** ou **centralizado** em um único bloco.

Normalmente:
- Regras de negócio
- Acesso ao banco
- HTML / resposta
- Controle de fluxo

ficam no **mesmo lugar** ou no mesmo arquivo.

---

## 🧨 Exemplo de Monolítico (PHP)

```php
<?php
// tudo misturado

$conn = new PDO(...);

if ($_POST) {
    $sql = "INSERT INTO users VALUES (...)";
    $conn->query($sql);
    echo "Usuário cadastrado";
}
```
## 📌 Aqui:
* Banco
* Regra
* Controle
* Saída
* estão todos juntos.

## O que é MVC?
* MVC é um padrão de organização.
* Ele separa responsabilidades em camadas claras:
* Model → dados e regras
* View → apresentação
* Controller → controle do fluxo

## 🧠 MVC resolve o quê?
* ✔️ Organização
* ✔️ Código legível
* ✔️ Manutenção fácil
* ✔️ Crescimento controlado
* ✔️ Menos acoplamento

## Comparação Direta

| Monolítico         | MVC                         |
| ------------------ | --------------------------- |
| Tudo misturado     | Responsabilidades separadas |
| Arquivo gigante    | Arquivos pequenos           |
| Difícil manutenção | Fácil manutenção            |
| Pouca reutilização | Alta reutilização           |
| Escala mal         | Escala melhor               |
