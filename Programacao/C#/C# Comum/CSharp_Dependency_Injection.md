# Dependency Injection no C# / .NET

## 📌 O que é DI?

Dependency Injection (DI) é um padrão que remove dependências diretas entre classes, tornando o código:

- Mais modular
- Mais testável
- Mais fácil de manter
- Seguindo princípios SOLID (principalmente DIP)

---

## 🧠 Conceitos

### **Inversão de Controle (IoC)**
O código não cria dependências — elas são fornecidas externamente.

### **Container de Injeção**
Gerencia ciclo de vida e resolução de objetos.

Usado no ASP.NET Core por padrão.

---

## 🏗️ Ciclos de Vida

| Lifetime | Descrição |
|---------|-----------|
Transient | Nova instância a cada requisição |
Scoped | Uma instância por requisição HTTP |
Singleton | Uma instância por aplicação |

---

## 🎯 Benefícios

- Reduz acoplamento
- Facilita testes com mocks
- Organização mais clara
- Substituição fácil de implementações

---

## ⚠️ Cuidados

- Não transformar tudo em serviço
- Cuidado com singletons usando dados mutáveis
- Evitar dependências circulares

---

## ✅ Quando usar DI

- Arquitetura corporativa
- Web APIs
- Microservices
- Aplicações testáveis

---

## 🧭 Conclusão

Dependency Injection é padrão obrigatório no .NET moderno, permitindo arquitetura limpa, modular e extensível.
