# 🖥️Introdução ao Hardware

O hardware do computador é composto por diversos componentes físicos responsáveis pelo funcionamento da máquina. Entre os principais, podemos destacar:

## 🧠1. Processador (CPU)

É o cérebro do computador. Ele realiza cálculos e processa as instruções dos programas, controlando tudo o que acontece no sistema.

## 2. Memória Volátil (RAM)

Armazena temporariamente os dados que o processador está utilizando no momento.
Quando o computador é desligado, o conteúdo da RAM é apagado.

## 3. Ponte Norte e Ponte Sul (Chipset)

São responsáveis pela comunicação entre os componentes da placa-mãe.

Ponte Norte: faz a ligação entre o processador, a memória RAM e a placa de vídeo (quando ela é onboard).

Ponte Sul: conecta dispositivos de menor velocidade, como USB, HD/SSD, teclado, mouse etc.

## 4. BIOS / UEFI

É o sistema básico de inicialização que configura o hardware antes de carregar o sistema operacional.
Ele é gravado num chip na placa-mãe.

## 5. Placa de Vídeo (GPU)

Responsável pelo processamento gráfico, como imagens, vídeos, jogos e renderização 3D.
Pode ser integrada ao processador/placa-mãe ou ser uma placa dedicada.

## 6. Slots PCI / PCIe

São entradas de expansão na placa-mãe onde podemos conectar placas adicionais, como:

Placa de vídeo dedicada

Placa de som

Placa de rede

Captura de vídeo


## 💾Diferença entre SSD & HD:

| Característica     | HD (Disco Rígido)               | SSD (Unidade de Estado Sólido)     |
|--------------------|----------------------------------|-------------------------------------|
| Tecnologia         | Disco magnético com partes móveis | Memória flash (sem partes mecânicas) |
| Velocidade         | Lento                            | Rápido                              |
| Ruído              | Pode fazer barulho               | Silencioso                          |
| Resistência        | Mais frágil                      | Mais resistente                     |
| Consumo de Energia | Maior                            | Menor                               |
| Preço              | Mais barato                      | Mais caro                           |


## Memoria Tipos:

| Geração   | Ano Aproximado | Frequência (Mhz efetivos) | Tensão | Velocidade | Observações |
|-----------|----------------|---------------------------|--------|------------|-------------|
| DDR (DDR1) | 2000-2002       | 200 ~ 400 MHz              | 2.5V   | Baixa      | Primeira geração de DDR usada em PCs |
| DDR2      | 2003-2005       | 400 ~ 800 MHz              | 1.8V   | Melhor que DDR | Menor consumo que DDR1 |
| DDR3      | 2007-2010       | 800 ~ 2133 MHz             | 1.5V   | Alta       | Muito utilizada por muitos anos |
| DDR4      | 2014-2016       | 2133 ~ 3200+ MHz           | 1.2V   | Muito alta | Mais rápida e eficiente energeticamente |
| DDR5      | 2021            | 4800 ~ 7200+ MHz           | 1.1V   | Extremamente alta | Maior largura de banda |
| DDR6*     | Em desenvolvimento | Pode ultrapassar 10.000 MHz | <1.1V? | Futuro | Ainda não disponível comercialmente |

## Diferença entre SSD X NVME X SHDD X HD

| Tipo        | Tecnologia | Velocidade | Partes Mecânicas | Tempo de Inicialização | Custo | Melhor Uso |
|-------------|-------------|------------|-------------------|-------------------------|--------|-------------|
| HD          | Disco magnético | Lento      | ✅ Sim             | Alto (30s ~ 2min)        | 💰 Barato | Armazenar grandes arquivos |
| SSHD        | Híbrido (HD + pequena memória flash) | Médio      | ✅ Sim (mas com cache flash) | Médio (20s ~ 40s) | 💰💰 Moderado | Usuários que querem algo intermediário |
| SSD SATA    | Memória flash (SATA) | Rápido     | ❌ Não             | Baixo (10s ~ 20s)        | 💰💰 Moderado | Sistema operacional e programas |
| SSD NVMe    | Memória flash (PCIe / M.2) | Muito rápido | ❌ Não             | Muito baixo (5s ~ 10s)  | 💰💰💰 Mais caro | Alto desempenho, jogos e tarefas pesadas |

