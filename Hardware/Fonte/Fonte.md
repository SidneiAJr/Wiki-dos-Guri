# Cálculos para Fontes (PSU) e Uso Geral

O dimensionamento correto da fonte de alimentação é essencial para garantir estabilidade e segurança do computador.

## Fórmula básica

A potência pode ser calculada pela fórmula:


Onde:
- **P** = Potência (Watts - W)
- **U** = Tensão (Volts - V)
- **I** = Corrente (Ampères - A)

## Observação Importante

> ***⚠️ SEMPRE CONSULTAR O FABRICANTE DA PSU***  
> Quem define a potência real suportada em cada trilha (+12V, +5V, +3.3V) é o **fabricante**, através da etiqueta técnica da fonte.
>
> Essa fórmula serve apenas para estimativas — o valor REAL está no rótulo da fonte.

---

## Exemplo prático

Se uma GPU consome 180W na linha de +12V:


Ou seja: a fonte deve fornecer **pelo menos 15 ampères** na linha +12V **só para a GPU**.

Se CPU consome 95W:


---

## Eficiência e Consumo da Tomada

Toda fonte perde um pouco de energia em forma de calor. A certificação **80 PLUS** indica quanta energia ela “desperdiça”.

Para saber o consumo REAL da tomada:

## Cálculo total com margem de segurança (banda de pico)

Vamos considerar o exemplo usado:

- GPU: 180W
- CPU: 95W

### 1️⃣ Soma do consumo

Consumo_Total = 180W (GPU) + 95W (CPU)
Consumo_Total = 275W

### 3️⃣ Banda de segurança (margem de 30%)

A margem cobre picos de consumo, quedas de tensão e o desgaste natural da fonte ao longo dos anos.

### 4️⃣ Recomendação final

Mesmo que o PC consuma cerca de **345W**,  
o ideal é uma fonte **de pelo menos 500W** (ou 550W / 600W para folga adicional).

| Consumo real | + 30% (pico) | Fonte recomendada |
|--------------|--------------|-------------------|
| 345W         | ~450W        | 500W ou 550W      |

---

## Por que não usar fonte “justa”?

- A fonte NUNCA deve trabalhar em 100% por longos períodos
- Em picos, a GPU pode ultrapassar o TDP nominal
- Eficiência cai quando a fonte trabalha no limite
- Menos estresse = mais vida útil

---


# Certificações de Fontes (Eficiência + Proteções)

## 🔌 Certificações de Eficiência (80 PLUS)

| Certificação   | Eficiência 20% | 50% | 100% | Indicação |
|----------------|----------------|-----|------|-----------|
| 80 PLUS White  | 80%            | 80% | 80%  | Básico / Antigo |
| 80 PLUS Bronze | 82%            | 85% | 82%  | Bom custo-benefício |
| 80 PLUS Silver | 85%            | 88% | 85%  | Intermediário |
| 80 PLUS Gold   | 87%            | 90% | 87%  | Recomendado para a maioria dos PCs |
| 80 PLUS Platinum | 90%          | 92% | 89%  | Alto desempenho |
| 80 PLUS Titanium | 90%(10%) • 92%(20%) | 94% | 90% | Servidores / Workstations |

---

## ⚙️ Proteções Internas (Segurança)

| Sigla | Nome (em inglês)            | Função |
|-------|-----------------------------|--------|
| OCP   | Over Current Protection     | Evita excesso de **corrente** |
| OVP   | Over Voltage Protection     | Evita **tensão alta** |
| UVP   | Under Voltage Protection    | Evita **queda de tensão** |
| OPP   | Over Power Protection       | Evita ultrapassar a **potência total** |
| SCP   | Short Circuit Protection    | Corta energia em caso de **curto-circuito** |
| OTP   | Over Temperature Protection | Desliga quando há **superaquecimento** |
| SIP   | Surge/Inrush Protection     | Protege contra **picos e surtos** |

---

> ✅ Quanto mais certificações **de eficiência** + mais proteções **internas**, melhor e mais confiável é a PSU.


