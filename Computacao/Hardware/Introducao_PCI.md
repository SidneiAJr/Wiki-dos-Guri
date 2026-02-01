# Evolução do PCI e PCI Express (PCIe 1.0 até PCIe 6.0)

O barramento PCI/PCIe é responsável pela comunicação de dispositivos de alta velocidade com a placa-mãe, como placas de vídeo, SSDs NVMe, placas de captura, controladoras etc. Ele evoluiu muito ao longo do tempo, principalmente em largura de banda e eficiência.

---

## 1️⃣ PCI (Paralelo) — Antes do PCIe

| Tecnologia | Ano | Tipo | Largura | Observação |
|------------|-----|------|---------|-------------|
| **PCI** | 1992 | Paralelo | 32 bits / 66 MHz | Usado para placas antigas de som, rede, vídeo básico |
| **PCI-X** | 1998 | Paralelo | 64 bits / 133 MHz | Voltado para servidores (mais rápido) |

🔹 **Limitação**: barramento paralelo → ruído elétrico e pouca escalabilidade  
🔹 A evolução exigia algo **serial e mais eficiente = PCI Express**

---

## 2️⃣ PCI Express — Evolução por Gerações

| Geração | Ano | Velocidade por lane (x1) | x16 (total) | Observações |
|--------|------|---------------------------|------------|-------------|
| **PCIe 1.0** | 2003 | 250 MB/s | 4 GB/s | Estreia do PCI Express |
| **PCIe 2.0** | 2007 | 500 MB/s | 8 GB/s | Dobrou a banda |
| **PCIe 3.0** | 2010 | ~1 GB/s (985 MB/s) | ~16 GB/s | Grande salto, usado até hoje |
| **PCIe 4.0** | 2017 | 2 GB/s | 32 GB/s | Começou no Ryzen 3000 |
| **PCIe 5.0** | 2021 | 4 GB/s | 64 GB/s | SSDs ultra rápidos e GPUs topo |
| **PCIe 6.0** | 2022/23 | 8 GB/s | 128 GB/s | Uso futuro: servidores / IA |

---

## 3️⃣ Retrocompatibilidade

| Slot físico | Placa suportada? |
|-------------|------------------|
| PCIe 4.0 suporta PCIe 3.0? | ✅ Sim |
| PCIe 3.0 suporta PCIe 4.0? | ✅ Sim (mas limita a 3.0) |
| PCIe 5.0 suporta todas anteriores? | ✅ Sim |
| PCI/PCI-X em PCIe? | ❌ Não |

> As gerações são **backward compatible** (compatibilidade reversa), mas a velocidade é limitada pela **menor geração**.

---

## 4️⃣ Diferença entre tamanhos (x1 / x4 / x8 / x16)

| Tamanho | Uso comum |
|---------|-----------|
| x1 | Placa de rede, Wi-Fi, USB extra |
| x4 | SSD NVMe (adaptador) |
| x8 | Algumas GPUs / Workstations |
| x16 | GPUs modernas |

---

## 5️⃣ Relação Prática (PCIe 3.0 vs 4.0 vs 5.0)

| Comparação | Equivalência | Observação |
|------------|--------------|-------------|
| PCIe 3.0 x16 = PCIe 4.0 x8 | Mesma banda | GPUs topo às vezes nem usam tudo |
| PCIe 4.0 x16 = PCIe 5.0 x8 | Mesmo caso | Muito útil em servidores |
| PCIe 5.0 x4 (SSD) | ~15 GB/s | 2× mais rápido que 4.0 |

---

## 6️⃣ Onde cada geração faz mais diferença?

| Geração | Melhor uso |
|---------|-------------|
| PCIe 3.0 | GPU intermediária e SSD NVMe comum |
| PCIe 4.0 | GPU high-end e SSDs mais rápidos |
| PCIe 5.0 | SSDs extrema performance / IA |
| PCIe 6.0 | Data centers e futuro do consumidor |

---

## 7️⃣ Resumo Final

| Geração | x16 | Aplicação |
|---------|------|-------------|
| 1.0 | 4 GB/s | básico (obsoleto) |
| 2.0 | 8 GB/s | legado |
| 3.0 | 16 GB/s | ainda muito comum |
| 4.0 | 32 GB/s | padrão atual nos jogos |
| 5.0 | 64 GB/s | entusiastas / IA |
| 6.0 | 128 GB/s | futuro (servidores) |

---

📌 **Conclusão**

- O PCI começou como **paralelo**, virou gargalo, então nasceu o PCIe **serial**.
- Cada nova geração **dobra a largura de banda**.
- GPUs modernas raramente saturam PCIe 4.0 x16.
- SSDs NVMe foram os principais beneficiados nas últimas gerações.

---
