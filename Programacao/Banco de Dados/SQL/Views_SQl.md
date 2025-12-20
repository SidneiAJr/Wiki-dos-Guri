## 🧱 5️⃣ VIEWS (Visões)
```SQL
Criam consultas salvas que funcionam como tabelas virtuais.

CREATE VIEW vw_personagens_completos AS
SELECT 
    p.nome_personagem,
    p.idade,
    e.nome_especie,
    h.nome_habilidade,
    a.nome_arma
FROM caracteristica_personagem cp
JOIN personagem p ON cp.id_personagem = p.id_personagem
JOIN especie e ON cp.id_especie = e.id_especie
JOIN habilidade h ON cp.id_habilidade = h.id_habilidade
JOIN armas a ON cp.id_arma = a.id_arma;
```
