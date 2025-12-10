# PHP | Introdução ao Doctrine ORM em PHP

Doctrine ORM (Object Relational Mapper) é uma poderosa ferramenta que facilita o trabalho com bancos de dados em PHP. Ele mapeia objetos para tabelas de banco de dados e oferece uma série de funcionalidades avançadas para gerenciamento de dados, incluindo consultas, relacionamentos entre entidades e muito mais.

## Índice

1. [Instalação do Doctrine ORM](#instalacao-do-doctrine-orm)
2. [Configuração Básica](#configuracao-basica)
3. [Criando Entidades](#criando-entidades)
4. [Consultas com Doctrine](#consultas-com-doctrine)
5. [Relacionamentos entre Entidades](#relacionamentos-entre-entidades)
6. [Manipulação de Dados](#manipulacao-de-dados)
7. [Conclusão](#conclusao)

## Instalação do Doctrine ORM

Para usar o Doctrine ORM, é necessário instalá-lo em seu projeto. O método mais comum é através do **Composer**. Se você não tiver o Composer instalado, pode baixar e instalá-lo em [https://getcomposer.org/](https://getcomposer.org/).

Para instalar o Doctrine ORM, execute o seguinte comando no terminal:

```bash
composer require doctrine/orm
<?php
use Doctrine\ORM\Tools\Setup;
use Doctrine\ORM\EntityManager;

// Caminho para as entidades
$paths = ["/path/to/entities"];
$isDevMode = true;

// Configuração do banco de dados
$dbParams = [
    'driver' => 'pdo_mysql',
    'user' => 'usuario',
    'password' => 'senha',
    'dbname' => 'nome_do_banco',
];

$config = Setup::createAnnotationMetadataConfiguration($paths, $isDevMode);
$entityManager = EntityManager::create($dbParams, $config);
````

## Criando Entidades

Em Doctrine, as entidades são representações de tabelas no banco de dados. Para criar uma entidade, você deve criar uma classe e anotá-la com os metadados do Doctrine.

```php
<?php
use Doctrine\ORM\Mapping as ORM;

/**
 * @ORM\Entity
 * @ORM\Table(name="usuarios")
 */
class Usuario
{
    /** 
     * @ORM\Id
     * @ORM\GeneratedValue
     * @ORM\Column(type="integer")
     */
    private $id;

    /** @ORM\Column(type="string") */
    private $nome;

    /** @ORM\Column(type="string") */
    private $email;

    // Getters e setters
}
````

## Criteria API

A Criteria API permite construir consultas programaticamente de forma mais flexível e segura. Exemplo:

````php
use Doctrine\Common\Collections\Criteria;

$criteria = Criteria::create()
    ->where(Criteria::expr()->eq('nome', 'João'))
    ->orderBy(['id' => 'ASC']);
    
$usuarios = $entityManager->getRepository(Usuario::class)->matching($criteria);
````

## Relacionamentos entre Entidades

Doctrine também facilita a definição de relacionamentos entre as entidades. Os tipos mais comuns são OneToMany, ManyToOne e ManyToMany.

```php
/**
 * @ORM\Entity
 * @ORM\Table(name="categorias")
 */
class Categoria
{
    /** 
     * @ORM\Id
     * @ORM\GeneratedValue
     * @ORM\Column(type="integer")
     */
    private $id;

    /** @ORM\Column(type="string") */
    private $nome;

    /** 
     * @ORM\OneToMany(targetEntity="Produto", mappedBy="categoria")
     */
    private $produtos;

    // Getters e setters
}

/**
 * @ORM\Entity
 * @ORM\Table(name="produtos")
 */
class Produto
{
    /** 
     * @ORM\Id
     * @ORM\GeneratedValue
     * @ORM\Column(type="integer")
     */
    private $id;

    /** @ORM\Column(type="string") */
    private $nome;

    /** 
     * @ORM\ManyToOne(targetEntity="Categoria", inversedBy="produtos")
     * @ORM\JoinColumn(name="categoria_id", referencedColumnName="id")
     */
    private $categoria;

    // Getters e setters
}
```

## Manipulação de Dados

Uma das maiores vantagens do Doctrine é a facilidade de manipular dados com objetos PHP.

```php
$usuario = new Usuario();
$usuario->setNome('João');
$usuario->setEmail('joao@example.com');

$entityManager->persist($usuario);
$entityManager->flush();

$usuario = $entityManager->find(Usuario::class, $id);
$usuario->setNome('Novo Nome');
$entityManager->flush();

$usuario = $entityManager->find(Usuario::class, $id);
$entityManager->remove($usuario);
$entityManager->flush();
````
