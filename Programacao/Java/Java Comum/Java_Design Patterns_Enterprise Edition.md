# 🧩 Design Patterns — Enterprise Edition

## 📘 Introdução
**Design Patterns** são soluções comprovadas para **problemas recorrentes de design e arquitetura de software**.  
No contexto **Enterprise Java** (e outras linguagens orientadas a objetos), eles ajudam a criar sistemas **escaláveis, extensíveis e de fácil manutenção**.

---

## 🧱 Classificação dos Padrões

### 🏗️ Criação (Creational Patterns)
Focados em **como os objetos são criados** e **gerenciados**, promovendo flexibilidade e desacoplamento.

- **Factory Method** → Centraliza a criação de objetos, delegando a decisão da instância concreta para subclasses.  
  *Evita dependência direta de classes específicas.*

- **Abstract Factory** → Cria **famílias de objetos relacionados** sem expor suas classes concretas.  
  *Ideal para manter consistência entre objetos de um mesmo contexto (ex: UI temas, bancos, etc.).*

- **Builder** → Separa a **construção de um objeto complexo** da sua representação final.  
  *Facilita criar objetos configuráveis passo a passo.*

- **Singleton** → Garante que exista **apenas uma instância** de uma classe em todo o sistema.  
  *Útil para recursos globais, mas deve ser usado com cautela para evitar acoplamento e problemas de teste.*

---

### 🧩 Estrutural (Structural Patterns)
Tratam da **composição entre classes e objetos**, tornando o sistema mais modular e flexível.

- **Adapter** → Permite que **interfaces incompatíveis trabalhem juntas**, agindo como um tradutor entre elas.  
  *Exemplo: integrar uma biblioteca externa com uma interface interna.*

- **Facade** → Cria uma **interface simples e unificada** para um sistema complexo.  
  *Facilita o uso e reduz dependências diretas entre subsistemas.*

- **Composite** → Organiza objetos em **estruturas hierárquicas** (como árvores), permitindo tratá-los de forma uniforme.  
  *Exemplo: elementos gráficos compostos por subelementos.*

- **Decorator** → Adiciona **comportamentos dinamicamente** a objetos sem alterar sua estrutura original.  
  *Excelente para adicionar funcionalidades opcionais.*

- **Proxy** → Atua como um **intermediário controlando o acesso** a outro objeto.  
  *Usado para controle de acesso, cache, lazy loading, etc.*

---

### ⚙️ Comportamental (Behavioral Patterns)
Focados em **como os objetos interagem e se comunicam**.

- **Strategy** → Define **famílias de algoritmos intercambiáveis**, permitindo alterar o comportamento em tempo de execução.  
  *Exemplo: diferentes formas de cálculo de desconto.*

- **Observer** → Cria uma relação de **notificação automática** entre objetos.  
  *Quando um objeto muda de estado, seus observadores são atualizados.*  
  *Usado em eventos, notificações e sistemas reativos.*

- **Command** → Encapsula uma **ação como um objeto**, separando quem solicita da execução em si.  
  *Facilita histórico, undo/redo e filas de tarefas.*

- **Template Method** → Define o **esqueleto de um algoritmo** e permite que subclasses personalizem etapas específicas.  
  *Promove reutilização e consistência de fluxo.*

- **Chain of Responsibility** → Cria uma **cadeia de manipuladores** para processar requisições.  
  *Cada handler decide se trata a requisição ou passa adiante.*  
  *Ideal para validações, logs e pipelines de processamento.*

---

## 🎯 Objetivos dos Design Patterns
- Reduzir **acoplamento** entre componentes  
- Facilitar **testes e manutenção**  
- Promover **reutilização e clareza arquitetural**  
- Suportar **evolução do sistema** com menos impacto  
- Encapsular boas práticas e **designs reutilizáveis**

---

## 🧠 Princípios Relacionados (S.O.L.I.D)

- **S** — *Single Responsibility*: cada classe deve ter um único propósito  
- **O** — *Open/Closed*: aberto para extensão, fechado para modificação  
- **L** — *Liskov Substitution*: subclasses devem poder substituir suas superclasses  
- **I** — *Interface Segregation*: preferir várias interfaces pequenas e específicas  
- **D** — *Dependency Inversion*: depender de abstrações, não de implementações

---

## 💼 Contexto Enterprise
Padrões são amplamente aplicados em arquiteturas corporativas como:

- **Spring Framework** → Inversão de Controle (IoC) e Injeção de Dependência (DI)  
- **Microservices** → Desacoplamento entre domínios e escalabilidade  
- **Domain-Driven Design (DDD)** → Modelagem orientada ao domínio de negócio  
- **Clean Architecture** → Separação clara de camadas e responsabilidades

---

## 👑 Padrões Essenciais para Sistemas Grandes
- **Factory** → Gerência de criação de objetos  
- **Strategy** → Troca dinâmica de comportamentos  
- **Builder** → Montagem de objetos complexos  
- **Observer** → Comunicação reativa entre componentes  
- **Facade** → Simplificação de subsistemas  
- **Adapter** → Integração entre interfaces incompatíveis  
- **Template Method** → Estruturação de fluxos padrão  
- **Chain of Responsibility** → Processamento encadeado e flexível

> Saber Design Patterns **não é decorar nomes**, é entender **quando e por que aplicá-los**.

---
