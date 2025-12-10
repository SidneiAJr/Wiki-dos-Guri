# Evolução dos Tipos de Conexão de Placas de Vídeo (Barramentos)

As placas de vídeo evoluíram junto com os barramentos da placa-mãe. Cada geração aumentou a largura de banda disponível, permitindo gráficos mais complexos e maior desempenho.

---

## 🔹 1. ISA (Década de 80 / início dos 90)

| Característica | Informação |
|---------------|------------|
| Ano | ~1984 |
| Velocidade | Muito baixa |
| Conector | Preto (longo) |
| Observação | Usado em PCs XT/AT, pré-VGA |

> Era usada para placas CGA e EGA antes do VGA se popularizar.

---

## 🔹 2. PCI (1993)

| Característica | Informação |
|---------------|------------|
| Ano | 1993 |
| Velocidade | Até 133 MB/s |
| Uso | Primeiras placas VGA aceleradas |
| Observação | Ainda compartilhava banda com outros dispositivos |

---

## 🔹 3. AGP (Accelerated Graphics Port) – 1997

| Característica | Informação |
|---------------|------------|
| Ano | 1997 |
| Velocidade | 266 MB/s a 2133 MB/s (AGP 1x até 8x) |
| Exclusividade | Canal dedicado para GPU |
| Observação | Pioneiro no salto de desempenho 3D (GeForce / Radeon antigas) |

> Esse barramento foi o primeiro projetado **exclusivamente** para vídeo.

---

## 🔹 4. PCI Express (PCIe) – 2004 em diante

O PCIe substituiu o AGP e se tornou o padrão atual. Ele usa “lanes” (faixas de transmissão) como x1, x4, x8 e **x16** (usado pelas GPUs).

| Geração | Ano | Velocidade por lane | x16 total | Observação |
|---------|------|----------------------|------------|-------------|
| PCIe 1.0 | 2004 | 250 MB/s | 4 GB/s | Primeiras GPUs PCIe |
| PCIe 2.0 | 2007 | 500 MB/s | 8 GB/s | Popular com séries GeForce 200/400 |
| PCIe 3.0 | 2010 | ~1 GB/s | 16 GB/s | Muito usado até hoje |
| PCIe 4.0 | 2017 | ~2 GB/s | 32 GB/s | Melhor para NVMe e GPUs novas |
| PCIe 5.0 | 2021 | ~4 GB/s | 64 GB/s | Topo atual em GPUs e SSDs |
| (PCIe 6.0)* | Futuro | ~8 GB/s | ~128 GB/s | Previsto para uso em servidores |

---

## Diferença visual entre AGP e PCIe

| AGP | PCIe |
|------|-------|
| Slot único, mais curto que PCIe, maioria cor marrom | Slot normalmente preto, x16 é maior e mais usado |
| Tecnologia antiga | Padrão atual |

---

## Quando ocorreu a troca?

| Antigo | Novo | Transição aproximada |
|--------|------|----------------------|
| AGP | PCIe 1.0 | ~2004–2006 |
| PCIe 2.0 | PCIe 3.0 | ~2010–2013 |
| PCIe 3.0 | PCIe 4.0 | ~2019 |
| PCIe 4.0 | PCIe 5.0 | ~2021 |

---

## Resumo final

| Era | Barramento | Observação |
|------|------------|-------------|
| Anos 80/90 | ISA / PCI | Muito limitados |
| 1997–2005 | AGP | Primeiro dedicado a GPU |
| 2004–atual | PCIe | Escalável e extremamente rápido |
| Futuro | PCIe 6.0 | Data centers e IA |

---

## Conclusão

A evolução do barramento gráfico foi essencial para que as GPUs acompanhassem a demanda crescente por jogos, renderização e IA. Hoje, quase todos os avanços em vídeo dependem da evolução do PCIe.

