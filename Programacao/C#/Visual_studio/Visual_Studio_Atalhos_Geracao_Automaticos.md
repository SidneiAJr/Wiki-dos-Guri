# ⚙️ Atalhos de Geração Automática no Visual Studio  
*(Equivalentes ao “Alt + Insert” do NetBeans)*

O **Visual Studio** possui recursos de geração automática de código que substituem o famoso atalho  
`Alt + Insert` do NetBeans.  
Esses comandos aceleram a criação de **construtores, propriedades, métodos, overrides** e muito mais.

---

## 🧠 Principais Atalhos

| Função | Atalho | Descrição |
|--------|---------|-----------|
| **Quick Actions / Sugestões automáticas** | `Ctrl + .` *(ponto)* | Abre o menu de ações rápidas — permite gerar construtores, propriedades, implementar interfaces, corrigir erros e refatorar código. |
| **Implementar interface / override** | `Ctrl + .` ou `Alt + Enter` | Mostra métodos herdados que podem ser sobrescritos ou implementados. |
| **Gerar propriedade rapidamente** | Digite `prop` → pressione `Tab` + `Tab` | Cria automaticamente um *property block*: `public int Id { get; set; }`. |
| **Gerar construtor** | Digite `ctor` → pressione `Tab` + `Tab` | Cria instantaneamente um construtor vazio dentro da classe. |
| **Criar método padrão** | Digite `m` → pressione `Tab` + `Tab` *(se habilitado nos snippets)* | Cria um método rapidamente. |
| **Gerar override** | Digite `override` → selecione da lista → `Tab` | Mostra todos os métodos herdados disponíveis para sobrescrever. |
| **Envolver com try/catch** | Selecione o código → `Ctrl + K` → `Ctrl + S` → digite `try` → Enter | Envolve o trecho selecionado em um bloco `try/catch`. |
| **Refatoração rápida (rename, extract, etc.)** | `Ctrl + R`, depois `R` ou `M` | Abre o menu de refatoração para renomear, extrair métodos ou mover código. |

---

## 💡 Dica: Menu de Contexto

Outra forma de acessar o mesmo recurso:
1. Clique com o **botão direito** sobre a variável ou classe.  
2. Escolha **Quick Actions and Refactorings...** *(ou use `Ctrl + .`)*  
3. Selecione **Generate Constructor / Properties / Equals / ToString / etc.**

---

## 🧩 Extensão ReSharper (opcional)

Se quiser a **mesma experiência do NetBeans (Alt + Insert)** no Visual Studio,  
instale a extensão **ReSharper** (da JetBrains).  
Após instalada, o atalho é idêntico:

> `Alt + Insert` → *Generate → Constructor / Properties / Equals / ToString / etc.*

---


