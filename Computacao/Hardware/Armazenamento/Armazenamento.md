# Armazenamento (HDD, SSD, NVMe)

O armazenamento é responsável por manter os dados **de forma permanente** (mesmo sem energia).

---

## Tipos principais

| Tipo | Exemplo | Vantagem | Desvantagem |
|------|----------|-----------|-------------|
| HDD (mecânico) | 5400/7200 RPM | Barato e maior capacidade | Lento |
| SSD SATA | 2.5" | Muito mais rápido que HDD | Limitado pela interface SATA |
| SSD NVMe (M.2) | PCIe x4 | Extremamente rápido | Mais caro |
| SSHD (Híbrido) | HDD + Cache SSD | Leitura mais rápida que HDD | Ainda lento comparado ao SSD |

---

## Velocidade (comparação)

| Tipo | Velocidade média |
|------|------------------|
| HDD | ~100 MB/s |
| SSD SATA | ~550 MB/s |
| SSD NVMe Gen3 | ~3500 MB/s |
| SSD NVMe Gen4 | ~7000 MB/s |

---

## Interfaces

| Interface | Uso | Velocidade |
|----------|-----|-------------|
| SATA III | HDD / SSD SATA | Até 600 MB/s |
| PCIe 3.0 x4 | NVMe | Até ~3500 MB/s |
| PCIe 4.0 x4 | NVMe | Até ~7000 MB/s |

---

## Quando escolher cada um?

| Situação | Recomendação |
|----------|--------------|
| PC simples / barato | HDD + SSD pequeno |
| Jogos | SSD SATA ou NVMe |
| Alta performance | NVMe |
| Servidor / banco de dados | NVMe Gen4 |

---

## Resumo

- HDD = capacidade
- SSD = velocidade
- NVMe = alto desempenho
