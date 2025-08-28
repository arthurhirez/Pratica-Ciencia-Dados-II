## Escolha do Tema e Conjunto de Dados

O objetivo do trabalho é estudar como diferentes aspectos (indicadores econômicos/sociais/culturais/geográficos, etc) influenciam no nível de Maturidade dos municípios brasileiros, conforme definido na plataforma Inteli.gente (https://inteligente.mcti.gov.br/). Existem quatro níveis de Maturidade, como ilustrado abaixo para São Carlos, porém é tomada a decisão de focar na Maturidade Econômica (dada a escolha de dados desse domínio, como os relativos à emprego e investimentos públicos). Porém, ao longo do projeto, são feitas análises considerando os outros domínios, para testar a robustez das soluções.

<p align="center">
  <img src="images/inteli.gente.png" height="250" title="Exemplo da Cidade de São Carlos na Plataforma Inteli.Gente">
  <br>
  <a>Fonte: </a>
  <a href="https://inteligente.mcti.gov.br/municipios/sao-carlos-sp">https://inteligente.mcti.gov.br/municipios/sao-carlos-sp<a/>
</p>

Para enriquecer o projeto, são utilizados dados de bases públicas, reunindo informações geográficas (IBGE), relacionadas com renda e escolaridade dos trabalhadores (RAIS-MTE) e a nível de municípios (Investimentos Federais - MF e PIB per capita - IBGE), com detalhes em suas respectivas seções.

## Principais resultados

### Seção 3 - Análise Espacial (Spatial Analysis) [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis)
O objetivo inicial seria modelar a distribuição regional de investimentos Federais, partindo da suposição que verbas aplicadas em uma cidade beneficiam seu entorno e da necessidade, dado que não são todas as cidades que recebem investimentos. Porém, no desenvolvimento do projeto foi considerado que os resultados não seriam representativos, o que levou à mudança de objetivo. A partir desse ponto, o estudo foi focado em estudar um método de como definir a influência regional das cidades, utilizando técnicas de GIS.

É definida a metodologia experimental, quais parâmetros e casos são contemplados, e é proposta uma nova região, intitulada Agregada. Estudando São Carlos em 2020, verifica-se que a metodologia produz reusltados coerentes, e nota-se os efeitos de suavização e detecção de Hot/Cold spots dada a variação de Domínio e vizinhança, sendo concluido que perspectiva é importante para definir a importância regional. A análise avança sobre a dinâmica da influência regional, considerando a dimensão de tempo, utilizando quartis regionais nas compararações.

Por fim, é feita uma breve análise generalizando os quartis regionais, para PIB per capita e Investimentos. Sâo observados padrões interessantes, e toca-se na superfície de como correlacionar Investimentos com PIB per capita. Adicionalmente, é feita uma análise considerando Hot/Cold spots, e feita a introdução de uma nova métrica, que busca sintetizar a relação entre os Domínios considerados. 

Apesar de não concluir o objetivo inicial (regressão espacial), foi possível desenvolver uma exploração da dinâmica de relevância regional, e trabalhos futuros podem aprofundar questões como a correlação entre diferentes variáveis (relacionando PIB per capita com ocupação da população e investimentos), e com esse resultado em mãos, avançar sobre o desafio de modelar o efeito de benefícios indiretos na vizinhança.

## Detalhamento das Análises

### Seção 3 - Análise Espacial (Spatial Analysis) [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis)
1. Análise e pré-processamento dos dados de Investimentos Federais/Maturidade: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.1%20An%C3%A1lise%20Explorat%C3%B3ria) 
2. Cobertura geográfica e Representatividade da amostra: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.2%20Avalia%C3%A7%C3%A3o%20Amostragem) 
3.  Exploração biblioteca GIS - PySAL : [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.3%20Estudo%20biblioteca%20Pysal)
4. Dinâmica de Influência/Relevância regional [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.4%20An%C3%A1lise%20Espacial) 
5. Estatísticas Espaciais e Níveis de Maturidade: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.5%20Rela%C3%A7%C3%A3o%20com%20n%C3%ADveis%20de%20Maturidade)


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a) Resultados *Hot/Cold spots* considerando PIB *per capita* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; b) Resultados Diferença entre quartis **Agregada - Estadual**
<p float="left">
  <img src="docs/3.Spatial Analysis/imgs/base_pib_spot.gif" width="500" />
  <img src="docs/3.Spatial Analysis/imgs/base_pib_diff.gif" width="500" /> 
</p>


## Links Rápidos para Acesso dos Notebooks pelo Google Colab:

### Seção 3 - Análise Espacial (Spatial Analysis)
1. Análise e pré-processamento dos dados de Investimentos Federais/Maturidade: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/drive/1H-UFlUElqIZPWiZx-WbYY11HoXHjqUUM)
2. Cobertura geográfica e Representatividade da amostra: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/drive/1tmKiPSczKZzR_CaihnKU_KZziBKatHvG)




