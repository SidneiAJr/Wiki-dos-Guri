# 🪟 Métodos de Janela no NetBeans (Java Swing)

Ao trabalhar com interfaces gráficas no **NetBeans** (usando **Swing**), é comum termos várias janelas (`JFrame`) e precisarmos **abrir uma nova** ou **fechar a atual**.  
Abaixo estão os principais métodos e exemplos usados para controlar essas janelas.

---

## 🔹 Exemplo básico

```java
Shimatsu per2 = new Shimatsu();  // Cria uma nova janela (objeto da classe Shimatsu)
this.dispose();                  // Fecha a janela atual
per2.setVisible(true);           // Exibe a nova janela
```

| Método                          | Descrição                                                                         |
| ------------------------------- | --------------------------------------------------------------------------------- |
| `setVisible(true/false)`        | Exibe ou oculta a janela.                                                         |
| `dispose()`                     | Fecha a janela e libera recursos (não encerra o programa todo).                   |
| `setDefaultCloseOperation(int)` | Define o que acontece quando o usuário clica no "X".                              |
| `setLocationRelativeTo(null)`   | Centraliza a janela na tela.                                                      |
| `setResizable(true/false)`      | Permite ou impede o redimensionamento da janela.                                  |
| `setTitle("Título")`            | Define o título da janela.                                                        |
| `pack()`                        | Ajusta automaticamente o tamanho da janela de acordo com os componentes internos. |
| `setSize(largura, altura)`      | Define manualmente o tamanho da janela.                                           |

| Ação                      | Método                                         |
| ------------------------- | ---------------------------------------------- |
| Mostrar janela            | `setVisible(true)`                             |
| Esconder janela           | `setVisible(false)`                            |
| Fechar janela atual       | `dispose()`                                    |
| Fechar tudo (sair do app) | `System.exit(0)`                               |
| Abrir nova e fechar atual | `this.dispose(); novaJanela.setVisible(true);` |
