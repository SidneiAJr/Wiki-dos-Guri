# 🎮 Godot Engine

> Documentação e anotações pessoais sobre **Godot**, o engine open-source para desenvolvimento de jogos 2D e 3D.

---

## 🧩 Sobre o Godot

O **Godot Engine** é uma engine gratuita e open-source usada para criar jogos em **2D**, **3D** e até aplicações interativas.  
É conhecido por sua leveza, flexibilidade e por usar a linguagem **GDScript** (baseada em Python), além de suportar **C#, C++ e VisualScript**.

---

## ⚙️ Recursos Principais

- 🌍 **Multiplataforma** — exporta para Windows, Linux, macOS, Web, Android e iOS.  
- 🧠 **GDScript** — linguagem fácil e poderosa inspirada em Python.  
- 🎨 **Editor visual completo** — interface intuitiva com nós, cenas e sinalização.  
- 🧱 **Sistema de Nodes e Scenes** — estrutura modular e escalável.  
- 🔊 **Suporte a áudio e física** integrados.  
- 🕹️ **Input system** avançado (gamepads, teclado, mouse, toques).  
- 🧩 **Extensível com C# e C++** — ideal pra performance e customização.  

---
# ⚖️ Comparativo de Linguagens na Godot Engine

> Diferenças principais entre **GDScript**, **C# (.NET)** e **C++ (GDExtension)** dentro do ecossistema da Godot.

---

## 🧩 Tabela Comparativa

| 🧠 Recurso / Aspecto | 🐍 **GDScript** | ⚙️ **C# (.NET / Mono)** | ⚡ **C++ (GDExtension / GDNative)** |
|:--|:--|:--|:--|
| 🏗️ **Tipo de Linguagem** | Interpretada, dinâmica (similar ao Python) | Compilada JIT (tipagem estática) | Compilada nativa (alta performance) |
| 💡 **Integração com Godot** | Nativa — feita especialmente pra engine | Alta — via runtime .NET integrado | Avançada — requer configuração e compilação |
| ⚙️ **Desempenho** | Muito bom (otimizado pra scripts) | Alto (JIT + tipagem forte) | Máximo (execução direta em máquina) |
| 🔤 **Sintaxe** | Simples e legível (estilo Python) | Verbosa e estruturada (estilo C#) | Complexa, com headers e builds |
| 🧱 **Curva de Aprendizado** | Fácil — ideal pra iniciantes | Média — exige noção prévia de C# / OO | Difícil — voltada pra devs experientes |
| 🔄 **Velocidade de Iteração** | Alta — salvar e rodar direto | Média — scripts compilam no build | Baixa — precisa recompilar o projeto |
| 🧰 **Ferramentas Externas** | Editor interno do Godot | Visual Studio / VS Code | CLion / Visual Studio / Makefile |
| 🧩 **Uso Ideal** | Lógica de jogo, protótipos, UI | Projetos médios/grandes com estrutura robusta | Extensões, módulos e desempenho máximo |
| 🧠 **Paradigma Principal** | Orientado a objetos, mas simples | Orientado a objetos completo | Orientado a objetos e baixo nível |
| 🧩 **Suporte a Tipagem Estática** | Opcional (desde Godot 4) | Sim, nativamente | Sim, nativamente |
| 🧩 **Compatibilidade Multiplataforma** | Total (2D, 3D, Web, Mobile) | Alta (dependente do .NET SDK) | Total (mas requer build específico por SO) |
| 🧩 **Acesso à API da Engine** | Completo, direto e integrado | Completo (via bindings C#) | Total (via ponte GDExtension) |
| 🧩 **Requer SDK externo** | ❌ Não | ✅ Sim (.NET SDK) | ✅ Sim (toolchain C++ e Godot headers) |
| 📚 **Documentação e Comunidade** | Ampla e oficial | Boa (crescendo com Godot .NET) | Avançada, voltada pra devs experientes |
| 🧩 **Exemplo de Uso Ideal** | Jogo indie 2D / protótipo rápido | RPG, simulação, apps complexos | Engine customizada, física, IA nativa |
| 🧩 **Arquivo de Script** | `.gd` | `.cs` | `.cpp` / `.h` |
| 🧩 **Forma de Execução** | Interpretado pelo runtime da Godot | Compilado pelo .NET no runtime | Compilado e linkado como módulo nativo |

---

## 💬 **Resumo**

| Situação | Linguagem Ideal |
|:--|:--|
| 🧩 Iniciando na Godot ou quer aprender rápido | **GDScript** |
| ⚙️ Já programa em C# / Unity | **C# (Godot .NET)** |
| ⚡ Precisa de máximo desempenho ou engine custom | **C++ (GDExtension)** |

---

> 📘 *Dica:*  
> Se o objetivo é aprender **game logic, design e fluxo da Godot**, começa com **GDScript**.  
> Depois, se quiser robustez e integração com o .NET, migra pra **C#**.  
> E se quiser chegar no “nível motor”, brinca com **C++**.

---

---

## 🧠 Comandos e Dicas

### Executar o projeto
```bash
godot -e
