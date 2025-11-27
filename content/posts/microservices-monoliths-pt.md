---
title: "Microservices Monoliths - Portuguese"
date: 2030-11-26T16:02:19-03:00
draft: true
---

## Índice
- [Microsserviços e Arquitetura Baseada em Eventos](#microsserviços-e-arquitetura-baseada-em-eventos)
- [Sistemas Monolíticos](#sistemas-monolíticos)
- [O que são Microsserviços](#o-que-são-microsserviços)
- [Arquitetura Baseada em Microsserviços](#arquitetura-baseada-em-microsserviços)
- [Setup de Microsserviços](#setup-de-microsserviços)
- [Escalando Microsserviços: Realidade x Mito](#escalando-microsserviços-realidade-x-mito)
- [Arquiteturas Distribuídas são Necessárias](#arquiteturas-distribuídas-são-necessárias)
- [Quando Optar por Sistemas Monolíticos](#quando-optar-por-sistemas-monolíticos)
- [Quando Optar por Microsserviços](#quando-optar-por-microsserviços)
- [Provocação: Você Está Preparado Para Microsserviços?](#provocação-você-está-preparado-para-microsserviços)

Microsserviços e Arquitetura Baseada em Eventos
Introdução ao Módulo: Arquitetura Baseada em Microsserviços

Neste módulo, exploramos os fundamentos essenciais da arquitetura de microsserviços, ajustando desde já as expectativas para que você saiba exatamente o que aprenderá.

Por que estudar microsserviços?

Embora muito utilizados em grandes empresas, microsserviços frequentemente falham na prática — não por problemas técnicos, mas por falta de compreensão conceitual por parte de desenvolvedores, tech leads e arquitetos.

Muitas vezes são implementados pelos motivos errados, sem clareza de objetivos ou domínio dos fundamentos.

O que você vai aprender neste módulo

Fundamentos da arquitetura baseada em microsserviços

Quando utilizar e quando evitar microsserviços

Como funcionam na prática e seus principais desafios

Estratégias para reduzir riscos de falhas

Como evitar a “estrela da morte” (excesso de dependências)

Diferença entre coreografia e orquestração

A importância do módulo

Grande parte do conteúdo é teórica, pois o maior desafio não está em criar um microsserviço isolado — isso é simples — mas em entender como compor e organizar a arquitetura como um todo.

Nosso objetivo

Compartilhar princípios sólidos para acelerar sua jornada e ajudar a evitar armadilhas comuns.

Sistemas Monolíticos
O que é um sistema monolítico?

Um monolito concentra todos os escopos e áreas dentro de uma única aplicação.

Características:

Todos os componentes e funcionalidades reunidos no mesmo sistema

Comunicação interna simples (chamadas diretas)

Modelo ainda predominante no mercado

Trabalho em equipe dentro do monolito

Squads atuam em partes distintas dentro do mesmo sistema

Requer organização para evitar conflitos no Git

Testes automatizados reduzem riscos

Benefícios práticos

Custo reduzido em infraestrutura

Atende muito bem empresas pequenas e médias

Produtividade mais alta com padrões unificados

Restrições tecnológicas

Linguagem única

Sem filas, circuit breaker, múltiplos bancos

Deploy simples

Riscos no deploy

Se falhar, o sistema inteiro cai

Microsserviços reduzem esse risco

Estratégias como blue-green diminuem impactos

Conclusão sobre monólitos

Simples, eficientes e totalmente adequados para muitos cenários, especialmente no início.

O que são Microsserviços

Microsserviços são aplicações pequenas, independentes e com escopo bem definido.

Princípio central

Eles devem ter apenas um motivo para mudar (SRP — Single Responsibility Principle).

Relação com Domain-Driven Design (DDD)

Bounded Contexts ajudam a identificar serviços

Mas nem todo contexto vira um microsserviço

Independência e Autonomia

Todo microsserviço deve:

Continuar funcionando mesmo que outros falhem

Possuir mecanismos de fallback

Exemplo:
Exibir saldo bancário mesmo se o serviço de cálculo estiver fora do ar → mostrar o último valor conhecido.
Isso é Graceful Degradation.

Parte de uma engrenagem maior

Um microsserviço isolado não é um microsserviço — é apenas um sistema pequeno.

Resumo

Escopo claro

Independente e autônomo

Parte de um ecossistema

Comunicação mais complexa

Arquitetura Baseada em Microsserviços
Microsserviço ≠ Arquitetura

Microsserviço = unidade de software

Arquitetura = como essas unidades se organizam

Características principais
Uso de múltiplas tecnologias

Cada serviço pode usar linguagens e bancos diferentes — mas isso exige governança.

Governança vs liberdade total

Padrões aumentam a produtividade

Microgerenciamento atrapalha

“Lei da Familiaridade”: eficiência cresce com padrões claros

Times de plataforma criam:

Templates

SDKs

Padrões internos

Ferramentas

O mito da liberdade total

Tecnologias demais geram sistemas caros e difíceis de manter.

Resumo

Microsserviços exigem:

Governança

Padronização

Equilíbrio entre liberdade e consistência

Setup de Microsserviços
1. Deploy menos arriscado

Se 1 serviço falha, os outros continuam

Reduz impacto no usuário

Mas aumenta a complexidade:

CI/CD por serviço

Monitoramento específico

Infra por serviço

2. Equipes especializadas

Microsserviços permitem:

Times focados em domínios

Mais profundidade técnica

Mais valor entregue

Escalando Microsserviços: Realidade x Mito
1. Promessa da escalabilidade seletiva

Escalar apenas partes críticas

Evita desperdício

2. O lado oculto

Muitos pipelines

Infra mais cara

Monitoramento complexo

3. O mito de que monólitos não escalam

Monólitos escalam vertical e horizontalmente.

4. Comunicação entre serviços

Ferramentas como Kafka, RabbitMQ, SQS:

Aumentam a complexidade

Mudam cultura

Aumentam custos

Conclusão

Microsserviços só fazem sentido em ambientes realmente grandes.

Arquiteturas Distribuídas são Necessárias
1. Por que grandes empresas precisam?

Muitos devs

Domínios enormes

Negócios complexos

2. Microsserviços: o “remédio amargo”

Difícil

Caro

Necessário em larga escala

3. Reflexão

A escolha depende do contexto — não da moda.

Quando Optar por Sistemas Monolíticos

MVPs e POCs

Descoberta de produto

Mudanças frequentes

Baixa maturidade em governança

Equipes pequenas

Orçamento limitado

Monólito = simples, barato e rápido.

Quando Optar por Microsserviços

Muitas equipes trabalhando ao mesmo tempo

Domínios bem definidos

Necessidade de escalar partes isoladas

Uso de múltiplas tecnologias

Microsserviços são sobre escalar organizações, não apenas sistemas.

Provocação: Você Está Preparado Para Microsserviços?

É necessário dominar:

Containers

CI/CD

Arquitetura distribuída

Comunicação assíncrona

Bancos independentes

Observabilidade (logs, métricas, tracing)

DDD

Ambiente distribuído é como o painel de um avião:

Não precisa apertar todos os botões agora

Mas precisa conhecê-los

Porque um dia você vai usar

Esse é o roadmap para maturidade real em microsserviços.
