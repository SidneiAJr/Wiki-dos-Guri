# 📌 HTML - `div` e Tags Semânticas

O HTML oferece elementos para estruturar o conteúdo da página.  
Entender a diferença entre `div` e as **tags semânticas** é essencial para criar páginas organizadas, acessíveis e entendidas pelos navegadores.

---

## **1) `div` — Elemento Genérico de Bloco**

A tag `div` representa um **container genérico** sem significado próprio.  
Ela serve como **agrupamento** para outros elementos.

Usos comuns:
- Organização de layout
- Agrupamento de seções
- Estruturação de blocos para estilização

A `div` **não descreve o conteúdo**, apenas o **agrupa**.

---

## **2) Por Que Usar Tags Semânticas**

Tags semânticas **descrevem o propósito** do conteúdo.

Benefícios:
- Facilita leitura e manutenção do código
- Ajuda mecanismos de busca (SEO)
- Melhora acessibilidade para leitores de tela
- Ajuda navegadores a interpretarem a estrutura

---

## **3) Principais Tags Semânticas**

| Tag | Significado | Uso Recomendado |
|-----|------------|----------------|
| `header` | Cabeçalho da página ou seção | Logo, título, menu principal |
| `nav` | Área de navegação | Menus e links principais |
| `main` | Conteúdo principal da página | Conteúdo central e relevante |
| `section` | Sessão temática | Blocos que agrupam conteúdos relacionados |
| `article` | Conteúdo independente | Notícias, posts, comentários, textos completos |
| `aside` | Conteúdo complementar | Barras laterais, notas, sugestões |
| `footer` | Rodapé | Créditos, contatos, links finais |

---

## **4) Quando Usar `div` e Quando Usar Tags Semânticas**

| Situação | Melhor Escolha | Motivo |
|---------|----------------|--------|
| Sem significado específico, apenas organização visual | `div` | Não altera o sentido do conteúdo |
| Conteúdo com função clara na página | Tags semânticas | Melhora entendimento da estrutura |
| Construindo layout com CSS Grid/Flex | `div` | Estrutura neutra |
| Criando menus, seções ou artigos | Tags semânticas | Indica propósito real |

---

## 🏁 Resumo Final

- **`div`** = apenas organiza.
- **Tags semânticas** = organizam **e** explicam a função do conteúdo.
- Usar semântica melhora:
  - Acessibilidade
  - SEO
  - Clareza do código

