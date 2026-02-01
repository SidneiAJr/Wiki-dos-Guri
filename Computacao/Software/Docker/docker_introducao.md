# 🐳 Docker — Canvas Conceitual

> Introdução ao Docker, explicando de forma clara os conceitos, usos e considerações técnicas.

---

## 1. O que é Docker?

* Docker é uma plataforma de **containerização** que permite criar, distribuir e executar aplicações em **ambientes isolados e padronizados**, chamados containers.
* Um container encapsula a aplicação junto com todas as suas dependências, bibliotecas e configurações, garantindo que ela rode da mesma forma em qualquer máquina.

---

## 2. Pra que serve?

* **Padronização de ambientes:** evita o clássico "na minha máquina funciona".
* **Desenvolvimento ágil:** permite levantar rapidamente ambientes completos.
* **Escalabilidade:** facilita replicar serviços e aplicações em servidores ou nuvem.
* **Isolamento:** cada container é independente, reduzindo conflitos entre aplicações.
* **Entrega contínua (CI/CD):** integra facilmente em pipelines de deploy.

---

## 3. Preciso instalar localmente no PC?

* **Opcional, mas recomendado para desenvolvimento:**

  * Pode usar Docker Desktop (Windows/Mac) ou instalar Docker Engine (Linux).
  * Permite criar, rodar e testar containers localmente.
* **Alternativas sem instalar localmente:**

  * Usar ambientes em nuvem (Docker Cloud, Play with Docker).

---

## 4. Consumo de RAM e Recursos

* Containers compartilham o **kernel do sistema operacional**, diferente de VMs, então geralmente consomem **menos memória e CPU**.
* É possível limitar recursos (RAM, CPU, disco) de cada container com flags de configuração.
* O consumo depende do **tipo de aplicação** e do número de containers ativos.

---

## 5. Docker é uma VM disfarçada?

* **Não exatamente**, mas pode parecer similar:

  * VM (Máquina Virtual) roda um **SO completo** emulado, isolado do host.
  * Container compartilha o **kernel do host**, apenas isolando processos, arquivos e rede.
  * Containers são **mais leves, rápidos e portáteis**.

---

## 6. Benefícios resumidos

* Portabilidade de aplicações
* Rapidez na inicialização
* Menor consumo de recursos comparado a VMs
* Facilita CI/CD e DevOps
* Isolamento seguro de serviços

---

*Canvas Docker — visão geral, usos, instalação e considerações de performance.*
