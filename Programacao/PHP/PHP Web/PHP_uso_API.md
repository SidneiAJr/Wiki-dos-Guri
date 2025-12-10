# Criando uma API REST simples — Comparativo PHP | Java | C#

## 1. PHP (usando PHP puro + header JSON)
```php
<?php
// api.php

// Simula um usuário (normalmente viria do banco)
$usuario = [
    "id" => 1,
    "nome" => "Maria",
    "email" => "maria@example.com"
];

// Define que a saída será JSON
header('Content-Type: application/json');

// Retorna os dados do usuário como JSON
echo json_encode($usuario);
?>
```

## 2. Java (usando Spring Boot)
```JAVA
@RestController
@RequestMapping("/api")
public class UsuarioController {

    @GetMapping("/usuario")
    public ResponseEntity<Map<String, Object>> getUsuario() {
        Map<String, Object> usuario = new HashMap<>();
        usuario.put("id", 1);
        usuario.put("nome", "Maria");
        usuario.put("email", "maria@example.com");

        return ResponseEntity.ok(usuario);
    }
}
```
## 3. C# (usando ASP.NET Core Web API)
```c#
[ApiController]
[Route("api/[controller]")]
public class UsuarioController : ControllerBase
{
    [HttpGet]
    public IActionResult GetUsuario()
    {
        var usuario = new {
            id = 1,
            nome = "Maria",
            email = "maria@example.com"
        };

        return Ok(usuario);
    }
}
```
