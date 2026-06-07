# Automação de Avaliações de Desempenho com Forms, Power Automate, SharePoint e Excel

## Visão geral

Este projeto foi desenvolvido para automatizar o processo de coleta, organização e tratamento de avaliações de desempenho internas.

A solução utiliza **Microsoft Forms** para coleta das respostas, **Power Automate** para automação do processo, **SharePoint** para armazenamento dos arquivos e **Excel Online** para consolidação, cálculo e acompanhamento das avaliações.

O objetivo principal foi transformar um processo que poderia depender de controles manuais em uma estrutura mais organizada, padronizada e rastreável.

## Contexto do problema

A empresa precisava aplicar avaliações de desempenho para diferentes áreas e equipes, utilizando formulários com perguntas específicas para cada grupo.

Sem uma automação estruturada, esse tipo de processo poderia gerar dificuldades como:

* Respostas espalhadas em diferentes locais;
* Retrabalho para consolidar informações;
* Dificuldade para organizar avaliações por área;
* Risco de erro no cálculo de notas;
* Falta de padronização no armazenamento dos dados;
* Maior tempo para transformar respostas em informações úteis;
* Dificuldade para acompanhar avaliações por colaborador e avaliador.

## Minha atuação no projeto

Neste projeto, fui responsável pela criação e estruturação técnica da solução.

Minhas principais responsabilidades foram:

* Criar os formulários no Microsoft Forms;
* Estruturar o fluxo de recebimento das respostas;
* Criar a organização dos arquivos no SharePoint;
* Configurar a automação para direcionar os dados corretamente;
* Estruturar as planilhas de controle no Excel;
* Organizar os dados recebidos dos formulários;
* Apoiar a transformação das respostas em notas e informações consolidadas;
* Criar uma estrutura que permitisse calcular pontuações e bônus finais.

Os critérios das perguntas e os parâmetros de avaliação foram definidos pela área responsável pelo processo de avaliação. Minha atuação foi focada na construção da solução técnica e na automação do fluxo de dados.

## Objetivo da automação

A automação tem como objetivo centralizar e organizar as respostas das avaliações de desempenho, separando os dados por tipo de formulário e área avaliada.

A solução permite:

* Coletar respostas via Microsoft Forms;
* Armazenar automaticamente as respostas em planilhas no SharePoint;
* Separar os dados conforme o tipo de avaliação;
* Padronizar o formato das respostas;
* Gerar campos estruturados para análise;
* Calcular notas por critério;
* Consolidar nota total;
* Apoiar o cálculo de bônus com base nas avaliações;
* Facilitar a consulta e acompanhamento dos resultados.

## Ferramentas e tecnologias utilizadas

* Microsoft Forms
* Microsoft Power Automate
* SharePoint
* Excel Online
* Microsoft 365
* Tabelas estruturadas no Excel
* Fórmulas e tratamento de dados
* Automação de respostas de formulários
* Organização de arquivos em ambiente compartilhado

## Estrutura da solução

A solução foi organizada com três formulários principais, cada um direcionado a grupos específicos da empresa.

As respostas são armazenadas em três planilhas separadas no SharePoint:

1. **Avaliação de Desempenho - Financeiro, Comunicação, Corporativo, Operação e Tecnologia**
2. **Avaliação de Desempenho - Oficina**
3. **Avaliação de Desempenho - Venda e Confiabilidade**

Cada planilha contém os registros recebidos dos formulários e campos estruturados para apoiar o cálculo das notas e do bônus final.

## Como a automação funciona

1. O avaliador acessa o formulário correspondente à área ou equipe avaliada.
2. O avaliador preenche as respostas no Microsoft Forms.
3. As respostas são enviadas automaticamente para a base vinculada ao formulário.
4. O Power Automate organiza o fluxo de recebimento das informações.
5. Os dados são armazenados em arquivos Excel no SharePoint.
6. As respostas são estruturadas por avaliador, colaborador, data e critérios avaliados.
7. As respostas como **Sim**, **Às vezes** e **Não** são utilizadas para compor notas.
8. A planilha consolida os campos de nota individual por pergunta.
9. O sistema calcula uma nota total para cada colaborador.
10. A partir da nota final, é possível apoiar o cálculo de bônus individual.

