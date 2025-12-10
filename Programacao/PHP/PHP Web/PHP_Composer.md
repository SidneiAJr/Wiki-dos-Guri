# Composer (Gerenciador de Dependências do PHP)

## 1. O que é o Composer?
O Composer é um gerenciador de dependências para PHP.  
Ele permite instalar bibliotecas externas (pacotes) e gerenciar versões de forma automática.

Sem o Composer, seria necessário baixar bibliotecas manualmente e atualizar na mão.

---

## 2. Para que serve?
- Instalar bibliotecas e frameworks (ex: Laravel, Monolog, PHPMailer)
- Atualizar dependências automaticamente
- Controlar versões (compatibilidade)
- Padronizar projetos PHP modernos
- Facilitar organização do código

---

## 3. Como funciona?
O Composer usa dois arquivos principais:

| Arquivo | Função |
|--------|--------|
| `composer.json` | Declara as dependências do projeto |
| `composer.lock` | Registra a versão exata instalada |

As bibliotecas instaladas ficam guardadas na pasta **`/vendor`**.

---

## 4. Tipos de dependências
| Tipo | Instalação | Uso |
|------|------------|-----|
| Dependência normal | `composer require pacote` | Usada em produção |
| Dependência de desenvolvimento | `composer require --dev pacote` | Usada só no desenvolvimento |

---

## 5. Versionamento
O Composer usa **versionamento semântico**:
- `^1.4` → aceita atualização de correção e melhorias
- `~1.4` → aceita apenas pequenas mudanças
- `1.4.*` → correções dentro da mesma versão

---

## 6. Benefícios
- Agilidade
- Segurança (pacotes com manutenção)
- Organização
- Compatibilidade
- Atualizações controladas

---

## 7. Exemplos de uso comuns
| Pacote | Uso |
|--------|-----|
| PHPMailer | Envio de e-mails |
| Guzzle | Requisições HTTP |
| Carbon | Manipulação de datas |
| Dotenv | Gerenciar variáveis de ambiente |
| PHPUnit | Testes automatizados |

---

## 8. Conclusão
Qualquer projeto PHP moderno utiliza Composer.  
Ele é o padrão do mercado e é obrigatório para frameworks modernos como **Laravel, Symfony e Slim**.

Sem o Composer, o PHP fica “limitado” ao básico.  
Com ele, é possível escalar e organizar um projeto corretamente.

# Namespaces e Autoload (PHP Moderno)

## 1. O que é um Namespace?

Namespace é uma forma de **organizar o código** em "pacotes" ou "espaços de nome".
Ele evita conflitos de nomes entre classes e deixa o código mais estruturado.

Sem namespaces, duas classes com o mesmo nome causariam erro.
Com namespace, o PHP sabe "de onde" a classe veio.

---

## 2. Exemplo simples de namespace

```php
<?php
namespace App\Models;

class Usuario {
    public function ola() {
        return "Olá!";
    }
}
```

# MVC em PHP (Conceito Simples e Direto)

## 1. O que é MVC?

MVC significa **Model - View - Controller**.
É um padrão de arquitetura para separar responsabilidades no código.

| Parte | Função |
|------|--------|
| Model | Regras de negócio e dados |
| View | Interface (HTML / o que o usuário vê) |
| Controller | Intermediário: recebe a requisição e escolhe o que fazer |

---

## 2. Por que usar MVC?

- Organiza melhor o código
- Facilita manutenção
- Separa "lógica" de "visual"
- Usado em frameworks (Laravel, Symfony, CodeIgniter)

---

## 3. Como funciona (fluxo simples)

1. O usuário acessa uma rota (ex: `/usuarios`)
2. O **Controller** recebe a requisição
3. O Controller chama o **Model** para buscar dados
4. O Controller envia os dados para a **View**
5. A View exibe o resultado (HTML)

---

## 4. Exemplo simples

**Model:**
```php
class UsuarioModel {
    public function listar() {
        return ["João", "Maria", "Carlos"];
    }
}
```


---

Se quiser, posso continuar com mais conteúdos avançados de PHP como:

| Próximos tópicos possíveis | Avançado? |
|---------------------------|-----------|
| Roteamento (Router) | ✅ |
| Middlewares | ✅ |
| Injeção de Dependência | ✅ |
| PDO + Query Builder | ✅ |
| ORM (Eloquent) | ✅ |
| SOLID aplicado no PHP | ✅ |
| PSR (normas oficiais) | ✅ |
| Tratamento de erros e Exceptions | ✅ |
| Sessions e Cookies avançado | ✅ |
| Serviços e camadas (Service Layer) | ✅ |

Se quiser que eu continue, diga **"continuar PHP avançado"** ou apenas **"next"** 👍


# Roteamento (Router) no PHP - Conceito Simples

## 1. O que é um Router?

Router (roteador de rotas) é o componente que **decide qual Controller e método** devem ser executados quando o usuário acessa uma URL.

Exemplo:
- `/usuarios` → chama `UsuarioController@index`
- `/produtos` → chama `ProdutoController@index`

Sem router: você cria vários arquivos .php soltos
Com router: você organiza por rotas e controllers

---

## 2. Como funciona (ideia simples)

1. O usuário acessa uma URL
2. O Router lê a URL
3. Ele identifica a rota
4. Chama o Controller correto
5. Controller chama o Model e retorna View

---

## 3. Exemplo simples de Router manual

```php
$rota = $_GET['url'] ?? '/';

if ($rota === '/usuarios') {
    $controller = new UsuarioController();
    $controller->index();
} elseif ($rota === '/produtos') {
    $controller = new ProdutoController();
    $controller->index();
}
```


# Middlewares no PHP (Explicação Simples)

## 1. O que é um Middleware?

Middleware é um **"filtro"** que roda **antes ou depois** do Controller.
Ele intercepta a requisição e verifica se algo precisa ser validado ou tratado.

---

## 2. Para que serve?

| Função | Exemplo |
|--------|----------|
| Segurança | Verificar login/autenticação |
| Permissões | Conferir se o usuário tem autorização |
| Logs | Registrar acessos do usuário |
| Performance | Cache de respostas |
| Sanitização | Limpar/validar entrada de dados |

---

## 3. Analogia simples

> Antes de entrar em uma sala, você passa por um **porteiro** (middleware).
> Ele verifica se você pode passar.
> Se você não tiver permissão → barrado.
> Se estiver tudo certo → entra (controller executa).

---

## 4. Exemplo simples (pseudo PHP)

```php
function authMiddleware() {
    if (!isset($_SESSION['usuario_logado'])) {
        header('Location: /login');
        exit;
    }
}
```
