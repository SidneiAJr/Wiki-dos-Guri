# ⚡️ Atalhos de Código Avançados no Android Studio

O Android Studio herda os atalhos do IntelliJ IDEA, oferecendo templates de código prontos e comandos rápidos que aumentam muito a produtividade.

---

## 🧩 **Code Templates (Abreviações + Tab)**

Esses são os equivalentes aos "sou", "psvm" e outros do NetBeans.

| Atalho | Expansão | Descrição |
|:--------|:-----------|:-----------|
| **psvm** | `public static void main(String[] args) {}` | Cria o método principal (em classes Java padrão). |
| **sout** | `System.out.println();` | Imprime texto no console. |
| **logd** | `Log.d(TAG, "mensagem");` | Log de depuração (Debug). |
| **logi** | `Log.i(TAG, "mensagem");` | Log informativo. |
| **logw** | `Log.w(TAG, "mensagem");` | Log de aviso (Warning). |
| **loge** | `Log.e(TAG, "mensagem");` | Log de erro. |
| **logt** | `private static final String TAG = "NomeClasse";` | Cria a constante `TAG` padrão para logs. |
| **Toast** | `Toast.makeText(context, "mensagem", Toast.LENGTH_SHORT).show();` | Mostra uma mensagem Toast na tela. |
| **Toastl** | `Toast.makeText(context, "mensagem", Toast.LENGTH_LONG).show();` | Toast com duração longa. |
| **fbc** | `findViewById(R.id.elemento);` | Recupera uma View pelo ID. |
| **rvsetup** | Cria estrutura básica de RecyclerView (template customizado). |
| **snack** | `Snackbar.make(view, "mensagem", Snackbar.LENGTH_SHORT).show();` | Cria um Snackbar (material design). |

---

## 💡 **Templates XML**

| Atalho | Expansão | Descrição |
|:--------|:-----------|:-----------|
| **Linear** | `<LinearLayout ...></LinearLayout>` | Cria um LinearLayout rapidamente. |
| **Relative** | `<RelativeLayout ...></RelativeLayout>` | Cria um RelativeLayout. |
| **Constraint** | `<androidx.constraintlayout.widget.ConstraintLayout ...></androidx.constraintlayout.widget.ConstraintLayout>` | Cria um ConstraintLayout. |
| **TextView** | `<TextView ... />` | Insere um TextView com atributos padrão. |
| **Button** | `<Button ... />` | Insere um botão básico. |
| **ImageView** | `<ImageView ... />` | Insere uma imagem. |
| **RecyclerView** | `<androidx.recyclerview.widget.RecyclerView ... />` | Insere um RecyclerView. |

---

## ⚙️ **Atalhos de Edição e Navegação (Java/Kotlin)**

| Atalho | Função |
|:--------|:--------|
| **Ctrl + Espaço** | Auto-complete. |
| **Ctrl + P** | Mostra parâmetros esperados de um método. |
| **Ctrl + Q** | Mostra a documentação do símbolo. |
| **Alt + Enter** | Mostra sugestões e correções rápidas. |
| **Ctrl + /** | Comenta/descomenta linha. |
| **Ctrl + Shift + A** | Busca qualquer comando do Android Studio. |
| **Ctrl + E** | Mostra arquivos recentes. |
| **Ctrl + Shift + F10** | Executa o app atual. |
| **Shift + F10** | Roda o último app executado. |
| **Shift + F9** | Inicia o depurador (debug). |
| **Ctrl + Alt + L** | Reformatar código. |
| **Ctrl + Alt + O** | Otimiza imports. |
| **Ctrl + B / Ctrl + Click** | Vai para a declaração. |
| **Ctrl + N** | Busca classes. |
| **Ctrl + Shift + N** | Busca arquivos. |
| **Alt + Insert** | Gera código (Getters/Setters/Constructors etc). |

---

## 🧠 **Atalhos Android Específicos**

| Atalho | Função |
|:--------|:--------|
| **Ctrl + Shift + ↑/↓** | Alterna entre Activity e layout XML. |
| **Ctrl + Alt + Home** | Abre o painel do emulador. |
| **Ctrl + F12** | Lista métodos da classe atual. |
| **Alt + F7** | Mostra onde um método/variável é usado. |
| **Ctrl + Shift + F** | Pesquisa global no projeto. |
| **Alt + Enter** | Corrige imports ou adiciona dependências no Gradle. |
| **Ctrl + Alt + Shift + S** | Abre a estrutura do projeto (módulos e SDKs). |

---

## 🧰 **Refatoração e Organização**

| Atalho | Ação |
|:--------|:--------|
| **Shift + F6** | Renomear variável/método/classe. |
| **Ctrl + Alt + M** | Extrair método. |
| **Ctrl + Alt + V** | Extrair variável. |
| **Ctrl + Alt + F** | Extrair campo. |
| **Ctrl + Alt + C** | Extrair constante. |
| **Ctrl + Alt + P** | Extrair parâmetro. |
| **Ctrl + Alt + L** | Reformatar código automaticamente. |

---

## 🔥 **Personalizando Templates**

Você pode criar ou editar seus próprios atalhos indo em:

> `File → Settings → Editor → Live Templates`

Lá dá pra:
- Criar novos **atalhos personalizados** (ex: `toastd`, `rvinit`).
- Usar variáveis automáticas (`$VAR$`, `$END$`, `$CLASS_NAME$`).
- Organizar por linguagem (Java, Kotlin, XML etc).

---

## ✨ **Exemplo de Template Personalizado**

Crie um **template customizado** chamado `toastd` com o código:

```java
Toast.makeText($context$, "$msg$", Toast.LENGTH_SHORT).show();
