# 🐧 Linux | Lista de Comandos Essenciais para Usar no Shell

Aqui está uma lista limpa, organizada e explicada dos comandos mais usados no Linux para administração básica e criação de scripts.

---

## 🔧 Atualização do Sistema

### **Atualizar repositórios**

```bash
sudo apt update
sudo apt upgrade
```

### 📂 Navegação e Manipulação de Diretórios
Mostrar diretório atual
pwd

Criar diretório
```bash
mkdir nome_da_pasta
```

### Criar várias pastas:
```bash
mkdir pasta1 pasta2 pasta3
```

### Criar pasta com estrutura (recursivo):
```bash
mkdir -p projeto/src/assets
```
### 📄 Manipulação de Arquivos
Exibir conteúdo de um arquivo
```bash
cat arquivo.txt
```
### ✍ Editores de Texto
Editor vim (avançado)
```bash
vim arquivo.txt
```
### Editor nano (fácil)
```bash
nano arquivo.txt
```
### 🖥 Monitoramento do Sistema
Ver processos em tempo real
```bash
htop
```

### Se não tiver instalado:
```bash
sudo apt install htop
```

### Listar arquivos
```bash
ls
```
### Listar com detalhes
```bash
ls -l
```
### Listar inclusive ocultos
```bash
ls -la
```
### Entrar em um diretório
```bash
cd nome_da_pasta
```
### Voltar um nível
```bash
cd ..
```
### Ir para o diretório inicial
```bash
cd ~
```
