# 🔌 Switch | Configuração de VLAN

A configuração de VLAN (Virtual LAN) permite separar a rede em segmentos independentes, melhorando segurança, desempenho e organização.

Abaixo está um guia simples e universal que funciona para a maioria dos switches gerenciáveis (Cisco, HP, Intelbras, TP-Link, D-Link, Aruba, Dell).

## 🟦  Acessar o Switch

Antes de configurar:

Conecte um cabo de rede do PC ao switch.

Acesse o IP padrão do equipamento (exemplos):

- 192.168.0.1

- 192.168.1.1

- 192.168.0.254

Login padrão (pode variar):

Usuário: admin

Senha: admin

## 🟩  Criar as VLANs

No menu do switch procure por algo como:

Switching → VLAN → VLAN Settings

VLAN Management

802.1Q VLAN

## Crie as VLANs que desejar:

| VLAN | Nome           | Função             |
| ---- | -------------- | ------------------ |
| 10   | Administrativa | TI, servidores     |
| 20   | Vendas         | Setor comercial    |
| 30   | Visitantes     | Rede de convidados |


## Atribuir Portas às VLANs

Agora defina quais portas pertencem a cada VLAN:

Access Port → porta pertence a uma única VLAN

Trunk Port → porta carrega várias VLANs (para outro switch, roteador ou firewall)

### Exemplo de configuração Access:

| Porta | VLAN | Tipo   |
| ----- | ---- | ------ |
| 1     | 10   | Access |
| 2     | 20   | Access |
| 3     | 30   | Access |

## Exemplo de Trunk:

| Porta | VLANs Permitidas | Tipo  |
| ----- | ---------------- | ----- |
| 24    | 10,20,30         | Trunk |


## Salvar as Configurações

Quase todos switches exigem salvar manualmente:

Save

Apply

Save to Flash

Write Memory (Cisco)

Se não salvar, o switch perde a configuração após reiniciar.
