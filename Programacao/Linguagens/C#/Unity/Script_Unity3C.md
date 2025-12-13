# 🎮 Unity — Scripts Essenciais em C#

> 💡 Este guia reúne os principais scripts usados em jogos feitos com Unity.  
> Cada script está comentado para fácil entendimento e pode ser usado como base para seus próprios projetos.

---

## 🧍 PlayerController.cs — Movimento do Jogador

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;
    private CharacterController controller;

    void Start()
    {
        controller = GetComponent<CharacterController>();
    }

    void Update()
    {
        float moveX = Input.GetAxis("Horizontal");
        float moveZ = Input.GetAxis("Vertical");

        Vector3 direction = new Vector3(moveX, 0, moveZ);
        controller.Move(direction * speed * Time.deltaTime);

        // Movimento alternativo por teclas
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
using UnityEngine;
using UnityEngine.UI;
using TMPro;
using System.Collections;

public class PlayerStats : MonoBehaviour
{
    public int maxHealth = 100;
    public int currentHealth;
    public int score = 0;
    public int munition = 10;
    public int armor = 10;

    public Slider healthBar;
    public TMP_Text scoreText;
    public Image healthBarFill;

    private Color originalColor;
    private bool isFlashing = false;
    private float flashDuration = 0.2f;

    void Start()
    {
        currentHealth = maxHealth;
        healthBar.maxValue = maxHealth;
        healthBar.value = currentHealth;
        originalColor = healthBarFill.color;
        UpdateScoreText();
    }

    public void TakeDamage(int damage)
    {
        currentHealth -= damage;
        healthBar.value = currentHealth;

        if (currentHealth > 0 && !isFlashing)
            StartCoroutine(FlashRed());
    }

    public void AddArmor(int value)
    {
        armor += value;
        UpdateScoreText();
    }

    public void AddScore(int value)
    {
        score += value;
        UpdateScoreText();
    }

    public void AddMunition(int value)
    {
        munition += value;
        UpdateScoreText();
    }

    void UpdateScoreText()
    {
        scoreText.text = $"Pontuação: {score}";
    }

    private IEnumerator FlashRed()
    {
        isFlashing = true;
        healthBarFill.color = Color.red;
        yield return new WaitForSeconds(flashDuration);
        healthBarFill.color = originalColor;
        isFlashing = false;
    }
}
```
## 🧠 EnemyAI.cs — Inimigo que Persegue o Jogador
```C#
using UnityEngine;
using UnityEngine.AI;

public class EnemyAI : MonoBehaviour
{
    public Transform player;
    private NavMeshAgent agent;

    void Start()
    {
        agent = GetComponent<NavMeshAgent>();
    }

    void Update()
    {
        agent.SetDestination(player.position);
    }
}
```
## Enemy.cs — Inimigo Que Dá Dano
```C#
using UnityEngine;

public class Enemy : MonoBehaviour
{
    public int damage = 10;

    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Player"))
        {
            PlayerStats player = collision.gameObject.GetComponent<PlayerStats>();
            player.TakeDamage(damage);
        }
    }
}
```

## 🪙 Collectable.cs — Coletar Moedas ou Itens
using UnityEngine;
```C#
public class Collectable : MonoBehaviour
{
    public int value = 10;

    private void OnTriggerEnter(Collider other)
    {
        if (other.CompareTag("Player"))
        {
            PlayerStats player = other.GetComponent<PlayerStats>();
            player.AddScore(value);
            Destroy(gameObject);
        }
    }
}
```

## PlayerShoot.cs — Sistema de Tiro com Munição
using UnityEngine;
```C#
public class PlayerShoot : MonoBehaviour
{
    public GameObject bulletPrefab;
    public Transform firePoint;
    public float bulletSpeed = 20f;
    private PlayerStats stats;

    void Start()
    {
        stats = GetComponent<PlayerStats>();
    }

    void Update()
    {
        if (Input.GetButtonDown("Fire1") && stats.munition > 0)
        {
            Shoot();
        }
    }

    void Shoot()
    {
        GameObject bullet = Instantiate(bulletPrefab, firePoint.position, firePoint.rotation);
        bullet.GetComponent<Rigidbody>().velocity = firePoint.forward * bulletSpeed;
        stats.munition--;
    }
}
```
## 🔘 Bullet.cs — Script da Bala
```C#
using UnityEngine;

public class Bullet : MonoBehaviour
{
    public float lifetime = 3f;
    public int damage = 10;

    void Start()
    {
        Destroy(gameObject, lifetime);
    }

    void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Enemy"))
        {
            Destroy(collision.gameObject);
            Destroy(gameObject);
        }
    }
}
```

## 🎥 CameraFollow.cs — Câmera que Segue o Jogador
```C#
using UnityEngine;

public class CameraFollow : MonoBehaviour
{
    public Transform player;
    public Vector3 offset;
    public float smoothSpeed = 0.125f;

    void LateUpdate()
    {
        Vector3 desiredPosition = player.position + offset;
        Vector3 smoothed = Vector3.Lerp(transform.position, desiredPosition, smoothSpeed);
        transform.position = smoothed;
    }
}
```
## 🧾 Menu.cs — Menu Principal
```C#
using UnityEngine;
using UnityEngine.SceneManagement;

public class Menu : MonoBehaviour
{
    public void StartGame()
    {
        SceneManager.LoadScene("GameScene");
    }

    public void QuitGame()
    {
        Application.Quit();
    }
}
```

## 💡 UIManager.cs — Atualizar Vida, Munição e Pontuação
```C#
using UnityEngine;
using TMPro;
using UnityEngine.UI;

public class UIManager : MonoBehaviour
{
    public TMP_Text scoreText;
    public TMP_Text ammoText;
    public Slider healthBar;

    public void UpdateUI(PlayerStats stats)
    {
        scoreText.text = "Score: " + stats.score;
        ammoText.text = "Munição: " + stats.munition;
        healthBar.value = stats.currentHealth;
    }
}
```

## 💾 GameManager.cs — Gerenciamento Geral do Jogo
```C#
using UnityEngine;

public class GameManager : MonoBehaviour
{
    public static GameManager instance;
    public PlayerStats playerStats;
    public UIManager uiManager;

    void Awake()
    {
        instance = this;
    }

    void Update()
    {
        uiManager.UpdateUI(playerStats);
    }
}
```
