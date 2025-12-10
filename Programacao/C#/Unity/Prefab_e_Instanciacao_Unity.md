# 🧠 **Unity_Interfaces_UI.md**  
(com **Slider** e **Image** incluídos 👇)


## 🧠 Interface (UI) na Unity — Botões, Sliders e Imagens

## 🧭 Introdução
A UI (Interface do Usuário) permite interagir com o jogo: menus, barras de vida, botões e textos.  
Tudo é criado dentro de um **Canvas**.

---

## 🪟 Elementos principais

| Elemento | Função | Exemplo |
|-----------|--------|----------|
| **Canvas** | Base da interface | Contém todos os elementos UI |
| **Text / TextMeshPro** | Mostra texto na tela | Pontuação, mensagens |
| **Button** | Executa ações com clique | Iniciar jogo, sair |
| **Image** | Exibe figuras ou ícones | Barra de vida, fundo |
| **Slider** | Representa um valor contínuo | Volume, progresso, energia |

---

## 🎛️ Exemplo — Slider controlando volume

```csharp
using UnityEngine;
using UnityEngine.UI;

public class ControleVolume : MonoBehaviour
{
    public Slider slider;
    public AudioSource musica;

    void Start()
    {
        slider.onValueChanged.AddListener(AjustarVolume);
    }

    void AjustarVolume(float valor)
    {
        musica.volume = valor;
    }
}
```
