# Unity C# - Player Stats Script

```csharp
using UnityEngine;
using UnityEngine.UI;
using TMPro; // Para usar TextMeshPro
using System.Collections;

public class PlayerStats : MonoBehaviour
{
    // ==============================
    // Variáveis principais
    // ==============================
    public int maxHealth = 100;      // Vida máxima do jogador
    public int currentHealth;        // Vida atual
    public int score = 0;            // Pontuação do jogador
    public Slider healthBar;         // Referência à barra de vida (UI Slider)
    public TMP_Text scoreText;       // Referência ao texto da pontuação
    public Image healthBarFill;      // Parte preenchida da barra de vida

    private Color originalColor;     // Cor original da barra de vida
    private bool isFlashing = false; // Controle do efeito de flash
    private float flashDuration = 0.2f; // Duração do flash
    public int munition;             // Munição do jogador
    private int ammo_Muni;           // Armazena munição inicial
    private int Armor;               // Armadura do jogador
    private int base_armor;          // Armadura base inicial

    // ==============================
    // Inicialização
    // ==============================
    void Start()
    {
        munition = 10;               // Define munição inicial
        Armor = 10;                  // Define armadura inicial
        ammo_Muni = munition;        // Armazena valor inicial da munição
        currentHealth = maxHealth;   // Vida inicial = vida máxima
        healthBar.maxValue = maxHealth;
        healthBar.value = currentHealth;

        originalColor = healthBarFill.color; // Salva cor original da barra
        base_armor = Armor;

        UpdateScoreText();           // Atualiza texto da pontuação
    }

    // ==============================
    // Recebe dano
    // ==============================
    public void TakeDamage(int damage)
    {
        currentHealth -= damage;     // Subtrai dano da vida
        //currentHealth = Mathf.Clamp(currentHealth, 0, maxHealth); // opcional para limitar

        healthBar.value = currentHealth; // Atualiza barra de vida

        // Inicia flash vermelho se o jogador está vivo e não está piscando
        if(currentHealth > 0 && !isFlashing)
        {
           StartCoroutine(FlashRed());
        }
    }

    // ==============================
    // Adiciona armadura
    // ==============================
    public void Addarmor(int armadura)
    {
      Armor += armadura;
      UpdateScoreText();
    }

    // ==============================
    // Adiciona pontuação
    // ==============================
    public void AddScore(int points)
    {
        score += points;
        UpdateScoreText();
    }

    // ==============================
    // Adiciona munição
    // ==============================
    public void Addmunition(int cartucho)
    {
        munition += cartucho;
        UpdateScoreText();
    }

    // ==============================
    // Atualiza o texto da pontuação
    // ==============================
    void UpdateScoreText()
    {
        scoreText.text = "Pontuação: " + score;
    }

    // ==============================
    // Efeito de flash vermelho na barra de vida
    // ==============================
    private IEnumerator FlashRed()
    {
        isFlashing = true;
        healthBarFill.color = Color.red;       // Muda cor para vermelho
        yield return new WaitForSeconds(flashDuration); // Espera duração do flash
        healthBarFill.color = originalColor;   // Retorna cor original
        isFlashing = false;
    }
}
