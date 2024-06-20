# Teste de Performance com JMeter - Plano de Teste para Youtube

Este repositório contém um arquivo XML que descreve um plano de teste de performance usando Apache JMeter para o site YouTube.

## Arquivo do Plano de Teste

O arquivo XML `jmeter_test_plan.xml` inclui as seguintes configurações principais:

- **TestPlan**: Define o plano de teste principal com variáveis definidas pelo usuário.
  - **host**: Define o host como `www.youtube.com`.
  - **protocol**: Usa HTTPS como protocolo de conexão.

- **ThreadGroup**: Configura o grupo de threads para simular usuários acessando o YouTube.
  - **Número de Threads**: 20 threads simultâneas.
  - **Tempo de Subida**: 60 segundos.
  - **Scheduler**: Ativado para iniciar os testes em um horário específico.

- **HTTPSamplerProxy**: Define a requisição HTTP GET para buscar informações no YouTube.
  - **Parâmetros**: Inclui um parâmetro `q` para realizar a busca.
  - **Configuração do Host e Protocolo**: Usa as variáveis definidas no TestPlan (`host` e `protocol`).

- **CSVDataSet**: Configuração para ler dados de um arquivo CSV.
  - **Arquivo CSV**: Define o caminho para o arquivo `termos01.csv` que contém os termos de busca.

- **ResultCollector**: Coleta e visualiza os resultados dos testes.
  - **Configuração de Salvamento**: Salva os resultados detalhados de cada requisição.

## Objetivo do Teste

Este plano de teste tem como objetivo simular o comportamento de múltiplos usuários realizando buscas no YouTube, utilizando dados de entrada de um arquivo CSV.

---

Para executar este plano de teste:

1. Configure o Apache JMeter com este arquivo XML.
2. Certifique-se de ter o arquivo CSV `termos01.csv` no caminho especificado.
3. Execute o teste para verificar o desempenho da aplicação sob carga simulada.

