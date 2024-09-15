# dre-test

# Author: Alexander Bento Melo
# Data: 15/09/2024

# Projeto de Orquestração Airflow

## Visão Geral
Este projeto configura um ambiente Airflow usando Docker Compose. 
A arquitetura inclui componentes do Airflow, como o webserver, scheduler, workers, triggerer e a ferramenta de monitoramento Flower.
O ambiente utiliza o PostgreSQL como banco de dados backend e o Redis como broker de mensagens.

## Componentes

- **PostgreSQL**: Armazena metadados e resultados das tarefas dos jobs do Airflow.
- **Redis**: Usado como broker de mensagens para distribuir tarefas entre os workers do Airflow.
- **Airflow Webserver**: Interface para visualizar DAGs, tarefas e fluxos de trabalho.
- **Airflow Scheduler**: Responsável por agendar os DAGs e suas tarefas.
- **Airflow Worker**: Executa as tarefas definidas nos DAGs.
- **Airflow Triggerer**: Responsável por executar triggers baseados em eventos das tarefas.
- **Flower**: Ferramenta de monitoramento para acompanhar o desempenho dos workers do Celery.

## Instruções de Configuração
1. Clone o repositório:
   ```bash
   git clone https://github.com/alexbentomelo/dre-3-test

2. Navegue até o diretório:

cd airflow-docker-setup

3. Inicie o ambiente com Docker Compose:

docker-compose up -d
Acesse a interface do Airflow visitando http://localhost:8080

## Credenciais Padrão
Usuário: airflow
Senha: airflow

## Monitoramento

Você pode monitorar os workers do Celery utilizando o Flower em http://localhost:5555.

## Problemas Comuns e Soluções

Erros de conexão com PostgreSQL: Certifique-se de que os valores de POSTGRES_USER, POSTGRES_PASSWORD e POSTGRES_DB correspondem entre os serviços.

Problemas de conexão com Redis: Verifique se o broker Redis está em execução e saudável utilizando o comando docker logs <nome-do-container-redis>.