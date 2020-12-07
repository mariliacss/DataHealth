# Etapa 03 - Análises com o Primeiro Modelo Lógico
## Primeiro Modelo Conceitual

![modelo conceitual](../stage03/assets/ModeloConceitual.png)

## Primeiros Modelos Lógicos
Coloque aqui os primeiros modelos lógicos dos bancos de dados relacionados aos modelos conceituais. Para o modelo relacional, sugere-se o formato a seguir. Para outros modelos lógicos o formato é livre, pode ser adotado aqueles apresentados em sala.

Exemplo de modelo lógico relacional
```
MentalHealthIssues(pais, ano, depressao, ansiedade, bipolaridade, alimentar, esquizofrenia)
ShareDeathsSuicide(pais, codigo, ano, porcentagemDeMortes)
RatesDeathsSuicide(pais, codigo, ano, RatesDeaths, RatesDeathsMale, RatesDeathsFemale)
RatesDetailedDeathsSuicide(pais, codigo, ano, RatesDeaths, RatesDeaths514, RatesDeaths1549, RatesDeaths5069, RatesDeaths70)
```
## Primeiro programa de extração e conversão de dados
Coloque um link para o arquivo do notebook que executa a extração e conversão de dados. Ele estará dentro da pasta notebook. Se por alguma razão o código não for executável no Jupyter, coloque na pasta src. Se a extração e conversão envolverem queries executadas atraves de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.

## Primeiro conjunto de queries
Coloque um link para o arquivo do notebook que executa o conjunto de queries. Ele estará dentro da pasta notebook. Se por alguma razão o código não for executável no Jupyter, coloque na pasta src. Se as queries forem executadas atraves de uma interface de um SGBD não executável no Jupyter, como o Cypher, apresente na forma de markdown.

## Bases de Dados

Título | Link | Descrição
------------ | ------------- | -------------
Suicide - Our World in Data | https://ourworldindata.org/suicide | Dados e tabelas gerais sobre suicídicio.
Mental Health - Our World in Data | https://ourworldindata.org/mental-health | Dados e tabelas gerais sobre saúde mental.

## Arquivos de Dados
Elencar os arquivos usados no projeto que estão disponíveis no Github do projeto.

Nome | Link | Descrição
------------ | ------------- | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

Os arquivos devem ser colocados na pasta data, em subpasta conforme seu papel (externo, interim, processado, raw). A diferença entre externo e raw é que o raw é em formato não adaptado para uso. A pasta raw é opcional, pois pode ser substituída pelo link para a base original da seção anterior. Coloque arquivos relacionais (usualmente CSV), XML ou JSON que não estejam disponíveis online e sejam acessados pelo notebook.
