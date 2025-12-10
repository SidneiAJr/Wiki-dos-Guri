# 🧱 Containers vs Máquinas Virtuais (VMs)

Tanto **containers** quanto **máquinas virtuais (VMs)** são tecnologias de virtualização,  
mas funcionam de formas **bem diferentes** e são usadas para propósitos distintos.

---

## ⚙️ Conceito Básico

| Tecnologia | O que é |
|:--|:--|
| **Máquina Virtual (VM)** | Simula um **computador completo**, com sistema operacional próprio. |
| **Container** | Isola **aplicações** dentro do mesmo sistema operacional, de forma leve e rápida. |

---

## 🧩 Estrutura Comparativa

### 🖥️ Máquina Virtual

- Cada VM precisa de:
  - Sistema operacional próprio (guest OS)
  - Kernel independente
  - Drivers e bibliotecas completas
- O hypervisor (ex: VirtualBox, VMware, Hyper-V) faz a intermediação com o hardware.


**Exemplo:**  
Instalar um Ubuntu Server dentro do Windows usando VirtualBox.

---

### 📦 Container

- Compartilha o **kernel do sistema operacional** com o host.  
- Isola apenas o ambiente de execução da aplicação.  
- Leve, rápido e consome menos recursos.


**Exemplo:**  
Rodar um servidor web Nginx ou uma aplicação Python dentro de um container Docker.

---

## ⚖️ Comparação Direta

| Critério | Containers | Máquinas Virtuais |
|:--|:--:|:--:|
| **Inicialização** | Segundos | Minutos |
| **Tamanho médio** | Centenas de MB | Vários GB |
| **Isolamento** | A nível de processo | A nível de hardware |
| **Uso de recursos** | Leve (compartilha kernel) | Pesado (SO completo) |
| **Portabilidade** | Alta | Média |
| **Segurança** | Boa, mas compartilhada | Alta (total isolamento) |
| **Gerenciamento** | Docker, Podman, Kubernetes | Hypervisor, VMware, VirtualBox |
| **Casos de uso** | Microserviços, DevOps, CI/CD | Testes de sistemas, SOs, virtualização completa |

---

## 🚀 Exemplo Prático

### 🧩 Container (Docker)
```bash
docker run -d -p 80:80 nginx
```

