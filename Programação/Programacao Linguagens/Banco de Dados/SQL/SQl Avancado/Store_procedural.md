## 🔁 4️⃣ STORED PROCEDURES (Procedimentos armazenados)
```SQL
Automatizam tarefas no banco, como inserções e atualizações.

DELIMITER $$

CREATE PROCEDURE AdicionarPersonagem(
    IN nome VARCHAR(100),
    IN idade INT,
    IN especie INT,
    IN habilidade INT,
    IN arma INT
)
BEGIN
    INSERT INTO personagem (nome_personagem, idade)
    VALUES (nome, idade);

    INSERT INTO caracteristica_personagem (id_especie, id_personagem, id_habilidade, id_arma)
    VALUES (especie, LAST_INSERT_ID(), habilidade, arma);
END $$

DELIMITER ;
```
