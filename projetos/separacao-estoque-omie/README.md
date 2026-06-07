# Automação de Separação de Estoque no Omie

## Visão geral

Esta automação foi desenvolvida para integrar o **Omie** ao **Power Automate** e a uma planilha de controle armazenada no **SharePoint**, com o objetivo de automatizar o acompanhamento de pedidos que entram na etapa de **Separação de Estoque**.

O fluxo captura automaticamente pedidos de venda quando eles são movidos para a etapa **"Separar Estoque"** no Omie, consulta os dados necessários via API, identifica informações relevantes do pedido e registra tudo em uma planilha estruturada para acompanhamento operacional.

Além disso, a automação também monitora quando um pedido é movido para a etapa **"Entregue"**, atualizando automaticamente o status e a data de entrega no controle.

## Contexto do problema

Antes da automação, o processo de separação de estoque dependia de acompanhamento manual dos pedidos dentro do Omie e atualização manual de controles externos.

Esse cenário gerava alguns desafios, como:

* Necessidade de consultar pedidos manualmente no Omie;
* Risco de esquecer pedidos que entravam na etapa de separação;
* Retrabalho na atualização de planilhas;
* Falta de padronização no registro das informações;
* Maior chance de erro humano na identificação de modelo, cor, bateria e status;
* Dificuldade para acompanhar o andamento dos pedidos até a entrega.

Com o crescimento da operação e a existência de diferentes lojas/aplicações dentro do Omie, tornou-se necessário criar uma solução automatizada, padronizada e rastreável.

## Objetivo da automação

O objetivo da automação é transformar a movimentação de pedidos no Omie em um processo integrado e automático de controle de estoque.

A solução busca:

* Capturar pedidos em tempo real quando entram na etapa **Separar Estoque**;
* Consultar dados completos do pedido e do cliente via API do Omie;
* Identificar automaticamente informações como loja, cliente, modelo, cor e tipo de bateria;
* Registrar os dados em uma planilha no SharePoint;
* Atualizar automaticamente o status do pedido quando ele for entregue;
* Reduzir tarefas manuais e melhorar a visibilidade do processo operacional.

## Ferramentas e tecnologias utilizadas

* Microsoft Power Automate
* Omie
* API do Omie
* Webhooks HTTP
* SharePoint
* Excel Online
* Microsoft 365
* Conector HTTP Premium
* Expressões no Power Automate
* Condições, filtros, composição de dados e análise de JSON

## Como a automação funciona

A automação é baseada em webhooks configurados no Omie. Quando um pedido muda de etapa, o Omie envia automaticamente um evento para uma URL gerada pelo Power Automate.

A partir desse evento, o fluxo verifica se a etapa recebida corresponde ao processo esperado.

### Fluxo de Separação de Estoque

1. Um pedido é movido para a etapa **"Separar Estoque"** no Omie.
2. O webhook do Omie envia o evento para o Power Automate.
3. O Power Automate valida se a etapa recebida é realmente **"Separar Estoque"**.
4. O fluxo consulta a API do Omie para buscar os detalhes completos do pedido.
5. O fluxo consulta a API do Omie para buscar os dados do cliente.
6. A automação identifica a loja responsável pelo pedido.
7. O fluxo localiza o produto principal, utilizado como referência para modelo e cor.
8. A automação identifica se o pedido possui bateria e classifica o tipo encontrado.
9. Os dados tratados são registrados em uma tabela do Excel armazenada no SharePoint.
10. A equipe passa a ter uma linha de controle com as principais informações do pedido.

### Fluxo de Entrega

1. Um pedido é movido para a etapa **"Entregue"** no Omie.
2. O webhook envia o evento para o Power Automate.
3. O fluxo valida se a etapa recebida é **"Entregue"**.
4. A automação localiza o pedido correspondente na planilha de controle.
5. O status é atualizado automaticamente para **"Entregue"**.
6. A data de entrega é preenchida automaticamente com base no momento da execução.

