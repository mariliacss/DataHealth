# Etapa Final

## Projeto Saúde Mental

## Equipe Data Health

* Marília Correa da Silva Santos
* Gustavo Praciano Barros

## Slides da Apresentação da Etapa Final
[Slides](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/slides/Apresenta%C3%A7%C3%A3o%20final%20.pdf)

## Resumo do Projeto

Projeto com a intenção de correlacionar os casos de suicídio pelo mundo com as doenças mentais mais comuns, como depressão, ansiedade, bipolaridade, verificando sua influência nos países com maiores taxas de suicídio.

## Motivação e Contexto 

Atualmente, as notícias sobre saúde mental e sua importância estão cada vez mais presentes em nosso cotidiano. Estmos sempre sendo bombardeados sobre saúde mental no trabalho, na faculdade ou colégio, em casa, etc. E com o isolamento social na pandemia, a reflexão sobre esse assunto acabou se tornando inevitável devido ao logo tempo sozinho sem poder seguir uma rotina e ver as pessoas que gostamos. Além disso, também é comum vermos notícias sobre suicídio associada a falta de saúde mental, principalmente depressão. Nesse contexto, ficamos interessados em pesquisar a respeito dessa relação entre casos de suicídio e as desordens mentais mais comuns no mundo.

## Detalhamento do Projeto 

A princípio, antes de efetivamente realizar a primeira conversão dos dados, pensamos em fazer uma relação entre as taxas de sucícidio e de doenças de forma mais aberta, para podermos ter mais mobilidade de escolha no momento de realizar as consultas. Isso acabou sendo uma vantegem pois encontramos várias análises diferentes nessa relação.

A partir do momento no qual escolhemos as bases de dados e baixmos os arquivos em CSV necessários, o primiero passo foi ajustar manualmente o nome das colunas que iríamos usar para facilitar no momento da leitura em SQL e também foi alterado o nome de algumas regiões e países que continham vírgulas as quais atrapalhavam a leitura dos arquvos. Após isso, usamos majioritariamente SQL para ler e manipular os dados. Escolhemos as colunas de cada arquivo que seriam mais interessantes para nossas análises e montamos as tabelas descritas na parte de Modelos Lógicos Finais.

Após olhar os dados coletados nas tabelas, consegimos refletir melhor para espercificar os direcionamentos para as consultas. Assim decidimos pelos seguintes questinomentos:
* Top 3 doenças que mais aparecem nos países com maior e menor taxa de suicídio.
* Qual a idade mais afetada pelas doenças mais prevalentes nos paises com maior taxa de suicídio.
* Países que aumentaram/diminuíram as taxas.
* Países que aumentaram/diminuíram as taxas médias.

Com esses tópicos pensamos que seria possível começar a traçar algum tipo de relação, mesmo que bem inicialmente, mas que não são tão comuns. Todas as queries para os tópicos anteriores estão apresentadas Binder: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/mariliacss/DataHealth/main).

## Evolução do Projeto

Durante a execução do projeto houveram várias mudanças importantes. Primeiramente, começamos com um tema relacionando suicídio com o uso de internet e rede sociais. Porém, durante a presquisa para dar continuidade na segunda estapa, não encontramos os dados que queríamos para da forma ao nosso modelo conceitual e fazer as análises que pensamos de início. Dessa forma, e com o acumulo de outras atividades da graduação, ficamos perdidos em como prosseguir com o projeto e acabamos perdendo muito tempo. Além disso, ficamos defasados em integrantes pois um membro trancou a matéria.

A partir desses problemas, tivemos uma reunião para conversar como iríamos resolver. Assim, mudamos o direcionamento e, aproveitando as ótimas bases de dados que encontramos sobre suicídio e saúde mental, resolvemos verificar essa relação. Apesar do tempo curto que tivemos, por ter que recomeçar do zero praticamente, conseguimos filtrar os dados e fazer análises muito interessentes para as etapas 3 e 4.

Ainda assim tivemos alguns problemas: na filtragem de dados para saber quais eram absolutos e relativos para comparação; organizar os dados em tabelas para o modelo relacional, pois os dados brutos estavam "em colunas" e passamos uma grande parte de uma aula com ajuda do professor para mudar de uma forma mais fácil de realizar as queries; e o Binder não ajudou na execução de algumas queries que demandavam mais processamento.

