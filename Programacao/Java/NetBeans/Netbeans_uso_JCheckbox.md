# ☑️ Tutorial de Uso do JCheckBox no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE** no seu computador.

## 🧱 Passo 2: Criar um novo JFrame
Siga o mesmo processo de criação de JFrame dos tutoriais anteriores.

## 🔘 Passo 3: Inserir o JCheckBox
1. Na aba **Palette**, procure por **Check Box** (ou `JCheckBox`).  
2. Arraste o componente para dentro do JFrame.

## ⚙️ Passo 4: Configurar Propriedades
1. Clique no **JCheckBox**.  
2. Vá até **Properties** e altere:
   - **text:** texto exibido (ex: `Receber notificações`)  
   - **font / colors:** aparência  
   - **toolTipText:** dica  

## 💡 Passo 5: Verificar se está Marcado
Para saber se a caixa está selecionada:
```java
if (chkNotificacoes.isSelected()) {
    System.out.println("Notificações ativadas!");
} else {
    System.out.println("Notificações desativadas!");
}
