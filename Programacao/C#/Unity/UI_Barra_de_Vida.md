# ❤️ Barra de Vida (UI na Unity)

## 🎯 Objetivo
Criar uma barra de vida que diminui quando o jogador sofre dano.

---

## 🧱 Passos

1. Crie um **Slider** no Canvas (UI → Slider).  
2. Renomeie para `BarraVida`.  
3. No Inspector, desative o texto numérico e altere a cor da barra.

---

## ⚙️ Script

```csharp
using UnityEngine;
using UnityEngine.UI;

public class VidaJogador : MonoBehaviour
{
    public Slider barraVida;
    public float vidaAtual = 100;
    public float vidaMax = 100;

    void Start()
    {
        barraVida.maxValue = vidaMax;
        barraVida.value = vidaAtual;
    }

    public void TomarDano(float dano)
    {
        vidaAtual -= dano;
        barraVida.value = vidaAtual;
        if (vidaAtual <= 0)
        {
            Debug.Log("Jogador morreu!");
        }
    }
}
```
---

### 💡 4. `Unity_Fisica_Colisoes.md`
➡️ Explica **colisões e triggers**, essenciais para gameplay:

- Diferença entre `OnCollisionEnter` e `OnTriggerEnter`
- Uso de colliders e rigidbodies
- Detecção de colisões com tags e layers

```markdown
void OnCollisionEnter(Collision colisao)
{
    if (colisao.gameObject.CompareTag("Inimigo"))
        Debug.Log("Colidiu com inimigo!");
}
```
