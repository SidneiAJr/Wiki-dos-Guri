# 🪞 Java Reflection — Guia Completo

Reflection é um recurso avançado do Java que permite **inspecionar e manipular classes, métodos, atributos e construtores em tempo de execução**, mesmo sem conhecer a classe antecipadamente.

É muito utilizado em:
- Frameworks (Spring, Hibernate, Quarkus)
- Injeção de dependências
- Serialização e desserialização
- Processamento de anotações
- Ferramentas de teste
- Depuração e análise dinâmica

---

## 📌 1. O que é Reflection?

Reflection possibilita:
- Obter informações de classes em tempo de execução
- Criar objetos dinamicamente
- Invocar métodos dinamicamente
- Acessar e modificar atributos (mesmo privados)
- Ler e manipular anotações

⚠️ **Cuidados**:
- Pode diminuir performance
- Pode quebrar encapsulamento
- Pode gerar problemas de segurança

---

## 📌 2. Obtendo o Objeto `Class<?>`

```java
Class<?> c1 = MinhaClasse.class;
Class<?> c2 = objeto.getClass();
Class<?> c3 = Class.forName("com.exemplo.MinhaClasse");
```

```java
Constructor<?>[] constructors = c1.getDeclaredConstructors();
```

## 📌 10. Quando Evitar Reflection?

Evite quando:

Performance é crítica

Há alternativa simples sem reflection

Precisa manter forte encapsulamento

Quer segurança rígida

## 📌 11. Vantagens e Desvantagens
✔️ Vantagens

Extremamente flexível

Permite frameworks complexos

Habilita automação

Permite código genérico

❌ Desvantagens

Mais lento que chamadas diretas

Pode quebrar encapsulamento

Pode causar erros difíceis de rastrear
