# ORMs para PHP

Existem diversas opções de ORMs (Object-Relational Mappers) para PHP que podem ser usadas para facilitar a interação entre a aplicação PHP e o banco de dados. Abaixo estão algumas das opções mais populares:

## 1. [Doctrine ORM](#doctrine-orm)
   - **Descrição**: O Doctrine é um dos ORMs mais populares para PHP. Ele oferece uma abordagem orientada a objetos para gerenciar dados e é altamente configurável. Suporta tanto consultas DQL (Doctrine Query Language) quanto Criteria API e é amplamente utilizado em frameworks como Symfony.
   - **Link**: [Doctrine ORM](https://www.doctrine-project.org/projects/orm.html)

## 2. [Eloquent ORM](#eloquent-orm)
   - **Descrição**: Eloquent é o ORM do framework Laravel. Ele oferece uma API simples e expressiva para trabalhar com bancos de dados, com suporte para relações entre modelos (One-to-One, One-to-Many, Many-to-Many). É uma ótima escolha para quem está utilizando o Laravel.
   - **Link**: [Eloquent ORM](https://laravel.com/docs/8.x/eloquent)

## 3. [RedbeanPHP](#redbeanphp)
   - **Descrição**: RedbeanPHP é um ORM simples e sem configurações. Ele é focado em rapidez e flexibilidade. Não exige a criação de migrações, já que cria a estrutura do banco automaticamente a partir das entidades.
   - **Link**: [RedbeanPHP](https://redbeanphp.com/)

## 4. [Propel ORM](#propel-orm)
   - **Descrição**: Propel é um ORM poderoso e fácil de usar. Ele suporta tanto consultas SQL nativas quanto consultas baseadas em objetos. O Propel também permite o uso de migrações e tem suporte para múltiplos bancos de dados.
   - **Link**: [Propel ORM](https://propelorm.org/)

## 5. [Yii ActiveRecord](#yii-activerecord)
   - **Descrição**: O Yii é um framework PHP que tem um ORM integrado chamado ActiveRecord. Ele facilita o mapeamento de objetos para tabelas do banco de dados e inclui métodos úteis para realizar operações CRUD.
   - **Link**: [Yii ActiveRecord](https://www.yiiframework.com/doc/guide/2.0/en/db-active-record)

## 6. [Slim ORM](#slim-orm)
   - **Descrição**: Slim ORM é um ORM minimalista baseado em PDO. Ele não tem tantas funcionalidades quanto o Doctrine ou Eloquent, mas é uma escolha interessante para projetos pequenos e para quem deseja algo simples e direto.
   - **Link**: [Slim ORM](https://github.com/candango/slim-orm)

## 7. [Mysqli ORM](#mysqli-orm)
   - **Descrição**: MySQLi ORM não é uma biblioteca, mas uma forma de usar a biblioteca **MySQLi** do PHP em um estilo orientado a objetos. Ao invés de usar consultas SQL diretas, ele facilita a manipulação de dados de forma orientada a objetos.
   - **Link**: [MySQLi Manual](https://www.php.net/manual/en/book.mysqli.php)

## 8. [CakePHP ORM](#cakephp-orm)
   - **Descrição**: O CakePHP fornece uma solução ORM integrada para trabalhar com bancos de dados. O ORM do CakePHP é altamente configurável e suporta associações, validações e consultas complexas de forma simples.
   - **Link**: [CakePHP ORM](https://book.cakephp.org/4/en/orm.html)

## 9. [Aura.SQL](#aurasql)
   - **Descrição**: Aura.SQL não é um ORM tradicional, mas sim uma biblioteca que permite mapear objetos para tabelas de forma orientada a objetos. Ela pode ser usada como um ORM leve e simples, ideal para quem quer maior controle sobre o banco de dados.
   - **Link**: [Aura.SQL](https://github.com/auraphp/Aura.Sql)

## 10. [MongoDB ODM (Doctrine MongoDB)](#mongodb-odm-doctrine-mongodb)
   - **Descrição**: Doctrine MongoDB ODM (Object-Document Mapper) é a versão do Doctrine para bancos de dados NoSQL, como o MongoDB. Ele permite trabalhar com documentos no MongoDB de maneira orientada a objetos.
   - **Link**: [Doctrine MongoDB ODM](https://www.doctrine-project.org/projects/doctrine-mongodb-odm.html)

## 11. [Phalcon ORM](#phalcon-orm)
   - **Descrição**: Phalcon é um framework PHP de alto desempenho que inclui um ORM rápido e eficiente. Ele oferece suporte para consultas SQL e pode ser uma ótima escolha para aplicações de alta performance.
   - **Link**: [Phalcon ORM](https://phalcon.io/en-us/docs/3.4/reference/orm)

## 12. [FluentPDO](#fluentpdo)
   - **Descrição**: FluentPDO é um ORM baseado em um construtor de consultas fluente. Ele não é um ORM tradicional, mas uma abordagem para escrever consultas SQL de maneira mais amigável e legível.
   - **Link**: [FluentPDO](https://github.com/fluxus/fluentpdo)

## Conclusão

Existem muitos ORMs disponíveis para PHP, e a escolha do melhor ORM depende de vários fatores, como a complexidade do projeto, a preferência pessoal e o framework que você está utilizando. O **Doctrine ORM** é uma das opções mais poderosas e flexíveis, mas outros ORMs como o **Eloquent**, **RedbeanPHP** e **Propel** também são ótimas escolhas para projetos específicos.

Ao escolher um ORM, é importante também considerar a performance, facilidade de uso e a compatibilidade com as versões do PHP e do banco de dados que você está utilizando.
