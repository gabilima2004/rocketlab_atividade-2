# rocketlab_atividade-2

# CineData Analytics — Arquitetura Medalhão

Projeto desenvolvido para a Atividade 2 de Engenharia de Dados, utilizando uma arquitetura Medalhão (Bronze, Silver e Gold) para processamento e análise de dados de filmes.

## Tecnologias

- Python
- PySpark
- Databricks
- Delta Lake
- SQL

## Arquitetura

### Bronze

Camada responsável pela ingestão dos dados brutos, preservando sua estrutura original e adicionando o timestamp de ingestão.

Fontes:

- Informações dos filmes
- Informações financeiras
- Métricas de engajamento
- Créditos e tags
- Avaliações dos usuários
- Cotação do dólar

### Silver

Camada de tratamento e padronização dos dados, incluindo:

- Padronização dos nomes das colunas
- Conversão e validação de tipos
- Tratamento de valores ausentes e inválidos
- Deduplicação
- Normalização de gêneros
- Separação de pessoas e empresas
- Conversão de valores financeiros de USD para BRL
- Tratamento da série temporal da cotação do dólar

### Gold

Camada analítica organizada em modelo dimensional, contendo:

- Dimensões de filmes, gêneros, pessoas, empresas e avaliações
- Bridges entre filmes e entidades multivaloradas
- Fato de performance dos filmes

A `fact_movies_performance` possui granularidade de um registro por filme.

## Analytics

Foram desenvolvidas consultas para responder:

1. Receita total dos filmes em BRL
2. Top 5 filmes por popularidade
3. Quantidade de filmes por gênero
4. Top 10 filmes por receita, com ranking
5. Ator com maior número de participações nos últimos 2 anos
6. Produtora com maior lucro nos últimos 5 anos

## Observação

Os dados e tabelas utilizados no processamento foram disponibilizados no ambiente Databricks da atividade. O notebook contém todo o processo de ingestão, transformação, modelagem e análise.

## Principais resultados

- Receita total em BRL: R$ 817.429.209.510,00
- Filme com maior popularidade: Blue Beetle
- Gênero com maior quantidade de filmes: Drama
- Maior receita: Avengers: Endgame
- Ator com mais participações nos últimos 2 anos: Kevin Hart (64 filmes)
- Produtora com maior lucro nos últimos 5 anos: Universal Pictures
