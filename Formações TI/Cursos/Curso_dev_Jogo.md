# 🎮 Curso de Desenvolvedor de Jogos

Durante o curso de **Desenvolvedor de Jogos**, aprendi a criar **jogos do zero**, modelar objetos em **3D** e entender todo o processo de **desenvolvimento de um game**, desde o design até a programação.

---

## 🧩 Conteúdos e Habilidades Aprendidas

- Modelagem 3D e criação de objetos;  
- Criação de jogos completos do zero;  
- Animações e rigging no **Maya**;  
- Animações e integração na **Unity**;  
- Programação em **C#**, tanto comum quanto voltada para **Unity**;  
- Estruturação de **projetos em C#** e boas práticas de desenvolvimento.

---

> 💡 Esse curso me deu uma visão completa do desenvolvimento de jogos — unindo criatividade, lógica e técnica. Foi uma das experiências mais divertidas e produtivas da minha trajetória na área de tecnologia.

---

## Como Criar um Jogo do Zero

Criar um jogo do zero envolve várias etapas, desde a concepção da ideia até a finalização e publicação do produto. O processo básico envolve:

1. **Planejamento e Design**:
   - Definir o estilo do jogo (2D, 3D, gênero, etc.).
   - Criar um conceito de gameplay.
   - Elaborar um design de nível e de interface.
   
2. **Modelagem e Animação**:
   - Modelar personagens, objetos e cenários em **3D** utilizando ferramentas como **Maya**.
   - Criar animações e preparar os assets para serem integrados no motor de jogo.

3. **Desenvolvimento do Jogo**:
   - Utilizar a **Unity** para a integração dos modelos, texturas e animações.
   - Programar a lógica do jogo, como movimentos, interações e eventos usando **C#**.

4. **Testes e Ajustes**:
   - Realizar testes de funcionalidade, jogabilidade e desempenho.
   - Ajustar a física, controles e balanceamento.

---

## Como Usar a Unity

A **Unity** é uma das ferramentas mais populares para o desenvolvimento de jogos. Para usar a Unity efetivamente, é necessário:

1. **Instalar o Unity Hub**: O Unity Hub é a central de gerenciamento das versões do Unity, projetos e serviços adicionais. Com ele, você pode instalar as versões mais recentes da Unity.

2. **Criar um Novo Projeto**:
   - Escolher o template de projeto (2D, 3D, VR, etc.).
   - Definir as configurações iniciais (plataforma de destino, resolução, etc.).

3. **Importação de Assets**:
   - Importar modelos 3D, animações, texturas e sons para o seu projeto.
   - Organizar esses assets em pastas dentro do projeto para facilitar o acesso.

4. **Programação e Interatividade**:
   - Utilizar scripts em **C#** para controlar a lógica do jogo, incluindo movimento, interações, física, etc.

5. **Build e Publicação**:
   - Configurar a plataforma de destino (PC, Web, Console, etc.).
   - Gerar o build final e realizar a publicação no formato desejado.

---

## Como Usar C# no Desenvolvimento de Jogos

O **C#** é a linguagem principal utilizada na **Unity** para a criação de scripts de jogos. Com ele, podemos controlar todos os aspectos do jogo, como movimentação de personagens, interações com objetos, física, e eventos.

1. **Scripts Básicos**:
   - Na Unity, os scripts são usados para controlar objetos dentro do jogo. Para criar um script, basta clicar com o botão direito na pasta de scripts e escolher **Create > C# Script**.

2. **Conceitos de Programação com C#**:
   - **Classe**: Cada script em C# é uma classe, e geralmente associamos uma classe a um objeto do jogo.
   - **Métodos**: Funções dentro de uma classe, como `Start()`, `Update()`, etc. O método `Start()` é executado quando o objeto é ativado, e o `Update()` é chamado a cada frame.

---

## Como Funciona o C#

**C#** é uma linguagem de programação orientada a objetos, o que significa que tudo em C# gira em torno de **objetos** e **classes**. A principal característica dessa abordagem é o encapsulamento, que organiza e estrutura o código de forma eficiente. Além disso, o C# possui **tipagem estática**, ou seja, os tipos das variáveis são definidos no momento da declaração.

### Principais Componentes do C#:

- **Classes e Objetos**: A base da programação orientada a objetos. Classes são moldes para objetos, e objetos são instâncias dessas classes.
- **Métodos e Propriedades**: Métodos são funções que realizam ações e propriedades representam atributos dos objetos.
- **Herança e Polimorfismo**: O C# permite que uma classe herde características de outra, o que ajuda a reutilizar código.

Exemplo básico de uma classe em C#:

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float moveHorizontal = Input.GetAxis("Horizontal");
        float moveVertical = Input.GetAxis("Vertical");

        Vector3 movement = new Vector3(moveHorizontal, 0, moveVertical);
        transform.Translate(movement * speed * Time.deltaTime);
    }
}
