## 🚀 7️⃣ ÍNDICES (Otimização)
```SQL
Índices aceleram buscas, especialmente em colunas usadas com WHERE ou JOIN.

CREATE INDEX idx_nome_personagem ON personagem(nome_personagem);
CREATE INDEX idx_habilidade_nome ON habilidade(nome_habilidade);
```

## 🔒 8️⃣ TRANSAÇÕES
```SQL
Permitem executar várias operações juntas com segurança.

START TRANSACTION;

INSERT INTO personagem (nome_personagem, idade) VALUES ('Rhaegor', 420);
UPDATE personagem SET idade = 421 WHERE nome_personagem = 'Rhaegor';

COMMIT;   -- Confirma as operações
-- ROLLBACK; -- Cancela se algo der errado
```