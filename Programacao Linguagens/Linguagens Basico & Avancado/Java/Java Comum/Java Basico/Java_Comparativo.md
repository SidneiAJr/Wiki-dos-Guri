# ⚖️ Comparação entre C++, Java e C#

Esta tabela destaca as **principais diferenças** entre C++, Java e C#, com foco em **memória, segurança, concorrência e execução**.

| Aspecto                      | C++                                                         | Java                                                                                  | C#                                                                                    |
| ---------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Gerenciamento de memória** | Manual (`new`/`delete`). O programador é responsável por liberar memória, aumentando o risco de **vazamentos** ou uso indevido. | Automático via **Garbage Collector (GC)**. Reduz risco de erros de memória e **use-after-free**. | Automático via **GC**, similar ao Java; gerencia memória e evita uso de objetos já liberados. |
| **Buffer overflow**          | Alta vulnerabilidade ao escrever além dos limites de arrays (`char buffer[10]`), podendo corromper memória. | Protegido; exceder limites de arrays gera **`ArrayIndexOutOfBoundsException`**. | Protegido; exceder limites de arrays gera **`IndexOutOfRangeException`**. |
| **Use-after-free**           | Possível e perigoso se um ponteiro acessar memória já liberada. | Impossível; GC garante que objetos acessíveis não são liberados prematuramente. | Impossível; GC mantém objetos vivos enquanto há referências. |
| **Memory leak**              | Comum se esquecer de chamar `delete` ou perder referência a objetos. | Raro, mas ainda possível se referências não forem liberadas (ex: listeners, caches). | Raro, mas possível com referências não liberadas (ex: eventos ou caches). |
| **Input injection**          | Depende do programador; vulnerável se não houver validação de entrada. | Depende do programador; cuidados necessários com SQL injection ou execução de comandos (`Runtime.exec`). | Depende do programador; cuidados necessários com SQL injection ou execução de processos (`Process.Start`). |
| **Tipos primitivos**         | Podem ser alocados na **stack** ou **heap**, inicialização manual. | Inicializados automaticamente em objetos; variáveis locais precisam ser inicializadas explicitamente. | Inicializados automaticamente em objetos; variáveis locais precisam ser inicializadas explicitamente. |
| **Concorrência**             | Threads manuais + mutex; maior risco de **race conditions** e deadlocks. | `synchronized`, `ReentrantLock`, classes **Atomic**; abstrações seguras e de alto nível. | `lock`, `Monitor`, classes **Interlocked**; abstrações seguras e de alto nível. |
| **Compilação e execução**    | Compilado para **binário nativo**, execução direta no hardware. | Compilado para **bytecode**, executado na JVM (máquina virtual). | Compilado para **bytecode (IL)**, executado na CLR (.NET runtime). |
| **Segurança de tipos**       | Fraca; casts podem quebrar o tipo, possibilitando erros em runtime. | Forte; checagem em tempo de compilação e runtime previne inconsistências. | Forte; checagem em tempo de compilação e runtime previne inconsistências. |

---

## 📝 Observações Gerais

- **C++** é poderoso, rápido e próximo do hardware, mas exige cuidado com memória e segurança.  
- **Java** combina portabilidade, segurança e facilidade de gerenciamento de memória, ideal para sistemas corporativos.  
- **C#** oferece recursos semelhantes a Java, com integração completa ao ecossistema .NET e melhorias em produtividade e segurança de tipos.  
- Todas as linguagens dependem de boas práticas do programador para evitar vulnerabilidades como injeção de entrada ou vazamentos de memória.

---
