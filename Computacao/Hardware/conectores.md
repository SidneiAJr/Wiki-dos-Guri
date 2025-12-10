# Conectores de PC (Alimentação, Dados e Expansão)

Os computadores utilizam diversos conectores internos e externos para alimentação elétrica e comunicação entre componentes. Conhecer cada conector ajuda a evitar erros de montagem e entender a compatibilidade entre peças.

---

## 1️⃣ Conectores de Alimentação (Fonte de Energia - PSU)

| Conector | Uso | Pinos | Onde é usado |
|----------|-----|--------|---------------|
| **ATX 24 pinos** | Alimenta a placa-mãe | 24 | Placa-mãe |
| **EPS 4+4 pinos (CPU)** | Alimenta o processador | 8 (ou 4+4) | Próximo ao soquete da CPU |
| **PCIe 6/8 pinos** | Alimenta a placa de vídeo | 6 ou 6+2 | GPU dedicada |
| **12VHPWR (16 pinos - novo)** | GPUs RTX 4000 / PCIe 5.0 | 16 | GPUs topo de linha |
| **SATA Power** | HDs, SSDs SATA, fans ARGB | 15 | Armazenamento / acessórios |
| **Molex 4 pinos** | Dispositivos antigos / fans antigos | 4 | Ventoinhas / controladores antigos |

---

### Observação importante
- A **placa-mãe não alimenta a GPU** → ela precisa do cabo PCIe separado.
- 12VHPWR é o substituto moderno dos 8 pinos.
- Algumas motherboards topo de linha usam **8 + 8 pinos** EPS para CPU.

---

## 2️⃣ Conectores de Dados (Armazenamento e Periféricos Internos)

| Conector | Tipo | Uso | Velocidade |
|----------|------|-----|------------|
| **SATA (dados)** | Cabo fino | HDs e SSDs SATA | Até 600 MB/s |
| **M.2 SATA** | slot interno | SSDs SATA | Mesmo do SATA |
| **M.2 NVMe (PCIe)** | slot interno | SSDs NVMe | Até 7000 MB/s (PCIe 4.0) |
| **U.2 (mais raro)** | profissional | Servidores / SSDs industriais | Muito rápido |

---

## 3️⃣ Conectores do Painel Frontal (Gabinete → Placa-mãe)

| Nome | Função |
|------|--------|
| **PWR_SW** | Botão de ligar |
| **RESET_SW** | Botão de reset |
| **HDD_LED** | Luz de atividade do armazenamento |
| **PWR_LED** | Luz do estado de ligado |
| **HD_AUDIO** | Áudio do painel frontal |
| **USB 2.0 / USB 3.0 / USB-C** | Portas de frente do gabinete |

---

## 4️⃣ Conectores de Fans e Bombas (Cooler)

| Conector | Pinos | Uso |
|----------|-------|-----|
| **FAN 3 pinos** | 3 | Controle por tensão (DC) |
| **FAN 4 pinos (PWM)** | 4 | Controle por pulsos (PWM) |
| **AIO_PUMP** | 4 | Bomba de water cooler |
| **ARGB (5V 3 pinos)** | 3 | Iluminação digital (endereçável) |
| **RGB (12V 4 pinos)** | 4 | LED tradicional fixo |

> **⚠ Inverter RGB com ARGB pode queimar iluminação**
> 5V ≠ 12V

---

## 5️⃣ Slots de Expansão (Placa-mãe)

| Slot | Uso |
|------|-----|
| **PCIe x16** | GPU |
| **PCIe x1 / x4** | Placas de rede, captura, som |
| **M.2 Key-M** | SSD NVMe |
| **M.2 Key-E** | Wi-Fi/Bluetooth |

---

Se o estilo estiver aprovado, eu continuo com:

✅ Seção: *Erros comuns ao montar PC*  
✅ Ilustração em ASCII (painel frontal / alimentação)  
✅ Explicação sobre B-Key, M-Key, E-Key no M.2

Confirma pra eu terminar?
Responda **"pode finalizar"** ✅  
ou **"ajusta antes"** se quiser alguma mudança.
