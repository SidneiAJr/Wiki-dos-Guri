# 🎮 Script de Movimentação do Jogador (Unity C#)

Este script demonstra duas formas diferentes de controlar o movimento de um jogador na Unity:
1. Usando **CharacterController** (movimentação suave com colisão).
2. Usando **Input.GetKey()** (movimentação direta do objeto).

---

## 🧱 Configuração no Unity

1. Crie um objeto chamado **Player** na Hierarchy.  
2. Adicione um **CharacterController** no componente do Player.  
3. Crie uma pasta chamada **Scripts** → Clique com o botão direito → *Create → C# Script* → nomeie como `PlayerController.cs`.  
4. Cole o código abaixo e salve.  
5. Arraste o script para o objeto **Player**.

---

## 💡 Script Completo (`PlayerController.cs`)

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;                     // Velocidade de movimento
    private CharacterController controller;      // Referência ao CharacterController

    void Start()
    {
        // Obtém o componente CharacterController anexado ao jogador
        controller = GetComponent<CharacterController>();
    }

    void Update()
    {
        // ======== MODO 1: Movimentação com CharacterController ========
        float moveX = Input.GetAxis("Horizontal");
        float moveZ = Input.GetAxis("Vertical");

        Vector3 direction = new Vector3(moveX, 0, moveZ);
        controller.Move(direction * speed * Time.deltaTime);

        // ======== MODO 2: Movimentação direta com Input.GetKey ========
        if (Input.GetKey(KeyCode.W))
            transform.Translate(Vector3.forward * speed * Time.deltaTime);

        if (Input.GetKey(KeyCode.S))
            transform.Translate(Vector3.back * speed * Time.deltaTime);

        if (Input.GetKey(KeyCode.A))
            transform.Translate(Vector3.left * speed * Time.deltaTime);

        if (Input.GetKey(KeyCode.D))
            transform.Translate(Vector3.right * speed * Time.deltaTime);
    }
}
