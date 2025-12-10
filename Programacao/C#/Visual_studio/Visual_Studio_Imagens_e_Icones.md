# 🖼️ Tutorial — Inserindo Imagens e Ícones no Visual Studio (C#)

## 🎯 Objetivo
Aprender a adicionar **imagens e ícones** em botões, formulários e outros componentes no **Windows Forms**.

---

## 🧩 1️⃣ Adicionando Imagem a um Botão

1. Selecione o botão no formulário.  
2. No painel **Properties**, procure a propriedade **Image**.  
3. Clique no botão **[...]** → **Importar Imagem**.  
4. Escolha uma imagem `.png` ou `.ico` da pasta do projeto (ex: `Resources/icone.png`).  
5. Altere:
   - `ImageAlign` → `MiddleLeft`
   - `TextAlign` → `MiddleRight`
   - `TextImageRelation` → `ImageBeforeText`

---

### Exemplo em Código
```csharp
botaoSalvar.Image = Image.FromFile("C:\\imagens\\save.png");
botaoSalvar.Text = "Salvar";
botaoSalvar.TextImageRelation = TextImageRelation.ImageBeforeText;
