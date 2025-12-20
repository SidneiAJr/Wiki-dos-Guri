## 🪟 **5️ Diferença entre JavaFX e Swing**

## 🎯 Objetivo
Entender as principais **diferenças entre JavaFX e Swing**, as duas principais bibliotecas gráficas do Java.

---

| 🧩 Recurso | 💻 Swing | 🎨 JavaFX |
|-------------|-----------|------------|
| **Ano de Lançamento** | 1998 | 2011 |
| **Abordagem** | Baseada em componentes (`JFrame`, `JButton`, etc.) | Baseada em cena (`Scene`, `Stage`, `FXML`) |
| **Interface Gráfica** | Simples e antiga | Moderna e com suporte a CSS |
| **Layout** | Feito no código (manual) | Feito via FXML (visual, com Scene Builder) |
| **Eventos** | `ActionListener`, `MouseListener`, etc. | Expressões lambda e `@FXML` methods |
| **Personalização** | Limitada (necessita LookAndFeel) | Altamente customizável com CSS |
| **Multimídia** | Suporte limitado | Suporte nativo a áudio, vídeo e gráficos 2D/3D |
| **Integração Web** | Difícil | Pode carregar HTML e JavaScript |
| **Recomendado para** | Aplicações simples ou legadas | Aplicações modernas e visuais |

---

## 💬 Exemplo Visual

**Swing:**
```java
JButton btn = new JButton("Clique");
frame.add(btn);
```
