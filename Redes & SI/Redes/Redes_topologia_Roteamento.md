# 1. Topologias de Redes

As topologias de redes definem a estrutura física e lógica de como os dispositivos estão conectados em uma rede. Cada tipo de topologia tem suas vantagens e desvantagens, e a escolha depende das necessidades específicas da rede. Abaixo estão as principais topologias de redes:

## 1.1. Topologia de Barramento

Na **topologia de barramento**, todos os dispositivos estão conectados a um único cabo compartilhado. Esse cabo atua como o meio de transmissão de dados entre todos os dispositivos da rede.

### Características:
- **Simplicidade**: Fácil de implementar e configurar.
- **Custo**: Baixo custo devido ao uso de um único cabo.
- **Desvantagens**: Se o cabo principal falhar, toda a rede é afetada. A performance também pode cair conforme o número de dispositivos aumenta.

### Exemplos de uso:
- Redes pequenas e locais onde o custo e a simplicidade são mais importantes que a escalabilidade.

---

## 1.2. Topologia de Estrela

Na **topologia de estrela**, todos os dispositivos estão conectados a um único ponto central, geralmente um switch ou roteador. A comunicação entre dispositivos é feita através desse ponto central.

### Características:
- **Facilidade de gerenciamento**: Como os dispositivos estão centralizados, fica mais fácil gerenciar e resolver problemas.
- **Resiliência**: Se um dispositivo falhar, apenas aquele dispositivo será afetado, não a rede inteira.
- **Desvantagens**: O ponto central é um ponto único de falha. Se o switch ou roteador falhar, toda a rede fica inoperante.

### Exemplos de uso:
- Redes empresariais, onde a confiabilidade e a facilidade de gerenciamento são cruciais.

---

## 1.3. Topologia de Anel

Na **topologia de anel**, os dispositivos são conectados em um formato circular. Cada dispositivo possui uma conexão direta com dois outros dispositivos, formando um "anel".

### Características:
- **Transmissão de dados**: Os dados viajam em uma direção ou ambas, dependendo da implementação, até alcançar o destino.
- **Desvantagens**: Se um único dispositivo ou conexão falhar, toda a rede pode ser interrompida.
- **Desempenho**: Pode ser afetado à medida que a rede cresce, já que todos os dados precisam passar por cada dispositivo até atingir o destino.

### Exemplos de uso:
- Redes de campus ou em ambientes controlados onde o tráfego de dados é moderado.

---

## 1.4. Topologia de Malha

Na **topologia de malha**, cada dispositivo está conectado a todos os outros dispositivos, criando várias rotas possíveis para os dados. Essa topologia oferece alta redundância e resiliência.

### Características:
- **Alta confiabilidade**: Se uma conexão falhar, os dados podem ser enviados por outra rota.
- **Desempenho**: Excelente em termos de velocidade e estabilidade, mas o custo de implementação pode ser elevado devido ao número de cabos e equipamentos necessários.
- **Desvantagens**: Custo e complexidade aumentam à medida que mais dispositivos são adicionados.

### Exemplos de uso:
- Redes corporativas de missão crítica, como em datacenters ou grandes empresas que necessitam de alta disponibilidade.

---

## 1.5. Topologia Híbrida

A **topologia híbrida** combina duas ou mais topologias diferentes, como estrela e barramento ou estrela e malha, para atender às necessidades específicas da rede.

### Características:
- **Flexibilidade**: Oferece o melhor de várias topologias, permitindo soluções customizadas.
- **Complexidade**: Pode ser mais difícil de gerenciar e configurar devido à combinação de diferentes topologias.

### Exemplos de uso:
- Redes empresariais grandes, onde é necessário balancear custo, desempenho e resiliência.

---

# 2. Protocolos de Roteamento

O roteamento é o processo de encaminhamento de pacotes de dados entre redes diferentes. Para que esse processo seja eficiente e seguro, são usados **protocolos de roteamento**. Existem dois tipos principais de protocolos de roteamento: os **Protocolos de Roteamento Interior (IGP)** e os **Protocolos de Roteamento Exterior (EGP)**.

## 2.1. Roteamento Estático vs Roteamento Dinâmico

- **Roteamento Estático**: O roteador é configurado manualmente com as rotas. Ideal para redes simples e pequenas, mas não é escalável e não se adapta automaticamente a mudanças na rede.
- **Roteamento Dinâmico**: O roteador ajusta automaticamente as rotas com base nas mudanças da rede, utilizando protocolos de roteamento. Esse método é mais eficiente e adequado para redes grandes e complexas.

---

## 2.2. Protocolos de Roteamento Interior (IGP)

### 2.2.1. RIP (Routing Information Protocol)

O **RIP** é um dos protocolos de roteamento mais antigos. Ele usa o número de saltos (hops) como métrica para determinar o melhor caminho. O RIP v1 e v2 são amplamente utilizados, sendo o v2 mais seguro, pois suporta autenticação.

- **RIP v1**: Não suporta VLSM (Variable Length Subnet Mask), ou seja, não pode trabalhar com sub-redes de diferentes tamanhos na mesma rede.
- **RIP v2**: Suporta VLSM e autenticação, o que o torna mais seguro que a versão 1.

### 2.2.2. OSPF (Open Shortest Path First)

O **OSPF** é um protocolo de roteamento baseado em **estado de link** e utiliza o algoritmo SPF (Shortest Path First). Ele é mais escalável e eficiente que o RIP e é amplamente usado em grandes redes.

- **Vantagens**: Escalabilidade, eficiência e suporte a VLSM.
- **Desvantagens**: Mais complexo de configurar e administrar que o RIP.

### 2.2.3. EIGRP (Enhanced Interior Gateway Routing Protocol)

O **EIGRP** é um protocolo híbrido, que combina características de roteamento vetorial e de estado de link. Ele usa o **algoritmo DUAL** (Diffusing Update Algorithm) para calcular a melhor rota.

- **Vantagens**: Menor uso de largura de banda, convergência rápida e suporte a VLSM.
- **Desvantagens**: É proprietário da Cisco, o que significa que ele não é compatível com dispositivos de outros fabricantes.

---

## 2.3. Protocolos de Roteamento Exterior (EGP)

### 2.3.1. BGP (Border Gateway Protocol)

O **BGP** é o protocolo de roteamento utilizado na troca de informações de roteamento entre diferentes sistemas autônomos (AS) na internet. Ele é fundamental para o roteamento de tráfego na internet global.

- **Vantagens**: Alta escalabilidade e robustez.
- **Desvantagens**: Complexidade de configuração e manutenção. Também é mais suscetível a falhas de segurança se não for configurado corretamente.

---

Esses são os tópicos básicos de **Topologias de Redes** e **Protocolos de Roteamento**. Você pode expandir mais cada um desses pontos dependendo da complexidade e profundidade que deseja para sua wiki. Se precisar de mais informações ou algum ajuste específico, só avisar!
