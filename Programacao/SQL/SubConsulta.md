# 🧠 SQL Avançado — Consultas, Procedures e Otimização

## 🧩 2️⃣ SUBCONSULTAS (Subqueries)
```SQL
🔹 Exemplo: encontrar personagens com mais de 100 anos que têm habilidades mágicas
SELECT nome_personagem
FROM personagem
WHERE idade > 100
AND id_personagem IN (
    SELECT id_personagem
    FROM caracteristica_personagem
    WHERE id_habilidade IN (
        SELECT id_habilidade FROM habilidade WHERE nome_habilidade LIKE '%Fogo%' OR nome_habilidade LIKE '%Morte%'
    )
);
```

## 🧩 10️⃣ Exemplo Avançado — Relatório Completo
```SQL
SELECT 
    p.nome_personagem AS "Personagem",
    e.nome_especie AS "Espécie",
    h.nome_habilidade AS "Habilidade",
    a.nome_arma AS "Arma",
    CASE 
        WHEN p.idade > 300 THEN 'Antigo'
        WHEN p.idade BETWEEN 100 AND 300 THEN 'Veterano'
        ELSE 'Jovem'
    END AS "Classificação de Idade"
FROM caracteristica_personagem cp
JOIN personagem p ON cp.id_personagem = p.id_personagem
JOIN especie e ON cp.id_especie = e.id_especie
JOIN habilidade h ON cp.id_habilidade = h.id_habilidade
JOIN armas a ON cp.id_arma = a.id_arma
ORDER BY p.idade DESC;
```
