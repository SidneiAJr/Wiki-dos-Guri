# 🪲 IntelliJ IDEA — Guia de Depuração (Debug)

Aprenda a usar o **modo Debug** do IntelliJ IDEA para analisar e corrigir o comportamento do seu código passo a passo.  
Ideal para encontrar bugs, entender fluxos e inspecionar variáveis durante a execução.

---

## 🎯 O que é o modo Debug?

O **Debug** permite que você execute o programa **de forma controlada**, pausando a execução em pontos específicos (breakpoints) para observar o estado das variáveis e a lógica do código.

---

## 📍 Como iniciar o Debug

1. Clique na **margem esquerda** do código (ao lado do número da linha) para adicionar um **breakpoint**.  
   🔴 Um ponto vermelho será exibido.
2. Vá em `Run → Debug 'Main'` ou use o atalho **Shift + F9**.
3. O programa será iniciado e **pausará no breakpoint**.

---

## ⚙️ Controles principais

| Atalho | Função |
|:--------|:--------|
| **F8** | Step Over — Executa a linha atual e vai para a próxima |
| **F7** | Step Into — Entra dentro de métodos chamados na linha atual |
| **Shift + F8** | Step Out — Sai do método atual e volta para o chamador |
| **Alt + F9** | Run to Cursor — Executa até o ponto onde o cursor está |
| **Ctrl + F2** | Finaliza a execução do programa |
| **F9** | Resume Program — Continua a execução até o próximo breakpoint |

---

## 🔍 Janela de Depuração

Durante o debug, observe:
- **Variables:** mostra o valor atual de cada variável.
- **Watches:** permite acompanhar variáveis ou expressões específicas.
- **Call Stack:** mostra o caminho das chamadas de método até o ponto atual.
- **Evaluate Expression (`Alt + F8`)**: permite testar expressões e ver seus resultados em tempo real.

---

## 💡 Dicas Úteis

- Você pode **mudar o valor de uma variável** durante a execução para testar diferentes cenários.
- Pode adicionar **condições em breakpoints** (clicando com o botão direito sobre o ponto vermelho).
- Se estiver depurando interfaces gráficas (Swing ou JavaFX), cuidado com threads secundárias.
- Combine Debug com **Logpoints** (breakpoints que não pausam, mas mostram mensagens no console).

---


