## ⚡ 3️⃣ FUNÇÕES DE AGREGAÇÃO
```SQL
SELECT 
    e.nome_especie,
    COUNT(p.id_personagem) AS total_personagens,
    AVG(p.idade) AS idade_media
FROM personagem p
JOIN caracteristica_personagem cp ON cp.id_personagem = p.id_personagem
JOIN especie e ON e.id_especie = cp.id_especie
GROUP BY e.nome_especie
ORDER BY total_personagens DESC;

```
