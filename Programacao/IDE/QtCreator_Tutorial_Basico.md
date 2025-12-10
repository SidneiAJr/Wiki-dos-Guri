# 🧠 Tutorial — Introdução ao Qt Creator (C++)

## 🎯 Objetivo
Aprender a **instalar, configurar e usar o Qt Creator**, a IDE oficial para criar aplicações **gráficas e multiplataforma em C++** usando o framework **Qt**.

---

## 🧱 1️⃣ O que é o Qt Creator?

O **Qt Creator** é uma IDE (Ambiente de Desenvolvimento Integrado) voltada para **C++**, desenvolvida pela **The Qt Company**.  
Ele permite criar aplicações **visuais, multiplataforma e de alto desempenho**, com suporte a **Windows, Linux, macOS e até mobile** (Android e iOS).

---

## ⚙️ 2️⃣ Instalação do Qt Creator

### 🔹 Passo a passo:
1. Acesse: [https://www.qt.io/download](https://www.qt.io/download)  
2. Baixe o instalador **Qt Online Installer** (versão gratuita “Open Source”).  
3. Durante a instalação:
   - Escolha **Qt 6.x** (ou a mais recente).  
   - Marque **MinGW** (para Windows) ou **GCC** (para Linux).  
   - Inclua **Qt Creator IDE** na seleção.  
4. Conclua o processo e abra o **Qt Creator**.

---

## 🧩 3️⃣ Criando seu primeiro projeto

### Passos:
1. Abra o **Qt Creator**  
2. Vá em **File → New Project → Qt Widgets Application**  
3. Dê um nome ao projeto (ex: `MeuPrimeiroQt`)  
4. Escolha a pasta onde salvar  
5. Clique em **Next → Finish**

---

## 🖥️ 4️⃣ Estrutura do Projeto

Após criar, o projeto gerará os seguintes arquivos:

| Arquivo | Função |
|----------|--------|
| `main.cpp` | Função principal do programa |
| `mainwindow.ui` | Interface gráfica (editável no Qt Designer) |
| `mainwindow.h` | Cabeçalho (declarações de classes e funções) |
| `mainwindow.cpp` | Lógica da interface e eventos |
| `.pro` | Arquivo de configuração do projeto (usado pelo QMake) |

---

## 🎨 5️⃣ Criando Interface Gráfica

1. Abra o arquivo `mainwindow.ui`  
2. Isso abrirá o **Qt Designer**, o editor visual de janelas.  
3. Na lateral esquerda, você verá componentes como:
   - **PushButton** → botão
   - **Label** → texto
   - **LineEdit** → campo de entrada
   - **ComboBox**, **RadioButton**, etc.

4. Arraste e solte os componentes para dentro da janela (`MainWindow`).

---

## ⚡ 6️⃣ Criando um Evento de Clique

1. Selecione o **botão** adicionado no `mainwindow.ui`  
2. Clique com o botão direito → **Go to Slot...**  
3. Escolha o evento `clicked()`  
4. O Qt Creator abrirá automaticamente o código `mainwindow.cpp`

Adicione a ação:
```cpp
void MainWindow::on_pushButton_clicked()
{
    QMessageBox::information(this, "Mensagem", "Botão clicado!");
}
