# 🔐 Switch | Port Security

O Port Security é um recurso de segurança utilizado em switches gerenciáveis para controlar quais dispositivos podem se conectar a cada porta física.
Ele impede acessos não autorizados, limita ataques internos e protege a rede contra MAC flooding, spoofing e dispositivos desconhecidos.

## Objetivo do Port Security

Restringir quais endereços MAC podem acessar a porta.

Bloquear dispositivos suspeitos ou não cadastrados.

Evitar que usuários troquem o cabo para outro computador.

Reduzir riscos de ataques internos na rede local.

## Como o Port Security Funciona

O switch pode:

Aprender automaticamente o MAC conectado (dynamic).

Salvar MAC manualmente (static).

Limitar o número máximo de MACs por porta.

Bloquear ou apenas alertar quando um MAC inválido tentar entrar.

Tipos de Ações do Port Security

## Quando ocorre uma violação (MAC não permitido), o switch pode agir de três formas:

1. Protect

MACs inválidos são ignorados.

Não gera log.

A porta continua ativa.

2. Restrict

MACs inválidos são bloqueados.

Gera log/SNMP.

A porta continua ativa.

3. Shutdown (Padrão)

MAC inválido → porta desativa (err-disabled).

Requer intervenção para reativar.

Mais seguro: Shutdown
Menos agressivo: Protect

## Parâmetros Comuns nos Switches

| Configuração         | Função                                          |
| -------------------- | ----------------------------------------------- |
| **Maximum MACs**     | Quantos MACs podem usar a porta                 |
| **Sticky MAC**       | Aprende o MAC automaticamente e grava na config |
| **Violation Action** | Ação quando MAC inválido é detectado            |
| **Aging Time**       | Tempo para MACs expirarem                       |
| **Static MAC**       | MAC definido manualmente                        |

Como Configurar Port Security (Visão Geral)

A maioria dos switches segue a mesma estrutura:

Passo 1 — Escolher a porta
Interface → Configurations → Port Security

Passo 2 — Ativar Port Security

Enable

Passo 3 — Definir o número máximo de MACs

Ex.: 1, 2, ou 3

Passo 4 — Escolher a ação em caso de violação

Protect

Restrict

Shutdown

Passo 5 — Opcional: MAC manual
MAC: AA:BB:CC:DD:EE:FF

Passo 6 — Salvar Configurações

Save

Apply

Write Memory
