# 💻 Introdução ao Python

Python é uma linguagem de programação de alto nível, interpretada e orientada a objetos.
É amplamente usada em diversos domínios, como desenvolvimento web, automação, análise de dados, inteligência artificial, entre outros.

## 🧩 Tipos de Variáveis

int: Números inteiros.

float: Números decimais.

str: Strings (sequências de texto).

bool: Valores lógicos (True ou False).

list: Lista de elementos.

tuple: Tupla (sequência imutável).

dict: Dicionário (estrutura de chave-valor).

set: Conjunto (sem valores duplicados).


## ✏️ Declaração de Variáveis

Em Python, não precisamos declarar o tipo de variável explicitamente. O tipo é atribuído dinamicamente.

Exemplo:

```PY
numero = 10
nome = ""
ativo = True
```

## 🌀 Estruturas de Controle
Condicional:
```PY
n1 = 5
n2 = 5

if n1 == n2:
    print("São iguais")
else:
    print("Não são iguais")

Loop (Laço de Repetição):
for i in range(11):
    print(f"Incrementado {i}")
```
## 🗃️ Listas

Em Python, as listas são usadas para armazenar vários itens.

# Criando uma lista
```PY
lista = [1, 2, 3, 5, 6, 7]
```
# Adicionando um item
```PY
lista.append(8)
```
# Removendo o último item
```PY
lista.pop()
```
# Filtrando elementos
```PY
lista_filtrada = [x for x in lista if x > 3]
```

## 🔑 Dicionários (ou Objetos)

Dicionários são estruturas de dados que armazenam pares chave-valor.

# Criando um dicionário

```PY
pessoa = {
    "nome": "Ana",
    "idade": 25,
    "cidade": "São Paulo"
}

# Acessando um valor
print(pessoa["nome"])  # Saída: Ana

# Adicionando ou modificando um valor
pessoa["idade"] = 26
```

## 🧮 Funções

Em Python, as funções são definidas com a palavra-chave def.

# Função simples
```PY
def soma(a, b):
    return a + b
```
# Função com valor de retorno
```PY
resultado = soma(10, 20)
print(resultado)  # Saída: 30

# Função lambda (função anônima)
multiplica = lambda a, b: a * b
print(multiplica(2, 3))  # Saída: 6
```

## 🖥️ Interação com o Usuário

Python permite interação com o usuário via a função input(), que lê entradas no terminal.

```PY
nome = input("Qual é o seu nome? ")
print(f"Olá, {nome}!")

```
## 🧩 Trabalhando com Arquivos

Para ler e escrever arquivos em Python, usamos as funções open(), read(), e write().

# Abrir um arquivo e escrever nele
```PY
with open("exemplo.txt", "w") as arquivo:
    arquivo.write("Olá, Mundo!\nEste é um arquivo de exemplo.")
```
# Ler um arquivo
```PY
with open("exemplo.txt", "r") as arquivo:
    conteudo = arquivo.read()
    print(conteudo)
```

## Exemplo de Uso de Lib(Pacote) tkinter

```PY
from tkinter import *
from tkinter import messagebox
import tkinter as tk

def calc_veiculo():
    try:
       valor_prin = float(entry_valor.get())
       parcela = int(entry_parcela.get())
       FormaPag = str(entry_forma.get())
       debito = valor_prin*0.10
       credito = valor_prin/parcela+0.80
       label_resultado.config(text=f"O Valor total no debito com desconto :{debito:,.2f}")
       label_resultado2.config(text=f"O Valor total no credito será: R$ {credito:,.2f}")
       label_parcela.config(text=f"Quantidade de Parcelas{parcela}")
       label_principal.config(text=f"O Valor Total do veiculo é: {valor_prin:,.2f}")
       label_formapag.config(text=f"A forma de pagamento selecionada: {FormaPag}")
       if FormaPag == 'Pix':
           deb = debito
       elif FormaPag == 'Debito':
           deb = debito
       elif FormaPag == 'Crediario':
           crediario = credito
       else:
           label_formapag.config(text=f"Forma de Pagamento Selecionada Invalida") 
    except ValueError:
        messagebox.showerror("Erro favor Informar valores validos")
    
root = tk.Tk()
root.title("Bem vindo")
root.geometry("500x500")

label_valor = tk.Label(root,text="Valor Inicial do Veiculo")
label_valor.pack(pady=5)
entry_valor=tk.Entry(root)
entry_valor.pack(pady=5)

label_parcela = tk.Label(root,text="Quantidade de parcelas")
label_parcela.pack(pady=5)
entry_parcela=tk.Entry(root)
entry_parcela.pack(pady=5)

label_forma = tk.Label(root,text="Forma de Pagamento")
label_forma.pack(pady=5)
entry_forma=tk.Entry(root)
entry_forma.pack(pady=5)

botao_calc = tk.Button(root,text="Calcular",command=calc_veiculo)
botao_calc.pack(pady=20)

label_parcela = tk.Label(root,text="Quantidade de parcelas",font=("Arial", 12, "bold"))
label_parcela.pack(pady=10)

label_principal = tk.Label(root,text="Valor do Veiculo",font=("Arial", 12, "bold"))
label_principal.pack(pady=10)

label_resultado = tk.Label(root,text="Valor Total No debito R$",font=("Arial", 12, "bold"))
label_resultado.pack(pady=10)

label_resultado2 = tk.Label(root,text=" Valor no credito R$",font=("Arial", 12, "bold"))
label_resultado2.pack(pady=10)

label_formapag = tk.Label(root,text="Forma de Pagamento",font=("Arial", 12, "bold"))
label_formapag.pack(pady=10)

root.mainloop()
```

## Usando API Moeda
```PY
import requests

url = "https://economia.awesomeapi.com.br/json/last/USD-BRL,BTC-BRL,EUR-BRL,CNY-BRL,GBP-BRL,ARS-BRL,JPY-BRL,RUB-BRL"

resposta = requests.get(url)

if resposta.status_code == 200:
    dados = resposta.json()
    print(dados)  # Aqui você pode acessar, por exemplo: dados["USDBRL"]["bid"]
  print("Dólar:", dados["USDBRL"]["bid"])
print("Dólar:", dados["USDBRL"]["bid"])
print("Dólar:", dados["USDBRL"]["bid"])
print("Dólar:", dados["USDBRL"]["bid"])
print("Dólar:", dados["USDBRL"]["bid"])
print("Dólar:", dados["USDBRL"]["bid"])
print("Dólar:", dados["USDBRL"]["bid"])
print("Dólar:", dados["USDBRL"]["bid"])
else:
    print("Erro:", resposta.status_code)
```

