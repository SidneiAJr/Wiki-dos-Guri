# 🌱 Introdução ao Spring Boot em Java

O Spring Boot é um framework Java que facilita muito o desenvolvimento de aplicações modernas — especialmente APIs, sistemas web e microserviços.
Ele faz parte do ecossistema Spring, que é uma das plataformas mais usadas no mundo para aplicações empresariais em Java.

# 🚀 O que é o Spring Boot?

Tradicionalmente, desenvolver em Java exigia muita configuração manual (XML, servidores de aplicação, dependências, etc.).
O Spring Boot surgiu para simplificar isso, permitindo que o desenvolvedor:

Crie e execute aplicações Java com pouquíssima configuração;

Evite o uso de servidores externos (como Tomcat manualmente, pois ele já vem embutido);

Tenha controle total sobre dependências e ambiente de execução via o arquivo pom.xml (Maven) ou build.gradle (Gradle).

Em resumo:
👉 Spring Boot é uma maneira rápida, prática e moderna de criar aplicações Java completas, com poucos arquivos e muita automação.

# ⚙️ Principais Recursos do Spring Boot

AutoConfiguração:
O Spring Boot detecta automaticamente dependências e configurações necessárias, sem necessidade de XML.

Servidor Embutido:
O projeto já vem com o Tomcat, Jetty ou Undertow, então basta rodar mvn spring-boot:run ou java -jar.

REST APIs Simplificadas:
Criar uma API REST é tão simples quanto usar:

```Java
@RestController
@RequestMapping("/api")
public class MeuController {
    @GetMapping("/hello")
    public String hello() {
        return "Olá, mundo!";
    }
}
```

Integração com Banco de Dados (Spring Data JPA):
Você pode criar repositórios com poucos comandos:

public interface UsuarioRepository extends JpaRepository<Usuario, Long> { }


Segurança embutida (Spring Security):
Permite autenticação e controle de acesso sem precisar programar tudo do zero.

# 🔍 Como criar um projeto rapidamente

- Acesse: 👉 https://start.spring.io

- Escolha:

- Project: Maven Project

- Language: Java

- Spring Boot: última versão estável

- Adicione dependências como:

- Spring Web

- Spring Data JPA

- MySQL Driver

- Clique em "Generate", baixe o .zip, extraia e abra no VS Code ou IntelliJ IDEA.
