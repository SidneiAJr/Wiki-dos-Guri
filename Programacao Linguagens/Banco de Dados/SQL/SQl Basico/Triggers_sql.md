## ⚠️ 6️⃣ TRIGGERS (Gatilhos)
```SQL
Executam comandos automaticamente após eventos como INSERT, UPDATE, DELETE.

Exemplo: registrar log de inserções em personagem
CREATE TABLE log_insercoes (
    id_log INT AUTO_INCREMENT PRIMARY KEY,
    nome_personagem VARCHAR(100),
    data_insercao DATETIME DEFAULT CURRENT_TIMESTAMP
);

DELIMITER $$

CREATE TRIGGER trg_log_personagem
AFTER INSERT ON personagem
FOR EACH ROW
BEGIN
    INSERT INTO log_insercoes (nome_personagem)
    VALUES (NEW.nome_personagem);
END $$

DELIMITER ;
```
