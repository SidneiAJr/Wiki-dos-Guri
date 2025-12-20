# 🐚 Shell Script | Tutorial Básico

## O Shell Script é usado para automatizar tarefas no Linux, manipular arquivos, criar sistemas simples e muito mais.

Este guia cobre os principais fundamentos:

- Variáveis

- Funções

- Loop (for, while)

- Condicionais (case)

- Arrays

## 🧩 Variáveis no Shell

O Shell não tem tipos — tudo é string, e números só funcionam em operações aritméticas.

`Criando variáveis`

```shell
nome="S"
idade=25
````

`Usando variáveis`
```shell
echo "Nome: $nome"
echo "Idade: $idade"
````

## 🧩Operações Aritméticas
```shell
echo $((10 + 20))
resultado=$((5 * 5))
echo $resultado
````

## 🧩Funções em Shell
```shell
minha_funcao() {
    echo "Rodando função!"
}
````

## 🧩 Função com Parametro
```Shell
login() {
    usuario=$1
    senha=$2
    echo "Usuário: $usuario | Senha: $senha"
}
login "admin" "123"
````

## 🧩 Arrays

```shell
frutas=("maçã" "banana" "uva")
// Lendo o array
for fruta in "${frutas[@]}"; do
    echo "$fruta"
done
````

## 🧩 Condicionais

```shell
if [ $idade -ge 18 ]; then
    echo "Maior de idade"
else
    echo "Menor"
fi
```
| Comparação | Significado             |
| ---------- | ----------------------- |
| `-eq`      | igual                   |
| `-ne`      | diferente               |
| `-gt`      | maior                   |
| `-lt`      | menor                   |
| `-ge`      | maior ou igual          |
| `-le`      | menor ou igual          |
| `=`        | igualdade entre strings |

## 🧩 Switch Case
```shell
case $opcao in
    1) echo "Opção 1";;
    2) echo "Opção 2";;
    *) echo "Inválido";;
esac
```

## 🧩Loops
```shell
for i in {1..5}; do
    echo "$i"
done
contador=1

while [ $contador -le 5 ]; do
    echo "$contador"
    contador=$((contador+1))
done
```

## 🧩Entrada do usuário
```shell
read -p "Digite seu nome: " nome
echo "Olá, $nome!"
```

##🧩Trabalhando com Arquivos
```shell
touch arquivo.txt
cp a.txt b.txt
mv a.txt pasta/
rm arquivo.txt
````

| Comando | Função                   |
| ------- | ------------------------ |
| `>`     | sobrescreve arquivo      |
| `>>`    | adiciona ao arquivo      |
| `<`     | usa arquivo como entrada |
| `2>`    | redireciona erros        |
| `&>`    | saída + erro             |


