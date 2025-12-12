# Spring Security & JWT — Conceitos Fundamentais

## 📌 Introdução

Spring Security é o framework padrão do ecossistema Spring para autenticação, autorização e proteção de aplicações.

Ele fornece:

- Controle de acesso
- Autenticação (identidade)
- Autorização (permissões)
- Filtros de segurança
- Prevenção contra ataques comuns
- Integração com tokens, OAuth2, JWT, SSO e mais

JWT (JSON Web Token) é o formato moderno para autenticação **stateless**, usado amplamente em APIs.

---

## 🛡️ Por que Spring Security?

- Controle centralizado de segurança
- Altamente configurável
- Integra com banco, LDAP, OAuth2, Keycloak
- Compatível com microservices
- Suporte nativo a autenticação stateless com JWT
- Usa filtros e chain para interceptar requisições

---

## 🧠 Conceitos Centrais

### Autenticação
Processo de verificar *quem é o usuário*.

### Autorização
Processo de verificar *o que o usuário pode fazer*.

### Contexto de Segurança
Armazena informações do usuário autenticado durante a requisição.

### Security Filter Chain
Sequência de filtros que Spring executa antes de chegar no controlador.

### Stateless vs Stateful
| Tipo | Armazena sessão? | Onde fica o estado |
|------|------------------|------------------|
Stateful | Sim | Servidor |
Stateless | Não | Token no cliente (JWT) |

---

## 🔐 JWT — Conceitos

JWT é um token assinado que identifica o usuário.

### Estrutura
Composto por três partes:

1. Header — tipo e algoritmo
2. Payload — dados (claims)
3. Signature — assinatura para validar

### Características
- Portável
- Autocontido
- Não depende de sessão
- Usado em APIs REST e microservices

### Quando usar JWT
- APIs REST
- Microservices
- Mobile / SPA (Angular, React, Vue)
- Sistemas que precisam escalar

---

## 🚫 Quando **não** usar JWT

- Aplicações simples com sessão
- Sistemas que exigem logout instantâneo universal
- Ambiente onde tokens podem vazar facilmente

Nesses casos, session + cookies pode ser melhor.

---

## 🧳 Claims Importantes

- `sub` — identificação do usuário
- `exp` — expiração
- `role` / `authorities` — permissões
- `iat` — data criação
- `iss` — emissor

---

## 🛂 Roles & Authorities

- **Role** — perfil do usuário (ADMIN, USER)
- **Authority** — permissão (CAN_DELETE, CAN_UPDATE)

Roles são grupos de authorities.

---

## 🔒 Cadeia de segurança (simplificada)

1. Requisição chega
2. Filtro verifica JWT
3. Valida token e extrai usuário
4. Injeta no contexto de segurança
5. Controller executa se autorizado

---

## ⚠️ Boas Práticas com JWT

- Tokens devem ter expiração curta
- Usar refresh tokens
- Assinar com chave forte
- Nunca guardar JWT em localStorage sem cuidado
- Preferir **HttpOnly Cookies** em apps web
- Proteger endpoints sensíveis

---

## 🧰 Boas práticas com Spring Security

- Desabilitar Session em APIs (stateless)
- Configurar rotas públicas e privadas
- Aplicar `.permitAll()`, `.authenticated()`, `.hasRole()` corretamente
- Centralizar configuração de segurança
- Logging de falhas e bloqueios
- Auditar ações de usuários críticos

---

## 🛡️ Segurança complementar

Spring Security não substitui:

- Sanitização de entrada
- Criptografia sensível
- Rate limiting
- Logs e auditoria
- Segurança de banco de dados

---

## 📑 Termos importantes

| Termo | Significado |
|------|-------------|
Authentication | Identificar usuário |
Authorization | Garantir acesso permitido |
Token | Comprovação de identidade |
Stateless | Sem sessão |
Filter Chain | Pipeline de segurança |
Claims | Informações dentro do token |

---

## 🧾 Conclusão

Spring Security + JWT é a combinação padrão para APIs modernas em Java.  
Ele garante autenticação segura, escalabilidade e flexibilidade, essencial em arquiteturas distribuídas e microservices.

> Entender segurança é indispensável para o desenvolvedor Java moderno.

