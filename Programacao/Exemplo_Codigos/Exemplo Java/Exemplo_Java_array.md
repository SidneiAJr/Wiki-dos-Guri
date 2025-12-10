# Exemplo de Arrays(Arraylist, Hashmap, Set)

## `Aqui contem exemplos de Array`

### `Array | Comum`:

```java
package aula1;
import java.util.Scanner;


public class Aula1 {

    public static void main(String[] args) {
       
         Scanner entrada = new Scanner(System.in);

        double array[]= new double[6];

        for(int i=0; i<array.length; i++ ){
            System.out.println("Insira Um valor: "+i);
            array[i]=entrada.nextDouble();
        }

        System.out.println("Informações do Array \n: ");
        for(int i = 0; i < array.length; i++){
            System.out.println("Posição " + i + ": " + array[i]);
        }
           entrada.close();
    }
    
}
````

### `Array | Lista(Lista Array)`:

````java
package aula1;

// Importa as classes necessárias para entrada de dados (Scanner) e listas (ArrayList e List)
import java.util.Scanner;
import java.util.ArrayList;
import java.util.List;

public class Aula1 {
    public static void main(String[] args) {
       
       // Cria uma lista de Strings chamada "lista"
       List<String> lista = new ArrayList<>();
       
       // Adiciona elementos (nomes) na lista
       lista.add("Arthur"); // posição 0
       lista.add("Jian");   // posição 1
       lista.add("Super Kalleo"); // posição 2
       lista.add("Joao da massa"); // posição 3
       lista.add("Luskao"); // posição 4
       
       // Remove o elemento "Joao da massa" da lista
       lista.remove("Joao da massa"); // agora a lista tem 4 elementos
       
       // Acessa elementos individuais usando o índice
       String p1 = lista.get(0); // pega o primeiro elemento ("Arthur")
       String p2 = lista.get(1); // pega o segundo elemento ("Jian")
       String p3 = lista.get(2); // pega o terceiro elemento ("Super Kalleo")
       
       // Substitui o elemento na posição 2 por um novo valor
       lista.set(2,"Lukao o brabo"); // "Super Kalleo" é substituído por "Lukao o brabo"
       
       // Armazena o tamanho atual da lista em uma variável
       int tamanhoLista = lista.size(); // 4 elementos atualmente
       
       // Exibe o tamanho da lista
       System.out.println("Tamanho da Lista: "+ tamanhoLista);
       
       // Exibe todos os elementos da lista
       System.out.println(lista); // imprime: [Arthur, Jian, Lukao o brabo, Luskao]
       
       // lista.remove(lista); 
       // Isso vai causar um erro de compilação ou de tempo de execução
       // Se quiser remover todos os elementos, use lista.clear();
       // lista.clear(); // limpa a lista completamente
       
       // Exibe os valores individuais armazenados antes da alteração
       System.out.println("Posiçao 1: "+p1); // "Arthur"
       System.out.println("Posiçao 2: "+p2); // "Jian"
       System.out.println("Posiçao 3: "+p3); // "Super Kalleo"
       
       // IMPORTANTE: p3 ainda vai mostrar "Super Kalleo" mesmo depois do set,
       // porque p3 foi atribuído antes da alteração com set()
              
    }
}
````

### `Array Set |List`

````java
package aula0212;
import java.util.Set;
import java.util.HashSet;


public class Aula0212 {

    public static void main(String[] args) {
        Set<String> tecnologia = new HashSet<>();
        
        tecnologia.add("Java");
        tecnologia.add("Assembly");
        tecnologia.add("Cobol");
        tecnologia.add("Java");
        tecnologia.add("C#");
        tecnologia.add("Python");
        
        int tamanho = tecnologia.size();
        
        System.out.println("Tamanho : "+tamanho);
        
        for(String tech: tecnologia){
            System.out.println("Tecnologias Disponiveis: "+tech);
        }
    }
}
````


## Array | MAP

```java
package aula0212;

import java.util.HashMap;
import java.util.Map;

public class Aula0212 {

