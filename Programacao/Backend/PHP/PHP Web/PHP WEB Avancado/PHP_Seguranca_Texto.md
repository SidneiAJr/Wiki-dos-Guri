# 🔒 Segurança Avançada em PHP (Somente Texto)

Segurança é essencial em qualquer aplicação PHP.  
Aqui estão os tópicos avançados que garantem proteção profissional contra ataques comuns.

---

# ⭐ 1. SQL Injection
Evitar concatenar dados do usuário em queries.  
Sempre usar consultas preparadas e validar entradas.

---

# ⭐ 2. XSS (Cross-Site Scripting)
Ocorre quando dados não tratados são exibidos no navegador.  
A solução é sempre escapar a saída e validar inputs.

---

# ⭐ 3. CSRF (Cross-Site Request Forgery)
Ataque que força o usuário a executar ações sem autorização.  
Prevenção: tokens CSRF únicos por formulário.

---

# ⭐ 4. Session Hijacking
Roubo da sessão do usuário.  
Medidas de proteção:
- regenerar ID após login  
- usar cookies com bandeiras seguras  
- expirar sessões ociosas  

---

# ⭐ 5. Armazenamento Seguro de Senhas
Nunca armazenar senhas em texto puro.  
Usar algoritmos modernos e funções próprias do PHP.  
Evitar MD5, SHA1 ou métodos caseiros.

---

# ⭐ 6. Validação e Sanitização de Dados
Todo dado vindo do usuário é considerado não confiável.  
Processos essenciais:
- sanitizar entrada  
- validar tipo, formato e tamanho  
- rejeitar conteúdo inesperado  

---

# ⭐ 7. Segurança em Uploads
Arquivos enviados pelo usuário são perigosos.  
Boas práticas:
- verificar tipo real  
- definir tamanho máximo  
- impedir execução direta  
- armazenar fora do diretório público  

---

# ⭐ 8. Cookies Seguros
Sempre usar:
- httpOnly  
- secure (em HTTPS)  
- SameSite  
Evitar armazenar dados sensíveis neles.

---

# ⭐ 9. Rate Limiting
Impede ataques de força bruta.  
Limitar tentativas por IP ou por tempo.

---

# ⭐ 10. Criptografia
Chaves e dados sensíveis devem ser protegidos.  
Ideal usar bibliotecas modernas e algoritmos seguros.

---

# ⭐ 11. Arquivos Config sensíveis
Jamais deixar:
- senhas  
- tokens  
- chaves  
- credenciais  

expostos em arquivos públicos.  
Sempre usar variáveis de ambiente.

---

# ⭐ 12. Logs de Segurança
Registrar:
- falhas de login  
- erros de banco  
- operações críticas  
Nunca expor logs ao usuário final.

---

# ⭐ 13. Cabeçalhos de Segurança
Aplicações sérias utilizam:
- Content Security Policy  
- X-Frame-Options  
- X-Content-Type-Options  
- Strict-Transport-Security  

---

# ⭐ 14. Princípio do Menor Privilégio
Usuários, sistemas e conexões só devem ter acesso ao necessário.  
Nunca usar contas root para bancos de dados comuns.

---

# ⭐ 15. Segurança no Servidor
Configurações importantes:
- desabilitar exibição de erros  
- desativar funções perigosas  
- limitar permissões de arquivos  
- usar HTTPS obrigatoriamente