## Tipos de dados registrados

As planilhas armazenam informações como:

* ID da resposta;
* Data e hora de início;
* Data e hora de conclusão;
* E-mail do avaliador;
* Nome do avaliador;
* Nome do colaborador avaliado;
* Respostas por critério;
* Observações textuais;
* Notas por pergunta;
* Nota total;
* Bônus base;
* Bônus final.

## Critérios avaliados

Os critérios de avaliação foram definidos pela área responsável pelo processo interno de desempenho.

A automação foi construída para receber, organizar e tratar esses critérios dentro da solução. Entre os temas avaliados estão:

* Comprometimento e presença;
* Convívio e integração com a equipe;
* Comunicação;
* Precisão em dados financeiros e comerciais;
* Zelo pelo local, equipamentos e uniforme;
* Qualidade e produtividade;
* Cumprimento de processos e procedimentos;
* Interesse em evolução profissional;
* Ética e lealdade;
* Conhecimento da cultura, produtos e regras da empresa;
* Observações gerais do avaliador.

Para áreas operacionais, como oficina, também existem critérios específicos ligados à execução de tarefas, processos, POPs, checklists e qualidade do serviço realizado.

## Tratamento dos dados

A solução transforma as respostas dos formulários em uma base estruturada para análise.

As respostas são organizadas em campos como:

```text
AVALIADOR
FUNCIONARIO
DATA
NOTA_1
NOTA_2
NOTA_3
NOTA_TOTAL
BONUS_BASE
BONUS_FINAL
```

Essa estrutura permite que a empresa consulte os resultados de forma mais clara e acompanhe a avaliação de cada colaborador com base nas respostas recebidas.

## Benefícios gerados

A automação trouxe benefícios como:

* Redução de trabalho manual;
* Maior organização das avaliações;
* Centralização dos dados no SharePoint;
* Padronização das respostas recebidas;
* Separação das avaliações por área;
* Menor risco de erro na consolidação;
* Facilidade para calcular notas e bônus;
* Melhor rastreabilidade das respostas;
* Mais agilidade no acompanhamento do desempenho dos colaboradores;
* Base estruturada para futuras análises e dashboards.

## Cuidados com dados sensíveis

Por se tratar de um projeto relacionado a avaliações internas, dados reais de colaboradores, avaliadores, comentários e informações internas não devem ser expostos publicamente.

Para apresentação em portfólio, os seguintes dados devem ser ocultados ou substituídos por exemplos fictícios:

* Nomes de colaboradores;
* E-mails corporativos;
* Comentários de avaliação;
* Notas individuais reais;
* Valores de bônus;
* Links internos do SharePoint;
* Identificadores de formulários;
* Informações confidenciais da empresa.

O objetivo da documentação pública é apresentar a arquitetura da solução, as ferramentas utilizadas e os ganhos do processo, sem expor informações sensíveis.

## Possíveis melhorias futuras

Algumas melhorias que podem ser implementadas futuramente:

* Criar dashboard no Power BI para análise dos resultados;
* Gerar relatórios por área, avaliador e colaborador;
* Automatizar envio de resumo para gestores;
* Criar alertas para avaliações pendentes;
* Adicionar controle de ciclo de avaliação;
* Criar histórico evolutivo por colaborador;
* Implementar validações adicionais nas respostas;
* Criar uma lista no SharePoint para centralizar metadados;
* Gerar relatórios individuais em PDF;
* Automatizar comunicação dos resultados para os responsáveis.

## Resumo profissional do projeto

Projeto de automação desenvolvido com **Microsoft Forms**, **Power Automate**, **SharePoint** e **Excel Online** para estruturar o processo de avaliações de desempenho internas.

A solução coleta respostas de diferentes formulários, organiza os dados em planilhas separadas por área, estrutura as informações por avaliador e colaborador, calcula notas e apoia o controle de bônus. O projeto reduziu retrabalho manual, melhorou a organização dos dados e trouxe mais rastreabilidade para o processo de avaliação.
