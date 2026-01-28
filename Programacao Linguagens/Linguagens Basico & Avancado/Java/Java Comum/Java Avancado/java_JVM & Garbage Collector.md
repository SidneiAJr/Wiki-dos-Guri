# ☕ JVM & Garbage Collector

## 📘 Introdução
A **Java Virtual Machine (JVM)** é o coração da plataforma Java.  
Ela é responsável por **executar, otimizar e gerenciar a memória** das aplicações, garantindo portabilidade e eficiência.  

Compreender sua arquitetura é essencial para escrever **código performático e escalável** — é o que diferencia um desenvolvedor pleno de um sênior.

---

## 🧠 Estrutura da JVM

A JVM é composta por **módulos de execução e gerenciamento de memória**, organizados em áreas conhecidas como *Runtime Data Areas*.

### 🔹 Runtime Data Areas

- **Stack (Pilha da Thread)** → Armazena variáveis locais, parâmetros de métodos e referências temporárias.  
  Cada *thread* tem sua própria pilha, e cada chamada de método cria um *frame*.

- **Heap** → Área compartilhada entre todas as threads, usada para armazenar **objetos** e **instâncias de classes**.  
  É a principal região gerenciada pelo Garbage Collector.

- **Metaspace** → Substituiu a antiga *PermGen*.  
  Guarda **metadados de classes**, **informações de métodos** e **estruturas de reflexão**.

- **PC Register (Program Counter)** → Indica a **instrução atual** sendo executada pela thread.  
  Cada thread possui seu próprio registrador.

- **Native Method Stack** → Armazena dados e instruções relacionados a **métodos nativos** (escritos em C/C++), usados via JNI.

---

## 🧩 Gerenciamento de Memória

A memória da JVM é dinâmica e organizada em regiões.  
O **Heap** é dividido para otimizar a coleta de lixo e a alocação de objetos.

### 🧱 Estrutura do Heap

- **Young Generation (Geração Jovem)**  
  Onde os novos objetos são criados.  
  Dividida em:
  - **Eden Space** → primeira área onde os objetos nascem.  
  - **Survivor Spaces (S0 e S1)** → armazenam objetos que sobreviveram a uma ou mais coletas.

- **Old Generation (Tenured)**  
  Contém objetos que **sobreviveram várias coletas** e são considerados de longa duração.  

📈 **Fluxo de vida dos objetos:**  
**Eden → Survivor → Old Generation**

---

## 🧹 Garbage Collector (GC)

O **Garbage Collector** é responsável por **liberar memória automaticamente**, removendo objetos que não estão mais em uso.

### 🔸 Principais Implementações

- **Serial GC** → Coleta simples e **single-threaded**.  
  Ideal para aplicações pequenas e ambientes com poucos núcleos.

- **Parallel GC** → Usa múltiplas threads para coletar, priorizando **throughput** (máximo desempenho bruto).  
  Mais pausas, mas maior eficiência em servidores.

- **CMS (Concurrent Mark-Sweep)** → Coleta paralela com **pausas menores**.  
  Agora é considerado **obsoleto**, substituído pelo G1 GC.

- **G1 GC (Garbage First)** → O **padrão atual** para servidores.  
  Divide o heap em regiões menores, coleta primeiro as que têm mais lixo, e mantém pausas previsíveis.

- **ZGC** → Focado em **latência ultra-baixa** com pausas abaixo de 10 ms, mesmo com heaps grandes.  
  Ideal para sistemas críticos.

- **Shenandoah** → Similar ao ZGC, otimiza coleta **concurrente**, mantendo **baixa latência** em aplicações de grande escala.

---

## ⚙️ Conceitos Importantes

- **Stop-the-World (STW)** → Pausa global onde todas as threads são suspensas para o GC executar.  
  Incontrolável, mas pode ser minimizada.

- **Compacting** → Processo de **reorganizar objetos** na memória, eliminando fragmentação e melhorando acesso.

- **Promotion** → Quando um objeto sobrevive a várias coletas e é movido da *Young* para a *Old Generation*.

- **Finalization** → Técnica antiga de limpeza de objetos; deve ser **evitada** devido a problemas de performance e imprevisibilidade.

---

## 🎯 Boas Práticas de Performance

- Evitar **criação excessiva de objetos temporários**.  
- Usar **objetos imutáveis** sempre que possível.  
- **Reutilizar objetos pesados** (como conexões e buffers).  
- **Monitorar o heap e o GC** em ambientes de produção.  

### 🧰 Ferramentas Recomendadas
- **Java Flight Recorder (JFR)** → Análise detalhada de performance em tempo real.  
- **JDK Mission Control (JMC)** → Visualização e diagnóstico de métricas do JFR.  
- **VisualVM** → Monitoramento e profiling de heap, threads e GC.  

---

## 🧠 Conclusão
A JVM é muito mais que um simples executor de bytecode — é uma **máquina inteligente de gerenciamento de recursos**.  
Compreender sua arquitetura e o funcionamento do **Garbage Collector** é essencial para:

- Otimizar performance  
- Evitar vazamentos de memória  
- Garantir estabilidade em produção  

> **Entender a JVM = dominar o motor da plataforma Java.**

---
