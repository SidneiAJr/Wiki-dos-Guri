# Sprint WEB - JAVA
```Java
// Pacote principal da aplicação Spring Boot
package com.example.demo;

import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.context.annotation.Bean;
import org.springframework.web.client.RestTemplate;

import java.util.List;
import java.util.Scanner;

// Anotação que marca a classe como uma aplicação Spring Boot
@SpringBootApplication
public class DemoApplication implements CommandLineRunner {

    // Instância de RestTemplate, utilizada para realizar requisições HTTP
    private final RestTemplate restTemplate;

    // Construtor que injeta a dependência do RestTemplate
    public DemoApplication(RestTemplate restTemplate) {
        this.restTemplate = restTemplate;
    }

    // Método principal que executa a aplicação Spring Boot
    public static void main(String[] args) {
        // Inicializa a aplicação Spring Boot
        SpringApplication.run(DemoApplication.class, args);
    }

    // Definição de um Bean que cria uma instância do RestTemplate
    @Bean
    public RestTemplate restTemplate() {
        return new RestTemplate(); // Cria uma nova instância de RestTemplate
    }

    // Método implementado da interface CommandLineRunner
    // Esse método será executado após a aplicação Spring Boot iniciar
    public void run(String... args) {
        // Scanner para ler a entrada do usuário
        Scanner entradainfo = new Scanner(System.in);
        int op = 0;

        // Laço que exibe o menu de opções e realiza a interação com o usuário
        while (op != 5) {
            System.out.println("Bem vindo ao sistema da Biblioteca:");
            System.out.println("Por Favor Selecione uma Opcao");
            System.out.println("1 - Ver catálogo");
            System.out.println("2 - Buscar Livro");
            System.out.println("3 - Lista de Autor");
            System.out.println("4 - Livros em outro Idioma");
            System.out.println("5 - Sair");

            // Lê a opção do usuário
            op = entradainfo.nextInt();
            entradainfo.nextLine(); // Limpa o buffer de entrada

            // Switch para executar a ação baseada na escolha do usuário
            switch (op) {
                case 1 -> vercatalogo();  // Exibe o catálogo de livros
                case 2 -> buscarlivro(entradainfo); // Realiza a busca por livro
                case 3 -> listarautor();  // Lista autores (não implementado)
                case 4 -> livroidioma();  // Busca livros por idioma (não implementado)
                case 5 -> System.out.println("Encerrando...");  // Finaliza o programa
                default -> System.out.println("Opção inválida.");  // Caso o usuário insira uma opção inválida
            }
        }
    }

    // Método que exibe um catálogo fixo de livros (em português)
    private void vercatalogo() {
        String[] livros = {
                "Autor: Pedro Luz, Ano: 2022, Idioma: Português, Avaliação: 4",
                "Autor: Pedro Luz Jr, Ano: 2023, Idioma: Português, Avaliação: 2",
                "Autor: Pedro Klaus, Ano: 2020, Idioma: Português, Avaliação: 1.5",
                "Autor: Pedro Luis, Ano: 2019, Idioma: Português, Avaliação: 3",
                "Autor: Pedro Miguel, Ano: 2016, Idioma: Português, Avaliação: 2.5"
        };
        // Exibe todos os livros do catálogo
        for (String livro : livros) {
            System.out.println(livro);
        }
    }

    // Método que busca livros por nome ou autor através de uma API externa
    private void buscarlivro(Scanner sc) {
        System.out.print("Digite o nome do livro ou autor para buscar: ");
        String termo = sc.nextLine(); // Lê o termo de pesquisa

        // URL da API que será chamada com o termo de pesquisa
        String url = "https://gutendex.com/books/?search=" + termo;

        // Realiza a requisição GET à API e converte a resposta para o objeto RespostaAPI
        RespostaAPI resposta = restTemplate.getForObject(url, RespostaAPI.class);

        // Se a resposta não for nula e contiver resultados, exibe os livros encontrados
        if (resposta != null && resposta.getResults() != null) {
            System.out.println("Resultados encontrados:");
            for (Livro livro : resposta.getResults()) {
                // Exibe título, autores e idiomas dos livros encontrados
                System.out.println("Título: " + livro.getTitle());
                System.out.println("Autor(es): " + livro.getAuthors().stream().map(Autor::getName).toList());
                System.out.println("Idioma(s): " + livro.getLanguages());
                System.out.println("---------------");
            }
        } else {
            System.out.println("Nenhum livro encontrado.");
        }
    }

    // Método que ainda não está implementado: lista os autores
    private void listarautor() {
        System.out.println("Função de listar autor ainda não implementada.");
    }

    // Método que ainda não está implementado: busca livros por idioma
    private void livroidioma() {
        System.out.println("Função de buscar por idioma ainda não implementada.");
    }

    // CLASSES INTERNAS

    // Classe representando um livro
    static class Livro {
        private String title;  // Título do livro
        private List<Autor> authors;  // Lista de autores
        private List<String> languages;  // Lista de idiomas

        public String getTitle() {
            return title;
        }

        public List<Autor> getAuthors() {
            return authors;
        }

        public List<String> getLanguages() {
            return languages;
        }
    }

    // Classe representando um autor de livro
    static class Autor {
        private String name;  // Nome do autor

        public String getName() {
            return name;
        }
    }

    // Classe que representa a resposta da API
    static class RespostaAPI {
        private List<Livro> results;  // Lista de livros retornados pela API

        public List<Livro> getResults() {
            return results;
        }
    }
}
```
