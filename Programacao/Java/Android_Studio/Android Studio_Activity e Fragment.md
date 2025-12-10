# 📱 Android Studio — Activity e Fragment

## 🧩 Introdução

No Android, **Activity** e **Fragment** são os blocos fundamentais da interface e do fluxo de navegação dos aplicativos.  
Eles controlam **o que o usuário vê** e **como ele interage** com a aplicação.

---

## 🪟 Activity — A Tela Principal

Uma **Activity** representa **uma única tela** com interface do usuário.  
Ela é a base de qualquer app Android — como se fosse a “janela principal” do programa.

📘 **Exemplo conceitual:**
- Um app de notas pode ter:
  - Uma `MainActivity` para listar notas.
  - Uma `NoteActivity` para editar ou criar notas.

---

### ⚙️ Ciclo de Vida de uma Activity

O sistema Android gerencia o estado de cada Activity usando **métodos de ciclo de vida**.

| Método | Descrição |
|--------|------------|
| `onCreate()` | Inicializa a Activity (carrega layout, variáveis, etc). |
| `onStart()` | Torna a Activity visível para o usuário. |
| `onResume()` | A Activity está em primeiro plano e ativa. |
| `onPause()` | A Activity está prestes a perder o foco. |
| `onStop()` | A Activity não está mais visível. |
| `onDestroy()` | A Activity está sendo destruída. |

💡 **Dica:** O estado é perdido ao destruir a Activity, então salve dados importantes antes de `onDestroy()`.

---

## 🧱 Fragment — A Parte de uma Tela

Um **Fragment** é um **componente reutilizável** dentro de uma Activity.  
Ele representa **uma parte da interface**, podendo ter seu próprio ciclo de vida e layout.

📘 **Exemplo conceitual:**
- Em um app de notícias:
  - `MainActivity` mostra a lista de notícias.
  - `NewsFragment` exibe o conteúdo da notícia selecionada.

---

### 🧩 Vantagens do uso de Fragments

- Reuso de interface em múltiplas telas.  
- Suporte a layouts dinâmicos (celular, tablet, modo paisagem).  
- Separação de responsabilidades (cada fragment cuida de uma função).  
- Controle mais granular de navegação e transições.

---

### ⚙️ Ciclo de Vida de um Fragment

O ciclo de vida de um fragment é **independente**, mas vinculado à Activity onde ele está inserido.

| Método | Descrição |
|--------|------------|
| `onAttach()` | O fragment é conectado à Activity. |
| `onCreateView()` | Cria e retorna o layout do fragment. |
| `onViewCreated()` | Chamado após o layout ser criado. |
| `onStart()` | O fragment se torna visível. |
| `onResume()` | O fragment está ativo e pronto para interação. |
| `onPause()` | O fragment perde o foco. |
| `onStop()` | O fragment não está mais visível. |
| `onDestroyView()` | O layout do fragment é destruído. |
| `onDetach()` | O fragment é desconectado da Activity. |

---

## 🔄 Comunicação entre Activity e Fragment

As telas podem **compartilhar dados** entre si.  
Existem várias formas de fazer isso:

1. **Via argumentos (Bundle):**
   - A Activity envia dados ao fragment usando um `Bundle`.
2. **Via interface (callback):**
   - O fragment chama métodos definidos na Activity.
3. **Via ViewModel compartilhado:**
   - Permite comunicação reativa entre componentes, ideal no padrão MVVM.

---

## 🧭 Navegação entre Activity e Fragment

Existem dois tipos principais de navegação:

### 🔹 Activity → Activity
Feita via **Intent**:
- `startActivity(Intent)` para abrir outra tela.
- `finish()` para encerrar a atual.

### 🔹 Activity → Fragment
Feita via **FragmentManager**:
- Adiciona, substitui ou remove fragments dinamicamente.
- Pode usar transições e animações entre fragments.

---

## 💡 Boas Práticas

- Use **Activities** para dividir grandes seções do app.  
- Use **Fragments** para telas ou partes que se repetem.  
- Prefira **ViewBinding** ou **DataBinding** para acessar elementos da interface.  
- Utilize **ViewModel + LiveData** para manter dados ao girar a tela.  
- Sempre **salve estado importante** no `onSaveInstanceState()`.

---

## 🧠 Resumo

| Conceito | Função | Arquivo Comum | Ciclo de Vida Próprio |
|-----------|--------|----------------|------------------------|
| Activity | Tela principal do app | `.java` / `.kt` | ✅ |
| Fragment | Parte reutilizável da interface | `.java` / `.kt` + `.xml` | ✅ |

---

## 🔍 Referências Recomendadas

- [Documentação oficial Android — Activities](https://developer.android.com/guide/components/activities)
- [Documentação oficial Android — Fragments](https://developer.android.com/guide/fragments)
- [Arquitetura Android — ViewModel e LiveData](https://developer.android.com/topic/libraries/architecture/viewmodel)

---

📘 *Autor:* Sidnei A. Jr  
📅 *Atualizado:* 31/10/2025  
🏷️ *Categoria:* Android Studio / Estrutura de Aplicações  
