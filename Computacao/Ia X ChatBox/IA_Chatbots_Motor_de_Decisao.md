# ⚙️ Motor de Decisão (Lógica e IA)

O **motor de decisão** é o componente responsável por determinar **o que o chatbot deve fazer** após interpretar uma mensagem do usuário.  
Ele conecta a **compreensão da linguagem (NLP/NLU)** com a **ação prática**, seja responder algo, executar uma função ou seguir um fluxo específico.

---

## 🧩 Como Funciona

1. **Entrada do Usuário:**  
   O chatbot recebe a mensagem e envia para o módulo de NLP/NLU para identificar a intenção.  

2. **Análise de Intenção:**  
   O sistema entende o que o usuário quer — por exemplo:  
   - "Quero rastrear meu pedido" → intenção = *rastreamento*  
   - "Esqueci minha senha" → intenção = *recuperar acesso*

3. **Decisão Lógica:**  
   O motor de decisão avalia a intenção e escolhe o **fluxo de resposta** adequado.  
   Esse processo pode envolver diferentes etapas:

   - **Verificação lógica ou matemática:** o sistema analisa os dados e verifica se a informação solicitada faz sentido ou é válida.  
   - **Validação de contexto:** antes de gerar a resposta, o chatbot confirma se entendeu corretamente o pedido.  
   - **Geração de resposta adequada:** com base na análise, o motor decide qual ação ou mensagem deve ser executada.  

   Em alguns casos, podem ocorrer **“chamadas” internas** (requisições entre módulos de IA ou APIs externas) para buscar informações adicionais antes de responder ao usuário.

   > 💬 **Exemplo:**  
   > Em certos contextos, a IA pode interpretar expressões informais — como “coe beleza?” — de forma incorreta, confundindo-as com comandos ou intenções diferentes.  
   > Isso acontece porque o modelo tenta associar a frase a um padrão conhecido, mesmo quando se trata apenas de uma saudação coloquial.


4. **Ação e Resposta:**  
   O bot executa a ação correspondente — buscar dados, responder, chamar API, etc.  
   Depois, envia a resposta gerada pelo módulo de NLG (geração de linguagem natural).

---

## 🧠 Tipos de Motores de Decisão

| Tipo | Descrição | Exemplo de Uso |
|------|------------|----------------|
| **Baseado em Regras** | Usa lógica simples (if/else, fluxogramas). | Chatbots de FAQ. |
| **Baseado em IA** | Usa machine learning para escolher respostas. | Assistentes inteligentes (ex: ChatGPT). |
| **Híbrido** | Combina regras e IA. | Chatbots empresariais que lidam com múltiplas situações. |

---

## 🔍 Exemplo de Fluxo Simples (Baseado em Regras)

```pseudo
Se intenção = "ver pedido"
    Mostrar rastreamento
Senão se intenção = "reclamar produto"
    Encaminhar para suporte humano
Senão
    Responder: "Desculpe, não entendi. Pode reformular?"
