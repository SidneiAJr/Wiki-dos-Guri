# 🧠 Tutorial — Validação de Campos no Visual Studio (C#)

## 🎯 Objetivo
Evitar erros de entrada de dados verificando se os campos estão preenchidos corretamente.

---

## ✅ Exemplo 1 — Campo Obrigatório
```csharp
if (string.IsNullOrWhiteSpace(txtNome.Text))
{
    MessageBox.Show("Por favor, preencha o nome!");
    return;
}
```
| 🧩 **Método** | 🎯 **Verifica** | 💡 **Descrição** | ✅ **Recomendado** |
|----------------|----------------|------------------|--------------------|
| `string.IsNullOrEmpty()` | Nulo **ou** vazio (`""`) | Verifica se o campo está sem texto | ✅ Sim |
| `string.IsNullOrWhiteSpace()` | Nulo, vazio **ou apenas espaços** | Mais completo, ignora espaços em branco | ✅✅ Melhor opção |
| `txtCampo.Text == ""` | Apenas vazio (`""`) | Simples, mas não detecta espaços | ⚠️ Limitado |
