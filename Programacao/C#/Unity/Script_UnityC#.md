## 💡 Criando um Script C#

1. Clique com o botão direito na pasta **Scripts** → **Create → C# Script**
2. Dê um nome (ex: `PlayerController.cs`)
3. Clique duas vezes para abrir no **Visual Studio** ou **VS Code**
4. Arraste o script para o seu objeto “Player” na Hierarchy.

---

### 🧠 Exemplo básico de movimentação com `Rigidbody`

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;     // Velocidade de movimento
    private Rigidbody rb;        // Referência ao Rigidbody do jogador

    void Start()
    {
        // Pega o componente Rigidbody anexado ao jogador
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        // Captura o input do teclado (setas/WASD)
        float moveX = Input.GetAxis("Horizontal");
        float moveZ = Input.GetAxis("Vertical");

        // Cria um vetor de movimento
        Vector3 movement = new Vector3(moveX, 0, moveZ);

        // Move o jogador suavemente usando física
        rb.MovePosition(transform.position + movement * speed * Time.deltaTime);
    }
}
