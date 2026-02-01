# Variáveis e Escopo no Shell

As variáveis no Shell são simples, mas muito poderosas. Aqui você vai aprender:
- Variáveis simples
- Variáveis de ambiente (globais)
- Escopo local
- Arrays
- Substituição de comandos

---

## 📌 Variáveis Simples

```bash
nome="Albertool"
idade=22
echo "$nome"
```

## 📌Variáveis de Ambiente (Globais)

Essas são visíveis por TODOS os processos.
```bash
export APP_VERSION="1.0"

Ver todas:

printenv
```

## Substituição de Comando

Coloca o resultado de um comando dentro de uma variável.
```bash
data=$(date)
arquivos=$(ls -1)
```
## Arrays em Bash
```bash
frutas=("maçã" "uva" "banana")
echo "${frutas[1]}"   # uva
echo "${frutas[@]}"   # imprime todas

##  Escopo Local (Dentro de Funções)

Sem local, tudo vira variável global.

teste() {
    local nome="Interno"
    echo "$nome"
}
```
```bash
teste
echo "$nome"  # vazio, pois 'nome' era local
```
##  Escopo Global

Variáveis criadas fora das funções são globais:
```bash
mensagem="Olá"
func() {
    echo "$mensagem"
}
func
```
