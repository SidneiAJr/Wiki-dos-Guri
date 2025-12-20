# 🧠 SQL Avançado — Consultas, Procedures e Otimização

## ⚙️ 1️⃣ JOINS AVANÇADOS
```SQL
🔸 INNER JOIN — junção de registros correspondentes
SELECT 
    p.nome_personagem,
    e.nome_especie,
    h.nome_habilidade,
    a.nome_arma
FROM caracteristica_personagem cp
INNER JOIN personagem p ON cp.id_personagem = p.id_personagem
INNER JOIN especie e ON cp.id_especie = e.id_especie
INNER JOIN habilidade h ON cp.id_habilidade = h.id_habilidade
INNER JOIN armas a ON cp.id_arma = a.id_arma;
```

## LEFT JOIN — mantém todos os registros da esquerda
```SQL
SELECT 
    p.nome_personagem,
    h.nome_habilidade
FROM personagem p
LEFT JOIN caracteristica_personagem cp ON p.id_personagem = cp.id_personagem
LEFT JOIN habilidade h ON cp.id_habilidade = h.id_habilidade;
```

## RIGHT JOIN — mantém todos os registros da direita
```SQL
SELECT 
    e.nome_especie,
    p.nome_personagem
FROM especie e
RIGHT JOIN caracteristica_personagem cp ON e.id_especie = cp.id_especie
RIGHT JOIN personagem p ON cp.id_personagem = p.id_personagem;
```
