# Etapa 04 - Análises com o Segundo Modelo Lógico
## Slides da Apresentação da Etapa
[Slides](https://github.com/mariliacss/DataHealth/blob/main/stage04/slides/stage04.pdf)

## Modelo Conceitual Atualizado
![modelo conceitual](https://github.com/mariliacss/DataHealth/blob/main/stage04/assets/Modelo%20Conceitual%20final.png)

## Modelos Lógicos Atualizados

```
MentalHealthDisorders(country, year, disease, share)
DisordersByAge(country, year, disease, age, share)
ShareDeathsSuicide(pais, codigo, ano, porcentagemDeMortes)
RatesDeathsSuicide(pais, codigo, ano, RatesDeaths, RatesDeathsMale, RatesDeathsFemale)
RatesDetailedDeathsSuicide(pais, codigo, ano, RatesDeaths, RatesDeaths514, RatesDeaths1549, RatesDeaths5069, RatesDeaths70)
```

## Programa de extração e conversão de dados atualizado
[Notebook](link)

## Conjunto de queries de dois modelos
[Notebook](link)

### Neo4j
Grafo ligando paises com a taxa de crescimento próxima
```
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/processed/mediaPorcentCresDecresSuicidio.csv' AS line
CREATE (:Suicide {name: line.PAIS, media: line.MÉDIA})

CREATE INDEX ON :Suicide(name)

MATCH (s1:Suicide)
MATCH (s2:Suicide)
where s2.media-s1.media<=0.1 and s2.media-s1.media>0
MERGE (s1)-[m:Maior]->(s2)
ON CREATE SET m.weight=1
ON MATCH SET m.weight=m.weight+1

match (s1:Suicide)-[:Maior]->(s2:Suicide)
RETURN s1.name as source, s2.name as target
```
Detectando a comunidade
```
CALL gds.graph.create(
  'communityGraph2',
  'Suicide',
  {
    Maior: {
      orientation: 'UNDIRECTED'
    }
  }
)

CALL gds.louvain.stream('communityGraph2')
YIELD nodeId, communityId
RETURN gds.util.asNode(nodeId).name AS name, communityId
ORDER BY communityId ASC

CALL gds.louvain.stream('communityGraph2')
YIELD nodeId, communityId
MATCH (p:Suicide {name: gds.util.asNode(nodeId).name})
SET p.community = communityId

CALL gds.louvain.stream('communityGraph2')
YIELD nodeId, communityId
RETURN gds.util.asNode(nodeId).name AS name, communityId
```
Grafo ligando paises com a mesma doença prevalente
```
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/processed/doencaMaisPrevalente.csv' AS line
CREATE (:Disease {name: line.COUNTRY, doenca: line.DISEASE, media: line.MEDIATAXA})

CREATE INDEX ON :Disease(name)

MATCH (d1:Disease)
MATCH (d2:Disease)
where d1.doenca = d2.doenca and d1.name <> d2.name
MERGE (d1)-[p:Prevalente {doenca: d1.doenca}]->(d2)

match (d1:Disease)-[:Prevalente]->(d2:Disease)
RETURN d1.name as source, d2.name as target
```
Detectando a comunidade
```
CALL gds.graph.create(
  'communityGraph',
  'Disease',
  {
    Prevalente: {
      orientation: 'UNDIRECTED'
    }
  }
)

CALL gds.louvain.stream('communityGraph')
YIELD nodeId, communityId
RETURN gds.util.asNode(nodeId).name AS name, communityId
ORDER BY communityId ASC

CALL gds.louvain.stream('communityGraph')
YIELD nodeId, communityId
MATCH (p:Disease {name: gds.util.asNode(nodeId).name})
SET p.community = communityId

CALL gds.louvain.stream('communityGraph')
YIELD nodeId, communityId
RETURN gds.util.asNode(nodeId).name AS name, communityId
```
## Bases de Dados

Título | Link | Descrição
------------ | ------------- | -------------
Suicide - Our World in Data | https://ourworldindata.org/suicide | Dados e tabelas gerais sobre suicídicio.
Mental Health - Our World in Data | https://ourworldindata.org/mental-health | Dados e tabelas gerais sobre saúde mental.

## Arquivos de Dados

Nome | Link | Descrição 
------------ | ------------- | -------------
mental-health-issues.csv | [link](https://github.com/mariliacss/DataHealth/blob/main/stage03/data/external/mental-health-issues.csv) | número de pessoas com a doença indicada
prevalence-of-anxiety-disorders-by-age.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/prevalence-of-anxiety-disorders-by-age.csv) | porcentagem de pessoas com ansiedade por idade
prevalence-of-bipolar-disorder-by-age.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/prevalence-of-bipolar-disorder-by-age.csv) | porcentagem de pessoas com transtorno bipolar por idade
prevalence-of-depression-by-age.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/prevalence-of-depression-by-age.csv) | porcentagem de pessoas com depressão por idade
share-deaths-suicide.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/share-deaths-suicide.csv) | porcentagem de suicídio por pas
share-of-population-with-schizophrenia.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/share-of-population-with-schizophrenia.csv) | porcentagem de pessoas com esquizofrenia país
share-with-an-eating-disorder.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/share-with-an-eating-disorder.csv) | porcentagem de pessoas com trasntorno alimentar por país
share-with-anxiety-disorders.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/share-with-anxiety-disorders.csv) | porcentagem de pessoas com ansiedade por país
share-with-bipolar-disorder.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/share-with-bipolar-disorder.csv) | porcentagem de pessoas com transtorno bipolar por país
share-with-depression.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/share-with-depression.csv) | porcentagem de pessoas com depressão por país
suicide-death-rates-by-sex.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/suicide-death-rates-by-sex.csv) | taxas de suicídio por sexo
suicide-rates-by-age-detailed.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/external/suicide-rates-by-age-detailed.csv) | taxas de suicídio por país
MentalHealthDisorders.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage03/data/processed/MentalHealthDisorders.csv) | porcentagem de doenças mentais por país
doencaMaisPrevalente.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage04/data/processed/doencaMaisPrevalente.csv) | média da porcentagem da doença mais provalente por país
grafoAnsiedadeDepressao.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage04/data/processed/grafoAnsiedadeDepressao.csv) | grafo ligando os paises que tem a mesma doença prevalente
grafoAnsiedadeDepressaoComunidade.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage04/data/processed/grafoAnsiedadeDepressaoComunidade.csv) | detecção da comuidade do grafoAnsiedadeDepressao.csv
mediaPorcentCresDecresSuicidio.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage04/data/processed/mediaPorcentCresDecresSuicidio.csv) | média da porcentagem de crescimento ou decrescimento de suicídio por país por país
primeiroGrafo.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage04/data/processed/primeiroGrafo.csv) | grafo ligando os países com taxa de crescimento semelhantes
primeiroGrafoComunidade.csv | [link](https://raw.githubusercontent.com/mariliacss/DataHealth/main/stage04/data/processed/primeiroGrafoComunidade.csv) | detecção de comunidade do primeiroGrafo.csv