Por fim, para alguns dados conseguidos na forma tabular não passar para modelo de grafos para conseguirmos fazer análises mais profundos nesse modelo. Mas ficamos satisfeitos com a quantidade e qualidade das análises que fizemos e, se desse mais tempo, teríamos muito mais para procurar.

## Resultados e Discussão

* Top 3 doenças que mais aparecem nos países com maior e menor taxa de suicídio.

![maiorestaxas](../EtapaFinal/assets/maiores.png)

![maiorestaxas](../EtapaFinal/assets/maiores.png)

![maiorestaxas](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/assets/maiores%20taxas.JPG)

![maiorestaxas](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/assets/menores%20taxas.JPG)

A partir dos gráficos conseguimos perceber que nos paises de maiores taxas de suicídio a doença mais prevalente é Depressão, já nos de menores taxas é Ansiedade. Aqui podemos perceber que talvez a depressão possa ser a principal doença associada ao suicídio.

* Qual a idade mais afetada pelas doenças mais prevalentes nos paises com maior taxa de suicídio.

![maiorestaxas](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/assets/idades.JPG)

* Países que aumentaram/diminuíram as taxas.
* Países que aumentaram/diminuíram as taxas médias.

![maiorestaxas](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/assets/aumentam.JPG)

![maiorestaxas](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/assets/diminuiram.JPG)

## Conclusões

Apesar de estarmos fazendo análises mais superficiais e obviamente não sermos nenhum tipo de profissional da área conseguimos pensar em algumas coisas que com mais análises e mais criteriosas.

Primeiramente, nos países com maior taxa de suicidio, observou-se uma maior prevalência de depressão, como já foi dito, e de ansiedade nos países com menor taxa. Além disso, de modo geral o suicídio diminui no mundo, em média os avanços mostraram se mais expressivos depois dos anos 2000, mas as taxas crescimento de doenças mentais, mostraram se ter mais crescimento durante os anos.

Os países com maior desenvolvimento (SDI e High Income), mostraram se ter mais ocorrência de suicídios na faixa etária de 15 a 49 anos. De modo geral, a maioria das doenças e suicídios mostraram se mais presentes com pessoas acima de 70 anos.

![maiorestaxas](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/assets/highincome.JPG)

Por fim, verificamos que com alta diminuição de suicidio de um país, não podemos implicar que o contexto do país é positivo pois observamos que a Groelândia foi um dos países que mais diminuíram as taxas (como podemos ver nos resultados da querie de aumento e diminuição), porém ainda continua como um das maiores taxas de suicídio (como podemos ver nos resultados da querie de doença prevalente nos países de maiores taxas).

## Modelo Conceitual Final

![modelo](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/assets/Modelo%20Conceitual%20final.png)

## Modelos Lógicos Finais
* Relacional:
```
MentalHealthDisorders(country, year, disease, share)
DisordersByAge(country, year, disease, age, share)
ShareDeathsSuicide(pais, codigo, ano, porcentagemDeMortes)
RatesDeathsSuicide(pais, codigo, ano, RatesDeaths, RatesDeathsMale, RatesDeathsFemale)
RatesDetailedDeathsSuicide(pais, codigo, ano, RatesDeaths, RatesDeaths514, RatesDeaths1549, RatesDeaths5069, RatesDeaths70)
```
* Grafos:
```
Países com taxa de crescimento próxima;
Países com a mesma doença prevalente;
```

## Conjunto de queries para todos os modelos

### SQL

As queries em SQL estão disponíveis no mesmo notebook ([link](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/notebooks/projetoBDFinal.ipynb)) em que estão as tabelas e a conversão de dados. No notebook está detalhado em qual parte começa as queries (os links do sumário só funcionam no Binder)

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/mariliacss/DataHealth/main)

### Neo4j

**Grafo ligando paises com a taxa de crescimento próxima**
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
![grafo](https://github.com/mariliacss/DataHealth/blob/main/stage04/assets/grafo2.png)

[link para o arquivo .cys](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/src/grafroSuicidio.cys)

**Grafo ligando paises com a mesma doença prevalente**
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
![grafo](https://github.com/mariliacss/DataHealth/blob/main/stage04/assets/grafo1.png)

[link para o arquivo .cys](https://github.com/mariliacss/DataHealth/blob/main/EtapaFinal/src/grafoDoencaPrevalente.cys)

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
