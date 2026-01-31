# 🧰 Tutorial — Criando Barras de Ferramentas com ToolStrip no Visual Studio (C#)

## 🎯 Objetivo
Aprender a criar uma **barra de ferramentas (ToolStrip)** com botões, ícones e ações rápidas em aplicativos **Windows Forms**.

---

## 🧱 1️⃣ O que é o ToolStrip?

O **ToolStrip** é uma barra horizontal que pode conter **botões, menus, caixas de texto e separadores** — muito usado para atalhos de ações como *Salvar*, *Abrir* ou *Sair*.

---

## ⚙️ 2️⃣ Criando um ToolStrip

### Passos:
1. Abra o **Visual Studio** → **Windows Forms App (.NET Framework)**  
2. No painel **Toolbox**, procure por **ToolStrip**  
3. Arraste o componente até o formulário (geralmente ele fica logo abaixo do menu)  
4. Clique no botão de **seta (∨)** no canto direito do ToolStrip e escolha:
   - **Insert Standard Items** → adiciona ícones padrão (Novo, Abrir, Salvar etc.)
   - ou adicione manualmente clicando em **Add Button**

---

## 🧩 3️⃣ Adicionando e Configurando Botões

1. Clique sobre o `ToolStripButton` adicionado  
2. No painel **Properties**, configure:
   - `Text` → Nome visível (ex: "Salvar")
   - `Image` → Escolha um ícone (pode usar imagens `.png`)
   - `DisplayStyle` → `ImageAndText` (para mostrar ambos)

---

## 🧠 4️⃣ Criando Eventos dos Botões

Dê **duplo clique** em um botão para criar o evento `Click`.

Exemplo:
```csharp
private void toolStripButtonSalvar_Click(object sender, EventArgs e)
{
    MessageBox.Show("Arquivo salvo com sucesso!");
}
