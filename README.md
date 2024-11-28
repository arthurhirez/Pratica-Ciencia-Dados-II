![Inteli.Gente Banner](images/Inteli.Gente.Banner.png)

# SCC0957 - Prática em Ciência de Dados II

Este repositório contém as informações coletadas ao longo do desenvolvimento do projeto da disciplina. O tópico motivador foi explorar os níveis de Maturidade das cidades, definidos na plataforma Inteli.gente (iniciativa do Ministério da Ciência, Tecnologia e Inovação - MCTI) e foram feitas análises sob diferentes prespectivas. A **aquisição dos dados é feita através de Web-scrapping**, descrita em detalhes na Seção 1 ([![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/1.%20Scrapper)). Na mesma seção **é proposta uma técnica que alia Visualização exploratória e Seleção de Features**, aferindo o desempenho da metodologia para a tarefa de regressão. (THIAGO: É ISSO MSM??). <-------------

Buscando agregar valor à análise, são integrados dados de escolaridade e renda dos trabalhadores, obtidos por meio da Relação Anual de Informações Sociais (RAIS), vinculada ao Ministério do Trabalho e Emprego (MTE), na Seção 2 ([![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA)). Essa análise é conduzida sob uma perspectiva geográfica, considerando diferentes níveis de granularidade. Além disso, aprofunda-se na relação entre geografia, nível de escolaridade e setor industrial. Conclui-se que a mudança na granularidade da análise — País, Região ou Estado — impacta significativamente na relação entre o nivel de maturidade econômico e os dados de escolaridade e setor industrial, evidenciando a complexidade e a heterogeneidade dos municípios brasileiros. Nesse contexto, adotar as divisões estabelecidas pelo **IBGE** revela-se uma abordagem mais eficiente, uma vez que a criação de agrupamentos significativos baseados exclusivamente em escolaridade e setor industrial apresenta desafios, devido às relações espaciais e à ampla diversidade entre os municípios.

A última estratégia adota é focada na dinâmica de Influência/Relevância regional dos municípios. A princípio, a estratégia seria utilizar dados de Investimentos Federais (Ministério da Fazenda - MF) e estudar sua correlação com os níveis de Maturidade ([![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis)). Porém, é encontrado o desafio de como distribuir os efeitos dos investimentos nos municípios no entorno. Para lidar com esse desafio, são empregadas ferramentas de GIS (Geographic Information System) em uma tentativa de quantificar a Influência regional dos municípios, utilizando dados de Investimentos Federais e  PIB *per capita*.


## Escolha do Tema e Conjunto de Dados

O objetivo do trabalho (???????????????) é estudar como diferentes aspectos (indicadores econômicos/sociais/culturais/geográficos, etc) influenciam no nível de Maturidade dos municípios brasileiros, conforme definido na plataforma Inteli.gente (https://inteligente.mcti.gov.br/). Existem quatro níveis de Maturidade, como ilustrado abaixo para São Carlos, porém é tomada a decisão de focar na Maturidade Econômica (dada a escolha de dados desse domínio, como os relativos à emprego e investimentos públicos). Porém, ao longo do projeto, são feitas análises considerando os outros domínios, para testar a robustez das soluções.

<p align="center">
  <img src="images/inteli.gente.png" height="250" title="Exemplo da Cidade de São Carlos na Plataforma Inteli.Gente">
  <br>
  <a>Fonte: </a>
  <a href="https://inteligente.mcti.gov.br/municipios/sao-carlos-sp">https://inteligente.mcti.gov.br/municipios/sao-carlos-sp<a/>
</p>

Para enriquecer o projeto, são utilizados dados de bases públicas, reunindo informações geográficas (IBGE), relacionadas com renda e escolaridade dos trabalhadores (RAIS-MTE) e a nível de municípios (Investimentos Federais - MF e PIB per capita - IBGE), com detalhes em suas respectivas seções.

## Principais resultados

### Seção 1 - Scrapping, Visualização e Seleção de Features [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/1.%20Scrapper)
Scrap (?) + Proposta metodologia Visualização /Seleção -> resultados regressão

### Seção 2 - Análise Exploratória (EDA) [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA)
- A investigação do nível de maturidade econômico por meio de análises e modelos no nível estadual pode apresentar resultados consistentes e satisfatórios.
  - Para análises exploratórias, utilizar uma granularidade menor, como as regiões intermediárias ou imediatas, pode ser interessante. Contudo, o desenvolvimento de modelos nesse nível enfrentaria limitações relacionadas à quantidade e qualidade dos dados disponíveis.
- Seguir as divisões estabelecidas pelo **IBGE** revela-se uma abordagem mais eficiente, pois criar agrupamentos utilizando medidas baseadas em distâncias com dados de escolaridade e setor industrial é um desafio, principalmente devido às complexas relações espaciais e à ampla diversidade entre os municípios.
- Apesar das distribuições dos níveis econômicos serem semelhantes entre diferentes escalas — Regiões, Estados, Regiões Imediatas e Regiões Intermediárias —, as relações entre as variáveis apresentam diferenças significativas:
  - Nas regiões Centro-Oeste e Sul, embora as distribuições relativas sejam parecidas, as relações com as variáveis do setor industrial são completamente distintas.
  - O mesmo ocorre entre os estados de Pernambuco (PE) e Rio Grande do Norte (RN).
- O desbalanceamento dos dados e a presença de muitos "outliers" também são desafios. No entanto, os outliers, nem sempre podem ser considerados como ruídos, pois o Brasil é composto por um grande número de municípios, incluindo alguns com altas populações e concentração de capital.
- Normalizar os dados de escolaridade e setor industrial pelos respectivos atributos Total, que representam a soma dos demais atributos, ou por outras abordagens como divisão pela popualçao total, pode ser uma abordagem mais adequada do que outros métodos de normalização devido à presença de outliers.
  - Técnicas como MinMax são influenciados por valores discrepantes, de modo a tenderem a aproximar excessivamente os dados entre os extremos.

### Seção 3 - Análise Espacial (Spatial Analysis) [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis)
O objetivo inicial seria modelar a distribuição regional de investimentos Federais, partindo da suposição que verbas aplicadas em uma cidade beneficiam seu entorno e da necessidade, dado que não são todas as cidades que recebem investimentos. Porém, no desenvolvimento do projeto foi considerado que os resultados não seriam representativos, o que levou à mudança de objetivo. A partir desse ponto, o estudo foi focado em estudar um método de como definir a influência regional das cidades, utilizando técnicas de GIS.

TODO: concluir alguma coisa

### Conclusão do projeto (acho que se fizer legal em cada seção não precisa repetir de novo)


## Detalhamento das Análises

### Seção 1 - Scrapping, Visualização e Seleção de Features  [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/1.%20Scrapper)

1. Web-Scraping na Plataforma Inteli.Gente (15/08/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/1.%20Scrapper)
2. Análise Inicial dos Dados do Inteli.Gente (12/09/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/1.%20(12-09-2024)%20An%C3%A1lise%20dos%20Dados%20do%20Scrapper.md)
3. Desenvolvimento do Gráfico Multi Scatter-plots 1D (19/09/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/2.%20(19-09-2024)%20Desenvolvimento%20do%20Gr%C3%A1fico%20Multi%20Scatter-plots%201-D.md)
4. Reordenação das Colunas no Gráfico Multi Scatter-plot (03/10/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/3.%20(03-10-2024)%20Reordena%C3%A7%C3%A3o%20das%20Colunas%20no%20Multi%20Scatter-plot.md)
5. Identificação de Atributos Aleatórios (10/10/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/4.%20(10-10-2024)%20Identifica%C3%A7%C3%A3o%20de%20Atributos%20Aleat%C3%B3rios.md)
6. Filtragem de Atributos Mal Comportados (07/11/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/5.%20(07-11-2024)%20Filtragem%20de%20Atributos%20Mal%20Comportados.md)
7. Análise Conjunta dos Atributos Bem Comportados e Mal Comportados (21/11/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/6.%20(21-11-2024)%20An%C3%A1lise%20Conjunta%20dos%20Atributos%20Bem%20Comportados%20e%20Mal%20Comportados.md)

---

### Seção 2 - Análise Exploratória (EDA) [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA)
1. Análise do Comportamento do Nível Econômico sob uma Perspectiva Geográfica: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/0.%20EDA%20Nivel%20Economico)
2. Análises Exploratórias do Comportamento do Nível Econômico e Setores Industriais: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/1.%20EDA/1.%20EDA%20Setor%20Industrial)
3. Análises Exploratórias do Comportamento do Nível Econômico e Educacional: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/2.%20EDA%20Pessoas%20em%20Cada%20Nivel%20Educacional)
4. Clusterização e Análises dos dados Educacional e Setores Industriais: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/3.%20Clusters)

