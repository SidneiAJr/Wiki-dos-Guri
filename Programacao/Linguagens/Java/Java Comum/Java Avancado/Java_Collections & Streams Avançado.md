# Collections & Streams Avançado

## 📌 Introdução
Collections e Streams são pilares do Java moderno.  
Nível avançado envolve entender **estrutura**, **complexidade**, **imutabilidade**, **performance** e **uso correto em sistemas grandes**.

---

## 🧰 Coleções e Estruturas Internas

### List — listas
- **ArrayList**: rápido pra leitura, lento pra remoção no meio
- **LinkedList**: bom para inserções/remoções frequentes, leitura mais lenta

### Set — elementos únicos
- **HashSet**: mais rápido (usa hashing)
- **LinkedHashSet**: mantém a ordem de inserção
- **TreeSet**: ordenado, porém mais lento (árvore)

### Map — chave/valor
- **HashMap**: padrão para performance
- **LinkedHashMap**: mantém ordem de inserção
- **TreeMap**: ordenado por chave
- **ConcurrentHashMap**: seguro para concorrência de alta performance

---

## ⚙️ Conceitos Importantes

- **Hashing** — define onde os dados são guardados
- **Load factor** — controla realocação e performance
- **Collisions** — vários valores no mesmo hash bucket
- **Imutabilidade** — reduz bugs e ajuda em concorrência
- **Fail-Fast Iterator** — detecta modificações concorrentes

---

## 🚀 Streams Avançado

### Características
- Não armazenam dados
- Imutáveis
- Lazy (executam apenas quando necessário)
- Podem ser paralelos
- Excelente para processamento de dados

### Operações importantes
- `map`, `filter`, `reduce`, `sorted`
- `collect`, `groupingBy`, `partitioningBy`
- `flatMap` (quando temos listas dentro de listas)

### Avoid
- Streams paralelos em coleções pequenas
- Streams para lógica com efeitos colaterais
- Usar streams onde um `for` é mais claro

---

## 🎯 Práticas Avançadas
- Preferir **coleções imutáveis**
- Usar streams para **processamento declarativo**
- Combinar `Collectors` para agregações complexas
- Entender custo de paralelismo

> Domínio avançado de Collections & Streams é um passo de maturidade no Java.
