# Desafio Técnico – Arquiteto de Soluções

## Visão Geral

Este repositório apresenta uma proposta de solução arquitetural para o desafio técnico de uma vaga de **Arquiteto de Soluções**, cujo objetivo é controlar o fluxo de caixa diário de um comerciante, contemplando lançamentos financeiros (créditos e débitos) e a disponibilização do saldo diário consolidado.

Mais do que uma entrega funcional, esta proposta busca demonstrar capacidade analítica, visão sistêmica, tomada de decisão arquitetural, atenção a requisitos não funcionais e organização técnica da solução.

---

## Objetivo do Negócio

Permitir que o comerciante consiga:

- registrar créditos e débitos diários  
- consultar lançamentos realizados  
- visualizar saldo consolidado por data  
- operar com confiabilidade mesmo diante de falhas parciais do sistema  

---

## Proposta de Solução

A arquitetura foi desenhada com separação entre dois contextos principais:

### 1. Serviço de Lançamentos

Responsável por:

- receber movimentações financeiras  
- validar dados de entrada  
- persistir lançamentos  
- publicar eventos de negócio  

### 2. Serviço de Consolidado Diário

Responsável por:

- consumir eventos de lançamentos  
- calcular saldo diário  
- disponibilizar consulta consolidada  

### Integração entre Serviços

A comunicação ocorre por **mensageria assíncrona**, reduzindo acoplamento e aumentando resiliência.

Essa decisão atende diretamente ao requisito de que o serviço de lançamentos continue disponível mesmo que o serviço de consolidado fique indisponível.

---

## Arquitetura Resumida

```text
┌─────────┐
│ Cliente │
└────┬────┘
     │
     ▼
┌─────────────────────────┐
│ Serviço de Lançamentos  │
└──────────┬──────────────┘
           │
           ▼
┌─────────────────────────┐
│ Fila / Broker           │
│ de Mensagens            │
└──────────┬──────────────┘
           │
           ▼
┌─────────────────────────┐
│ Serviço de Consolidado  │
│ Diário                  │
└─────────────────────────┘