    public static void main(String[] args) {

        // Mapa de magos e seus poderes
        Map<String, Double> poderes = new HashMap<>();

        poderes.put("Eldrin", 750.0);
        poderes.put("Mira", 920.0);
        poderes.put("Thalos", 860.3);

        // Atualizando o poder de Eldrin e guardando o valor antigo
        double poderAntigoEldrin = poderes.put("Eldrin", 800.0);

        // Recuperando valores
        double poderMira = poderes.get("Mira");

        // Exibindo todos os registros
        System.out.println("Lista de Magos e seus Poderes:");
        for (Map.Entry<String, Double> entry : poderes.entrySet()) {
            System.out.println("Mago: " + entry.getKey() + " | Poder: " + entry.getValue());
        }

        // Exibições individuais
        System.out.println("\nPoder de Mira: " + poderMira);
        System.out.println("Poder antigo de Eldrin: " + poderAntigoEldrin);
        System.out.println("Poder atual de Eldrin: " + poderes.get("Eldrin"));

        // Tamanho total
        int totalMagos = poderes.size();
        System.out.println("Quantidade Total de Magos: " + totalMagos);
    }
}
````
## Quadro Comparativo – Array vs Set vs Map

| Estrutura | Como funciona                                                | Aceita valores repetidos?    | Mantém ordem?                    | Acesso por índice? | Acesso por chave?        | Usos típicos                                         |
| --------- | ------------------------------------------------------------ | ---------------------------- | -------------------------------- | ------------------ | ------------------------ | ---------------------------------------------------- |
| **Array** | Lista fixa de elementos, sempre com tamanho definido.        | ✔ Sim                        | ✔ Sim (ordem de inserção)        | ✔ Sim              | ✖ Não                    | Listas simples, dados em sequência.                  |
| **Set**   | Conjunto que armazena valores únicos.                        | ✖ Não (remove duplicados)    | ✖ Não (HashSet não mantém ordem) | ✖ Não              | ✖ Não                    | Garantir que não existam repetidos, coleções únicas. |
| **Map**   | Estrutura de chave → valor. Cada chave aponta para UM valor. | Chave: ✖ Não<br>Valor: ✔ Sim | ✖ Não (HashMap não ordena)       | ✖ Não              | ✔ Sim (acessa por chave) | Dicionários, cadastros, tabelas de busca, configs.   |

## Tipos de Arrays:

| Estrutura     | Método          | Descrição                                                  | Exemplo de Uso em Java                               |
| ------------- | --------------- | ---------------------------------------------------------- | ---------------------------------------------------- |
| **Array**     | `array[index]`  | Acesso direto por índice.                                  | `int[] arr = {1, 2, 3}; System.out.println(arr[0]);` |
|               | `length`        | Retorna o tamanho do array.                                | `System.out.println(arr.length);`                    |
| **ArrayList** | `add()`         | Adiciona um elemento à lista.                              | `list.add("Java");`                                  |
|               | `get()`         | Obtém o valor pelo índice.                                 | `String value = list.get(0);`                        |
|               | `remove()`      | Remove o elemento especificado ou pelo índice.             | `list.remove(0);`                                    |
|               | `size()`        | Retorna o tamanho da lista.                                | `int size = list.size();`                            |
| **Set**       | `add()`         | Adiciona um elemento ao conjunto (não permite duplicados). | `set.add("Java");`                                   |
|               | `remove()`      | Remove um elemento do conjunto.                            | `set.remove("Java");`                                |
|               | `contains()`    | Verifica se um elemento está presente no conjunto.         | `set.contains("Java");`                              |
|               | `size()`        | Retorna o número de elementos no conjunto.                 | `int size = set.size();`                             |
| **Map**       | `put()`         | Insere um par chave-valor.                                 | `map.put("Java", 1);`                                |
|               | `get()`         | Obtém o valor associado a uma chave.                       | `int value = map.get("Java");`                       |
|               | `remove()`      | Remove a chave e o valor associado.                        | `map.remove("Java");`                                |
|               | `containsKey()` | Verifica se a chave existe no mapa.                        | `map.containsKey("Java");`                           |
|               | `size()`        | Retorna o número de entradas (pares chave-valor) no mapa.  | `int size = map.size();`                             |
|               | `keySet()`      | Retorna um conjunto de todas as chaves do mapa.            | `Set<String> keys = map.keySet();`                   |
|               | `values()`      | Retorna uma coleção de todos os valores do mapa.           | `Collection<Integer> values = map.values();`         |

