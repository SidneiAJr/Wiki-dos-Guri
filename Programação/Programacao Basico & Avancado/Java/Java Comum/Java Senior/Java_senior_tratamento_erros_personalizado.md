# Java | Exceções Personalizadas

## O que são Exceções em Java?

Em Java, **exceções** representam situações inesperadas ou erros que ocorrem durante a execução do programa.

Elas servem para:

* Interromper o fluxo normal
* Informar que algo deu errado
* Permitir tratamento adequado do erro

---

## Checked vs Unchecked Exceptions

### Checked Exceptions

São exceções **verificadas em tempo de compilação**.
O compilador obriga o tratamento com `try/catch` ou `throws`.

Exemplo:

```java
IOException
SQLException
```

---

### Unchecked Exceptions

São exceções que **ocorrem em tempo de execução**.
Herda de `RuntimeException`.

Exemplo:

```java
NullPointerException
IllegalArgumentException
```

---

## Por que criar Exceções Personalizadas?

Criar exceções próprias permite:

* Mensagens de erro mais claras
* Melhor organização do código
* Separação de regras de negócio
* Padronização de erros no sistema

👉 Muito usado em **backend profissional**.

---

## Criando uma Exceção Personalizada

### Exceção Checked

```java
public class UsuarioNaoEncontradoException extends Exception {
    public UsuarioNaoEncontradoException(String mensagem) {
        super(mensagem);
    }
}
```

Uso:

```java
if (usuario == null) {
    throw new UsuarioNaoEncontradoException("Usuário não encontrado");
}
```

---

### Exceção Unchecked (mais comum no backend)

```java
public class NegocioException extends RuntimeException {
    public NegocioException(String mensagem) {
        super(mensagem);
    }
}
```

Uso:

```java
if (saldo < valor) {
    throw new NegocioException("Saldo insuficiente");
}
```

---

## Onde lançar Exceções Personalizadas?

📌 **Service Layer**

Nunca na camada de controller diretamente.

```java
public class UsuarioService {

    public Usuario buscarPorId(Long id) {
        Usuario usuario = repository.buscar(id);

        if (usuario == null) {
            throw new UsuarioNaoEncontradoException("Usuário não encontrado");
        }

        return usuario;
    }
}
```

---

## Tratando Exceções

### try / catch

```java
try {
    service.buscarPorId(10L);
} catch (UsuarioNaoEncontradoException e) {
    System.out.println(e.getMessage());
}
```

---

### Propagando exceções

```java
public void executar() throws UsuarioNaoEncontradoException {
    service.buscarPorId(10L);
}
```

---

## Boas práticas

✅ Use exceções personalizadas para regras de negócio
✅ Prefira `RuntimeException` no backend
✅ Mensagens claras e objetivas
❌ Não use exceções para fluxo normal

---

## Resumo rápido

* Exceções representam erros
* Checked → obrigam tratamento
* Unchecked → mais usadas no backend
* Exceções personalizadas deixam o código profissional
