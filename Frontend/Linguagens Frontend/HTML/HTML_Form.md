# 📌 Documentação: Formulário HTML e Métodos GET e POST

O elemento **`form`** no HTML é utilizado para **enviar dados** inseridos pelo usuário para algum destino, geralmente um servidor ou uma aplicação.  
O envio é realizado através do atributo **`method`**, que define **como** os dados serão transmitidos.

Existem dois métodos principais:

---

## **1) Método GET**

- Envia os dados **pela URL**.
- Os valores preenchidos no formulário são anexados ao endereço depois de um ponto de interrogação.
- Os dados **ficam visíveis** na barra de endereços.
- É ideal para **pesquisas, filtros, navegação** ou qualquer ação que **não seja confidencial**.
- É mais rápido, porque não envolve encapsulamento de dados.
- **Não é indicado** para envio de informações sensíveis (ex.: senhas).

**Uso recomendado:**  
Quando você quer **buscar ou consultar** informações sem alterar dados no servidor.

---

## **2) Método POST**

- Envia os dados **internamente**, no corpo da requisição.
- Os dados **não aparecem na URL**.
- É indicado para **informações sensíveis**, como logins ou cadastros.
- Suporta envio de **arquivos e grandes volumes de dados**.
- É utilizado principalmente quando existirá alguma **modificação**, como criar, salvar ou atualizar informações.

**Uso recomendado:**  
Quando você deseja **registrar, armazenar ou alterar** dados no servidor com segurança.

---

## 🧭 Resumo Comparativo

| Característica | GET | POST |
|----------------|-----|------|
| Local onde os dados são enviados | URL | Corpo da requisição |
| Visibilidade dos dados | Visíveis | Ocultos |
| Segurança | Baixa | Alta (relativa) |
| Tamanho máximo dos dados | Limitado | Pode ser maior |
| Uso comum | pesquisa, navegação | cadastro, login, upload, alterações |
| Afeta estado do sistema | Não | Sim (geralmente) |

---

## ✅ Regra geral para lembrar

> **Use GET para buscar.**  
> **Use POST para enviar, salvar ou alterar.**

---

