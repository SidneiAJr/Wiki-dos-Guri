# ⚙️ Introdução a Componentes Passivos e Ativos

## 📘 O que são Componentes Eletrônicos?
Os **componentes eletrônicos** são os blocos fundamentais dos circuitos.  
Eles se dividem em duas grandes categorias:

- **Passivos:** não geram energia, apenas a consomem ou armazenam.  
- **Ativos:** controlam o fluxo de corrente e podem amplificar ou gerar sinais.

---

## 🧩 1. Componentes Passivos

### 🔸 Resistor
Limita o fluxo de corrente elétrica em um circuito.

- **Símbolo:** ⏧  
- **Unidade:** Ohm (Ω)  
- **Lei de Ohm:** `V = R × I`  
- **Uso comum:** proteger LEDs e controlar correntes.

📎 **Curiosidade:** os resistores são codificados por **faixas de cores** que indicam seu valor em ohms.

---

### 🔸 Capacitor
Armazena energia elétrica em forma de **campo elétrico**.

- **Unidade:** Farad (F)  
- **Símbolo:** ||  
- **Função:** filtrar sinais, armazenar energia, suavizar ruídos.  
- **Tipos:** cerâmico, eletrolítico, tantalum.

💡 **Exemplo:** usado em fontes para estabilizar a tensão após a retificação.

---

### 🔸 Indutor
Armazena energia em forma de **campo magnético**.

- **Unidade:** Henry (H)  
- **Símbolo:** espiral (bobina)  
- **Função:** filtrar ruído, armazenar energia em conversores.  
- **Presente em:** fontes chaveadas, rádios, e motores.

---

### 📊 Comparativo entre Passivos

| Componente | Armazena Energia? | Controla Corrente? | Exemplo de Uso |
|-------------|------------------|--------------------|----------------|
| Resistor | ❌ | ✅ (limita) | LED, divisores de tensão |
| Capacitor | ✅ (elétrica) | ❌ | Filtros, fontes |
| Indutor | ✅ (magnética) | ❌ | Conversores, filtros |

---

## ⚡ 2. Componentes Ativos

### 🔹 Diodo
Permite a passagem de corrente **em um só sentido**.

- **Polarização direta:** conduz.  
- **Polarização reversa:** bloqueia.  
- **Tensão típica (Si):** 0,7V.

| Tipo | Aplicação |
|------|------------|
| Diodo comum (1N4007) | Retificação |
| Diodo Zener | Estabilização de tensão |
| LED | Emissão de luz |
| Schottky | Alta velocidade, baixa queda de tensão |

---

### 🔹 Transistor
Pode **amplificar sinais** ou **atuar como chave**.

- **Tipos:** BJT (NPN, PNP), MOSFET  
- **Terminais:** Base (B), Coletor (C), Emissor (E)  
- **Aplicações:** amplificadores, controle de motores, lógica digital.

📎 **Curiosidade:** os processadores modernos têm **bilhões de transistores** em um único chip.

---

### 🔹 Circuitos Integrados (CIs)
Conjunto de **centenas ou milhões de componentes miniaturizados** em um chip de silício.

| CI | Função |
|----|--------|
| NE555 | Temporizador / oscilador |
| LM741 | Amplificador operacional |
| 7805 | Regulador de tensão 5V |
| ATmega328 | Microcontrolador do Arduino |

---

### 🔹 Sensores e Microcontroladores
São componentes ativos “inteligentes”, capazes de **interagir com o ambiente** e **tomar decisões**.

| Categoria | Exemplos | Função |
|------------|-----------|--------|
| Sensores | LDR, NTC, DHT11 | Detectam luz, temperatura, umidade |
| Atuadores | Relés, motores | Executam ações físicas |
| Microcontroladores | Arduino, ESP32 | Controlam sistemas automáticos |

---

## ⚖️ Comparando Ativos e Passivos

| Característica | Passivos | Ativos |
|----------------|-----------|--------|
| Geram energia? | ❌ | ✅ (controlam ou amplificam) |
| Precisam de fonte externa? | ❌ | ✅ |
| Armazenam energia? | ✅ (alguns) | ✅ (internamente) |
| Exemplo | Resistor, Capacitor, Indutor | Diodo, Transistor, CI |
| Função principal | Condicionar sinais | Controlar ou processar sinais |

---

## 🔍 Dica Prática
> Todo circuito eletrônico é uma **combinação de componentes passivos e ativos**.  
> Passivos moldam o sinal, e os ativos o **processam**.

---

## 📚 Referências
- *Malvino – Eletrônica Volume 1 e 2*  
- *Sedra & Smith – Microeletrônica*  
- Datasheets: Texas Instruments, STMicroelectronics  
- [Falstad Circuit Simulator](https://falstad.com/circuit/)

---

**Autor:** _Seu Nome_  
**Data:** `2025-10-20`  
**Licença:** MIT  

> 💬 “Os componentes passivos sustentam o circuito, os ativos lhe dão vida.”
