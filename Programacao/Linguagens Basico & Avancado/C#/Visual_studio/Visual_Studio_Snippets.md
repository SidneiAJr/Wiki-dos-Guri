# ⚡ Snippets no Visual Studio (atalhos automáticos de código)

Os **snippets** do Visual Studio são atalhos de escrita que expandem em blocos de código prontos,  
sem precisar digitar tudo manualmente — igual ao `sout` do Java.

---

## 🧠 Snippets mais usados em C#

| Comando digitado | Pressione `Tab` + `Tab` | Resultado |
|------------------|--------------------------|------------|
| `cw` | ✅ | Expande para `Console.WriteLine();` *(equivalente ao `sout` do Java)* |
| `for` | ✅ | Cria um laço `for` completo com índice padrão (`for (int i = 0; i < length; i++) { }`) |
| `foreach` | ✅ | Gera um loop `foreach` automático |
| `if` | ✅ | Cria estrutura `if () { }` |
| `else` | ✅ | Cria bloco `else { }` |
| `try` | ✅ | Cria bloco `try { } catch (Exception ex) { }` |
| `prop` | ✅ | Cria uma propriedade (`public int Id { get; set; }`) |
| `ctor` | ✅ | Gera construtor padrão (`public ClassName() { }`) |
| `switch` | ✅ | Cria estrutura de `switch` completa |
| `do` | ✅ | Cria laço `do { } while ();` |
| `while` | ✅ | Cria laço `while () { }` |

---

## 💡 Dica extra

Se quiser ver **todos os snippets disponíveis**, digita qualquer coisa no editor e aperta:
> `Ctrl + K`, depois `Ctrl + X`  
> *(abre o menu de inserção de snippet, mostrando todos os disponíveis para C#).*

Ou ainda:
> `Ctrl + K`, depois `Ctrl + S`  
> *(permite envolver código com estruturas — tipo try/catch, region, etc.)*

---

## 🧩 Criar snippets personalizados
Você pode criar seus próprios atalhos:
1. Vá em **Tools → Code Snippets Manager...** (`Ctrl + K`, `Ctrl + B`)
2. Escolha **Language: C#**
3. Clique em **Add…** e selecione sua pasta de snippets personalizados (`.snippet`)
4. Agora seu atalho vai funcionar igual os nativos!

---

💬 **Exemplo:**
Você pode criar um snippet chamado `log` que expande pra:
```csharp
Console.WriteLine("Log: " + DateTime.Now);
```
