# 🔌 Switch | Configuração Básica

Configurar um switch gerenciável exige alguns passos fundamentais.
Este guia explica o processo inicial de forma simples e clara.

## 📡 `Acessando o Switch pela Primeira Vez`

A maior parte dos switches usa um IP padrão de fábrica, como:

- 192.168.0.1

- 192.168.1.1

- 192.168.0.254

- 192.168.2.1

Esse IP varia conforme o fabricante e o modelo.

Passo a passo para acessar:

Conecte o PC diretamente na porta do switch (geralmente porta 1 ou a porta marcada como MGMT).

Configure o computador com um IP fixo da mesma faixa, por exemplo:

- IP: 192.168.0.10

- Máscara: 255.255.255.0

Abra o navegador e digite o IP padrão do switch.

## `Usuário e Senha Padrão`

Cada fabricante define credenciais iniciais diferentes.
Os mais comuns:

Usuário: admin

Senha: admin


Usuário: admin

Senha: password

## Configurações Básicas Necessárias

Alterar IP do Switch

Defina o IP da sua rede:

Exemplo: 192.168.1.2

Máscara: 255.255.255.0

Gateway: conforme a rede local

## Criar VLANs (opcional, mas comum)

Separação de setores, segurança e organização da rede.

| VLAN | Descrição     |
| ---- | ------------- |
| 10   | Administração |
| 20   | Operacional   |
| 30   | Visitantes    |


