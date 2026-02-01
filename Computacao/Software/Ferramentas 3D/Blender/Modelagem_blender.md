# 🧱 Modelagem no Blender — Guia Essencial

A **modelagem 3D** é o processo de criar e moldar objetos dentro do Blender.  
Aqui você aprende as principais ferramentas, atalhos e boas práticas para criar qualquer tipo de modelo.

---

## ✨ 1. Modos de Trabalho

| Modo | Função |
|------|---------|
| **Object Mode** | Manipular objetos completos (mover, rotacionar, escalar) |
| **Edit Mode** | Editar vértices, arestas e faces |
| **Sculpt Mode** | Esculpir com pincéis (detalhes orgânicos) |

Use **Tab** para alternar entre *Object Mode* e *Edit Mode*.

---

## 🧰 2. Ferramentas Básicas de Modelagem

| Ação | Atalho | Descrição |
|------|---------|-----------|
| Adicionar objeto | `Shift + A` | Adiciona primitivos (cubos, esferas, planos etc.) |
| Mover | `G` | Move o objeto |
| Rotacionar | `R` | Gira o objeto |
| Escalar | `S` | Muda o tamanho |
| Duplicar | `Shift + D` | Cria cópia do objeto |
| Excluir | `X` | Remove o objeto |
| Centralizar | `Alt + G` | Zera a posição |

💡 **Dica:** Combine com eixos, como `G + Z` (mover no eixo Z).

---

## ✂️ 3. Ferramentas do Edit Mode

| Ação | Atalho | Descrição |
|------|---------|-----------|
| Extrudar | `E` | Cria novas faces a partir da seleção |
| Inserir Loop Cut | `Ctrl + R` | Adiciona divisões na malha |
| Cortar Faces (Knife) | `K` | Faz cortes personalizados |
| Mesclar vértices | `M` | Junta pontos selecionados |
| Espelhar | `Ctrl + M` | Inverte o modelo em um eixo |
| Apagar faces | `X` | Remove vértices, arestas ou faces |

---

## 🧩 4. Modificadores Importantes

| Modificador | Função |
|--------------|--------|
| **Mirror** | Simetria perfeita em um eixo |
| **Subdivision Surface** | Suaviza e aumenta o número de polígonos |
| **Bevel** | Arredonda bordas |
| **Array** | Duplica objetos em sequência |
| **Boolean** | Corta ou une objetos (união, diferença, interseção) |
| **Solidify** | Dá espessura a superfícies planas |

⚠️ **Atenção:** Antes de exportar, aplique modificadores com `Ctrl + A → Apply All Transforms`.

---

## 🧱 5. Boas Práticas

- Trabalhe em **escala real** (ex: 1 unidade = 1 metro).  
- Mantenha **topologia limpa** (sem triângulos ou n-gons sempre que possível).  
- Nomeie objetos e coleções corretamente.  
- Use **Modifiers** não destrutivos antes de aplicar.

---