## Etapas principais do fluxo

* Recebimento do evento via webhook HTTP;
* Validação da etapa do pedido;
* Consulta dos detalhes do pedido na API do Omie;
* Consulta dos dados do cliente;
* Tratamento do retorno em JSON;
* Mapeamento da loja;
* Identificação do produto principal;
* Extração automática de modelo e cor;
* Identificação do tipo de bateria;
* Registro dos dados em planilha no SharePoint;
* Atualização automática de status quando o pedido é entregue.

## Integrações utilizadas

### Omie

O Omie é o sistema de origem das informações. Ele envia os eventos de mudança de etapa dos pedidos e disponibiliza os dados por meio da API.

### Power Automate

O Power Automate é responsável por receber os webhooks, executar as regras de validação, consultar a API, tratar os dados e registrar as informações na base de controle.

### SharePoint

O SharePoint é utilizado como local de armazenamento da planilha de controle, permitindo que a equipe acompanhe os pedidos registrados pela automação.

### Excel Online

O Excel funciona como base operacional para consulta e acompanhamento dos pedidos, contendo informações como pedido, loja, cliente, modelo, cor, bateria, status e datas relevantes.

## Regras aplicadas na automação

A automação possui regras para identificar dados relevantes do pedido, como:

* Verificação da etapa do pedido antes de executar o fluxo;
* Mapeamento da loja com base na origem do pedido;
* Identificação do produto principal por padrão de nomenclatura;
* Extração do modelo a partir do código do produto;
* Extração da cor a partir do código do produto;
* Verificação da existência de bateria no pedido;
* Classificação da bateria como lítio, chumbo ou não aplicável;
* Atualização automática do status quando o pedido é entregue.

## Benefícios gerados

A automação trouxe ganhos importantes para o processo operacional, como:

* Redução de tarefas manuais;
* Maior velocidade no registro dos pedidos;
* Menor risco de erro na separação de estoque;
* Padronização das informações registradas;
* Melhor rastreabilidade dos pedidos;
* Atualização automática do status de entrega;
* Centralização das informações em uma base compartilhada;
* Mais clareza para a equipe acompanhar pedidos pendentes, em separação ou entregues.

## Cuidados com dados sensíveis

Para fins de portfólio, este projeto foi documentado sem expor informações sensíveis.

Foram removidos ou ocultados:

* Chaves de API;
* Tokens de autenticação;
* Segredos de integração;
* URLs privadas de webhook;
* Dados reais de clientes;
* Informações internas da empresa;
* Dados financeiros;
* Identificadores sensíveis dos sistemas utilizados.

A documentação pública tem como objetivo apresentar a lógica da solução, as tecnologias utilizadas e os benefícios do projeto, sem comprometer a segurança da operação.

## Possíveis melhorias futuras

Algumas melhorias que podem ser implementadas futuramente:

* Ativar notificações automáticas por e-mail para responsáveis pela separação;
* Adicionar alertas no Microsoft Teams;
* Criar logs de execução para auditoria e suporte;
* Registrar erros em uma lista do SharePoint;
* Criar painel no Power BI para acompanhar pedidos por status, loja e prazo;
* Expandir a automação para outras etapas do pedido, como faturamento ou envio;
* Melhorar o tratamento de falhas em chamadas de API;
* Criar uma estrutura mais escalável para novas lojas ou novas aplicações no Omie;
* Substituir parte do controle manual por status automatizados.

## Resumo profissional do projeto

Projeto de automação desenvolvido com **Power Automate**, integrando **Omie**, **API REST**, **webhooks**, **SharePoint** e **Excel Online** para automatizar o controle de pedidos em separação de estoque.

A solução captura pedidos em tempo real quando são movidos para a etapa de separação, consulta dados complementares via API, trata as informações recebidas e registra automaticamente os dados em uma base compartilhada. Também atualiza o status dos pedidos quando são entregues, reduzindo trabalho manual, melhorando a rastreabilidade e aumentando a eficiência operacional.