# 7. Fonte de Alimentação (PSU)

A **PSU (Power Supply Unit)** fornece energia elétrica para todos os componentes do computador, convertendo a tensão da rede (AC) em tensões DC necessárias (tipicamente +12V, +5V e +3.3V). Uma boa PSU é essencial para estabilidade, segurança e longevidade do sistema.

## Principais características
- **Potência nominal** (W): capacidade total que a PSU pode fornecer (ex.: 500W, 650W, 850W).
- **Eficiência**: relação entre potência de saída e consumo da rede (ex.: 80 PLUS Bronze, Silver, Gold, Platinum).
- **Conectores**: 24-pin ATX, 8-pin CPU, PCIe 6/8-pin para GPU, SATA, Molex.
- **Modularidade**: modular, semi-modular ou não modular (cabeamento removível facilita montagem).
- **Capacidade da(s) trilha(s) +12V**: hoje em dia a maior parte da potência útil vem da(s) linha(s) +12V — confira a corrente (A) disponível nessa linha.
- **Forma**: ATX, SFX (tamanhos físicos).

---

## Fórmula básica (Lei de Ohm aplicada)
A relação entre potência (P), tensão (U, em volts) e corrente (I, em ampères) é:


---

## Cálculo prático — Como dimensionar a PSU

### 1) Estime o consumo dos componentes
Exemplo de somatório (valores típicos, só como exemplo):

| Componente       | Consumo aproximado |
|------------------|--------------------:|
| CPU              | 95 W               |
| GPU              | 250 W              |
| Placa-mãe        | 50 W               |
| RAM (2x)         | 20 W               |
| SSD              | 5 W                |
| HDD              | 8 W                |
| Fans (3x)        | 15 W               |
| **Total**        | **443 W**          |

### 2) Adicione margem de segurança (headroom)
Recomenda-se adicionar entre **20% e 30%** para picos, envelhecimento e upgrades:

- Com 30% de margem: `443 W × 1.30 = 575.9 W` → escolher uma PSU comercial de **650 W** seria apropriado.

### 3) Verifique a corrente na linha +12V
Se a maior parte da potência é entregue em +12V (comum em CPU+GPU):

Ex.: se CPU+GPU consomem 345 W (250 + 95):


Ex.: para uma PSU escolhida de 650 W com eficiência prática de 90% (0.90):

- `P_in = 650 / 0.90 = 722.22 W`

Em tomadas de 230 V:
- `I_input = 722.22 / 230 ≈ 3.14 A`

Em tomadas de 127 V:
- `I_input = 722.22 / 127 ≈ 5.69 A`

---

## Recomendações práticas
- **Prefira PSUs com selo 80 PLUS Bronze ou superior** (Gold/Platinum melhor eficiência).
- **Dê preferência a PSUs com boa margem na(s) linha(s) +12V** (GPU/CPU dependem disso).
- **Evite comprar no limite** (escolha sempre com 20–30% a mais do que o somatório dos componentes).
- **Considere picos de corrente** (por exemplo, alguns GPUs têm picos no arranque).
- **Não baseie a compra apenas no preço** — qualidade de componentes internos (capacitores, filtros) importa.
- **Cheque conectores**: se a sua GPU precisa de 2×8-pin PCIe, confirme que a PSU tem essas saídas nativas (não use adaptadores sempre que possível).
- **Se planeja upgrades (GPU mais potente)**, prefira uma PSU mais robusta desde já.

---

## Exemplos rápidos
1. **Corrente necessária em +12V** para 500 W inteiramente no 12V:


## Exemplo de Placa mãe:

![placa mae](https://github.com/SidneiAJr/Documentacao/blob/main/prints/10.png)


