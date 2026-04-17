# Arquitetura da Solução

## Visão Geral

A solução foi desenhada seguindo princípios de escalabilidade, resiliência, segurança e simplicidade operacional.

O sistema é composto por uma aplicação principal responsável pelo controle financeiro, exposta por APIs seguras e integrada a serviços de persistência, autenticação e monitoramento.

## Componentes Principais

- Frontend Web ou Mobile para interação do usuário.
- API Gateway para entrada única das requisições.
- Serviço de Cashflow contendo regras de negócio.
- Banco de Dados relacional para persistência.
- Serviço de autenticação/autorização.
- Camada de observabilidade com logs, métricas e alertas.

## Fluxo Resumido

1. Usuário acessa aplicação.
2. Requisição passa pelo API Gateway.
3. Token é validado.
4. Serviço Cashflow processa a operação.
5. Dados são persistidos no banco.
6. Logs e métricas são enviados ao monitoramento.

## Diagrama

```text
┌──────────────┐
│   Usuário    │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│   Frontend   │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ API Gateway  │
└──────┬───────┘
       │
       ▼
┌──────────────────────┐
│ Serviço Cashflow     │
└──────┬────────┬──────┘
       │        │
       ▼        ▼
┌──────────┐   ┌───────────────┐
│ Banco de │   │ Observability │
│ Dados    │   │ Logs/Metrics  │
└──────────┘   └───────────────┘
