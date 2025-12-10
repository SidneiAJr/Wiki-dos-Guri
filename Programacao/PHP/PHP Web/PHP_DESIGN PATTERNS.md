# 🎨 Design Patterns em PHP (Somente Texto)

Design Patterns são soluções reutilizáveis para problemas comuns na programação.  
Não são regras, mas modelos que ajudam a escrever código organizado, limpo e sustentável.

---

# ⭐ 1. Singleton
Garante que uma classe tenha apenas uma instância ao longo do sistema.  
Muito usado para gerenciar conexões ou configurações centrais.

---

# ⭐ 2. Factory Method
Cria objetos sem expor a lógica de criação diretamente.  
Ótimo para centralizar a forma como instâncias são criadas.

---

# ⭐ 3. Abstract Factory
Um nível acima da Factory.  
Cria “famílias” de objetos relacionados, mantendo a consistência entre eles.

---

# ⭐ 4. Strategy
Permite trocar comportamentos de forma dinâmica em tempo de execução.  
Ideal para sistemas que possuem várias “estratégias” possíveis para uma mesma tarefa.

---

# ⭐ 5. Observer
Um objeto "avisa" outros quando sofre alterações.  
Perfeito para notificações, eventos e sistemas que reagem a mudanças.

---

# ⭐ 6. Adapter
Conecta códigos incompatíveis permitindo que trabalhem juntos.  
Converte uma interface em outra esperada pelo sistema.

---

# ⭐ 7. Decorator
Adiciona funcionalidades extras a um objeto sem modificar sua estrutura original.  
Útil para extensões de comportamento.

---

# ⭐ 8. Repository
Cria uma camada entre o sistema e o banco de dados.  
Fornece métodos de acesso organizados e desacoplados.

---

# ⭐ 9. Dependency Injection
Inversão de controle: em vez de criar suas dependências, o objeto as recebe de fora.  
Melhora testabilidade e organização.

---

# ⭐ 10. MVC (Model–View–Controller)
Divide o sistema em:
- Model (dados e regras de negócio)  
- View (interface)  
- Controller (fluxo e lógica de requisição)

Ajuda a manter o código modular e limpo.

---

# ⭐ 11. Facade
Cria uma interface simples para sistemas complexos.  
Facilita acesso a subsistemas agrupados.

---

# ⭐ 12. Builder
Constrói objetos complexos passo a passo, controlando cada parte do processo.

---

# ⭐ 13. Command
Empacota uma ação em um objeto independente.  
Bom para filas, histórico de ações ou desfazer operações.

---

# ⭐ 14. Iterator
Permite percorrer coleções de forma uniforme, sem expor sua estrutura interna.

---

# ⭐ 15. Template Method
Define o esqueleto de um algoritmo e permite que subclasses personalizem partes específicas.

---

# ⭐ Conclusão
Design Patterns ajudam a construir sistemas mais escaláveis, fáceis de testar e manter, além de evitar reinvenção da roda.
