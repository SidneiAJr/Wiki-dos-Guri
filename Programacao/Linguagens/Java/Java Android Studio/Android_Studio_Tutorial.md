# 📱 Guia Completo — Android Studio com Java

O **Android Studio** é a IDE oficial para o desenvolvimento de aplicativos Android. Ele oferece suporte para **Java, Kotlin e Dart (Flutter)**, além de ferramentas como **emulador Android, gerenciador de dispositivos virtuais e integração com Gradle**.

Tambem Pode arrastar e copia a aplicação

---

## 🚀 O que você vai aprender neste guia

- ✅ O que é o Android Studio
- ✅ Como instalar e configurar
- ✅ Criar um projeto Android com Java
- ✅ Estrutura do projeto (Activity, XML, Manifest)
- ✅ Criar e executar emuladores Android
- ✅ Exemplos completos de código em Java
- ✅ Dicas extras para devs Android

---

## 🧠 O que é o Android Studio?

O **Android Studio é uma IDE (Ambiente de Desenvolvimento Integrado)** para criar aplicativos Android.  
Ele inclui:

| Recurso | Função |
|---------|-------|
| IDE | Escrever e rodar código |
| Gradle | Automatiza a construção do app |
| SDK Manager | Gerencia versões do Android |
| AVD Manager | Cria emuladores Android |
| Logcat | Exibe logs de execução |

---

## ⚙️ Instalação do Android Studio

### 1️⃣ Baixar o Android Studio
- Acesse: **https://developer.android.com/studio**
- Baixe a versão recomendada para seu sistema operacional.

### 2️⃣ Executar Instalador
- Siga os passos do instalador.
- O Android Studio irá configurar automaticamente:
  - **JDK (Java Development Kit)**
  - **SDK Android**
  - **Emulador Android**

### 3️⃣ Primeiro acesso
- Ao abrir a IDE pela primeira vez, espere a configuração inicial dos componentes.
- Vá em **Tools > SDK Manager** para verificar se as versões do Android estão instaladas corretamente.

---

## 🎯 Criando um Projeto Android com Java

### ▶️ Passo a passo

1. Clique em **Start a new Android Studio Project**
2. Escolha o template **Empty Activity**
3. Defina:
   - **Nome do App**
   - **Linguagem: Java**
   - **API mínima recomendada: API 21+**

---

## 📁 Estrutura do Projeto

| Arquivo/Pasta | Função |
|--------------|--------|
| `MainActivity.java` | Lógica principal do app |
| `activity_main.xml` | Interface em XML |
| `AndroidManifest.xml` | Permissões e configurações do app |

---

## 💻 Exemplo — MainActivity Java com Toast

```java
package com.exemplo.meuapp;

import android.os.Bundle;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Exemplo simples de exibição de mensagem
        Toast.makeText(this, "Bem-vindo ao Meu App!", Toast.LENGTH_SHORT).show();
    }
}
```

## 📱 Configurando um Emulador Android (AVD)
▶️ Criar um dispositivo virtual

Vá em Tools > AVD Manager

Clique em Create Virtual Device

Escolha um modelo (ex: Pixel 3 ou Pixel 6)

Selecione uma versão do Android

Clique em Finish

## ▶️ Testar o aplicativo

Clique em Run (▶) ou pressione Shift + F10

O app abrirá no emulador

🧩 Exemplos de Aplicações Java
🔹 Exemplo 2 — Conversor de Dólar
