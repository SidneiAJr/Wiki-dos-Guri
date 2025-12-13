# 🔘 Tutorial de Uso do JRadioButton no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE** no seu computador.

## 🧱 Passo 2: Criar um novo JFrame
Siga o mesmo processo dos tutoriais anteriores.

## 🎚️ Passo 3: Inserir os JRadioButtons
1. Na **Palette**, procure por **Radio Button** (ou `JRadioButton`).  
2. Arraste **dois ou mais** botões para o JFrame (ex: Masculino / Feminino).

## ⚙️ Passo 4: Configurar Propriedades
1. Altere o **text** de cada botão.  
   - Exemplo: `Masculino`, `Feminino`.  
2. Dê um nome para cada um:
   - `rdbMasculino`, `rdbFeminino`.

## 🧩 Passo 5: Agrupar os Botões
Para que apenas **um** possa ser selecionado:
1. Vá em **Palette → Button Group**.  
2. Arraste o **ButtonGroup** para o JFrame (não aparece visualmente).  
3. No painel **Properties**, selecione cada `JRadioButton` e defina o **buttonGroup** como o grupo criado.

## 💡 Passo 6: Obter a Seleção
```java
if (rdbMasculino.isSelected()) {
    System.out.println("Selecionado: Masculino");
} else if (rdbFeminino.isSelected()) {
    System.out.println("Selecionado: Feminino");
}
