# Exemplo de Aplicação Web em C# com ASP.NET Core

Este é um exemplo simples de uma aplicação ASP.NET Core que cria uma API para gerenciar usuários.

## 1. Criação do Projeto

Abra o terminal e crie um novo projeto ASP.NET Core usando o comando:

```bash
dotnet new webapi -n MeuProjetoApi
cd MeuProjetoApi
````


### `User.cs`

```c#
public class User
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Email { get; set; }
}
```

### `UsersController.cs`

```c#
using Microsoft.AspNetCore.Mvc;
using System.Collections.Generic;

namespace MeuProjetoApi.Controllers
{
    [Route("api/[controller]")]
    [ApiController]
    public class UsersController : ControllerBase
    {
        // Lista de usuários (em um cenário real, isso viria de um banco de dados)
        private static List<User> users = new List<User>
        {
            new User { Id = 1, Name = "João", Email = "joao@email.com" },
            new User { Id = 2, Name = "Maria", Email = "maria@email.com" }
        };

        // GET: api/users
        [HttpGet]
        public IActionResult Get()
        {
            return Ok(users);
        }

        // GET: api/users/{id}
        [HttpGet("{id}")]
        public IActionResult Get(int id)
        {
            var user = users.Find(u => u.Id == id);
            if (user == null)
            {
                return NotFound();
            }
            return Ok(user);
        }

        // POST: api/users
        [HttpPost]
        public IActionResult Post([FromBody] User newUser)
        {
            users.Add(newUser);
            return CreatedAtAction(nameof(Get), new { id = newUser.Id }, newUser);
        }

        // PUT: api/users/{id}
        [HttpPut("{id}")]
        public IActionResult Put(int id, [FromBody] User updatedUser)
        {
            var user = users.Find(u => u.Id == id);
            if (user == null)
            {
                return NotFound();
            }

            user.Name = updatedUser.Name;
            user.Email = updatedUser.Email;

            return NoContent();
        }

        // DELETE: api/users/{id}
        [HttpDelete("{id}")]
        public IActionResult Delete(int id)
        {
            var user = users.Find(u => u.Id == id);
            if (user == null)
            {
                return NotFound();
            }

            users.Remove(user);
            return NoContent();
        }
    }
}
```

### `Startup.cs`

```C#
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddControllers();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.UseRouting();
        
        app.UseEndpoints(endpoints =>
        {
            endpoints.MapControllers();
        });
    }
}
````