---

### Seção 3 - Análise Espacial (Spatial Analysis) [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis)
1. Análise e pré-processamento dos dados de Investimentos Federais/Maturidade: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.1%20An%C3%A1lise%20Explorat%C3%B3ria) 
2. Cobertura geográfica e Representatividade da amostra: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.2%20Avalia%C3%A7%C3%A3o%20Amostragem) 
3.  Exploração biblioteca GIS - PySAL : [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.3%20Estudo%20biblioteca%20Pysal)
4. Dinâmica de Influência/Relevância regional [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.4%20An%C3%A1lise%20Espacial) 
5. Estatísticas Espaciais e Níveis de Maturidade: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.5%20Rela%C3%A7%C3%A3o%20com%20n%C3%ADveis%20de%20Maturidade)


## Estudos futuros (????????) acho que nme precsa




## Links Rápidos para Acesso dos Notebooks pelo Google Colab:

### Seção 1 - Scrapping, Visualização e Seleção de Features
1. Script para Download dos Dados: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Scrapper%20v2%20(PCDII).ipynb)
2. Análise Inicial dos Dados do Inteli.Gente: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/Notebooks/1.%20(12-09)%20An%C3%A1lise%20dos%20Dados%20do%20Scrapper.ipynb)
3. Desenvolvimento do Gráfico Multi Scatter-plots 1D: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/Notebooks/2.%20(19-09)%20Desenvolvimento%20do%20Gr%C3%A1fico%20Multi%20Scatter-plots%201-D.ipynb)
4. Reordenação das Colunas no Gráfico Multi Scatter-plot: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/Notebooks/3.%20(03-10)%20Reordena%C3%A7%C3%A3o%20das%20Colunas%20no%20Multi%20Scatter-plot.ipynb)
5. Identificação de Atributos Aleatórios: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/Notebooks/4.%20(10-10)%20Identifica%C3%A7%C3%A3o%20de%20Atributos%20Aleat%C3%B3rios.ipynb)
6. Filtragem de Atributos Mal Comportados: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/Notebooks/5.%20(07-11)%20Filtragem%20de%20Atributos%20Mal%20Comportados.ipynb)
7. Análise Conjunta dos Atributos Bem Comportados e Mal Comportados: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/Notebooks/6.%20(21-11)%20An%C3%A1lise%20Conjunta%20dos%20Atributos%20Bem%20Comportados%20e%20Mal%20Comportados.ipynb)

---

### Seção 2 - Análise Exploratória (EDA)
1. Análise do Comportamento do Nível Econômico sob uma Perspectiva Geográfica: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/2.%20EDA/0.%20EDA%20Nivel%20Economico/REGIONAL_ECONOMIC_LEVEL.ipynb)
2. Análise Exploratória do Número de Pessoas em cada Nível Educacional de cada Cidade: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/2.%20EDA/2.%20EDA%20Pessoas%20em%20Cada%20Nivel%20Educacional/RAIS_ESC_FREQ_(PCDII).ipynb)
3. Análise Exploratória da Renda em cada Setor Industrial de cada Cidade: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/2.%20EDA/3.%20EDA%20Setor%20Industrial/RAIS_RENDA%20(PCDII).ipynb)

---

### Seção 3 - Análise Espacial (Spatial Analysis)
1. Análise e pré-processamento dos dados de Investimentos Federais/Maturidade: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/drive/1H-UFlUElqIZPWiZx-WbYY11HoXHjqUUM)
2. Cobertura geográfica e Representatividade da amostra: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/drive/1tmKiPSczKZzR_CaihnKU_KZziBKatHvG)




