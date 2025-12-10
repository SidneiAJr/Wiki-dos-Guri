# 🧱 Componentes da Unity

## 🧭 Introdução
Na Unity, **tudo é um GameObject**.  
O comportamento e aparência de cada objeto são definidos pelos **componentes** que ele possui.

---

## ⚙️ Principais Componentes

| Componente | Função | Exemplo |
|-------------|--------|----------|
| **Transform** | Controla posição, rotação e escala | Mover um objeto no cenário |
| **Rigidbody** | Adiciona física (gravidade, colisão realista) | Fazer uma bola cair |
| **Collider** | Detecta colisões com outros objetos | BoxCollider, SphereCollider |
| **Renderer** | Mostra o objeto na tela | Renderizar modelos e sprites |
| **Animator** | Controla animações | Anima personagem ou UI |
| **Camera** | Define o ponto de visão | Exibir a cena ao jogador |
| **Light** | Ilumina a cena | SpotLight, Directional Light |
| **AudioSource** | Toca sons e músicas | Efeitos de passos e explosões |

---

## 🧩 Exemplo de Uso

```csharp
using UnityEngine;

public class Bola : MonoBehaviour
{
    public float forca = 5f;
    Rigidbody rb;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            rb.AddForce(Vector3.up * forca, ForceMode.Impulse);
        }
    }
}
```

---


