# Definição de novo objetivo - **Influência regional** 

Nessa etapa do projeto, à época da execução, foi tomada a decisão de abandonar o objetivo inicial, que seria definir uma metodologia para distribuir valores de investimentos Federais, buscando modelar seu benefício para a população - e usar esses dados para inferir o nível de maturidade da cidade. Porém, conforme exposto na última seção, **não havia segurança sobre a significancia dos resultados dessa abordagem** (seriam basicamente números sem garantia de significado), portanto é tomada a decisão de projeto de investigar a dinâmica de relevância regional nos municípios paulistas.

Para isso, é expandida a base de dados, buscando realizar uma análise espaço-temporal. São coletados os dados de PIB *per capita* do período de 2010 à 2021, e os dados de investimentos Federais do período entre 2014 e 2023. A disparidade entre os casos impediu uma análise pareada, e pode ser tópico de projetos futuros (como estimar os anos anteriores/posteriores com base nos dados pareados, por exemplo). Os dados tem o mesmo tratamento dispensado na Seção 3.1 ([![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.1%20An%C3%A1lise%20Explorat%C3%B3ria)), e portanto não serão exibidos novamente.

# Análise Espaço-Temporal
## Estudo de caso - São Carlos
### Analisando parâmetros importantes - Vizinhança para agrupamento e Domínio considerado

Considerando as funcionalidades da biblioteca Pysal, apresentadas na seção anterior, é feito o desenho de um experimento variando o Domínio considerado (Regiões Imediata, Intermediária, Agregada e Estadual) e a granularidade da vizinhança (Município, Imediata, Intermediária, Agregada e Estadual) para o agrupamento das cidades, que é relevante para o cálculo do *Spatial Lag* e *Hot/COld spots*. Uma descrição da metodologia é exibida abaixo, assim como a verificação realizada para conferir se os resultados obtidos estavam coerentes. É proposto um Domínio novo aos do IBGE, denominada Região Agregada é uma granularidade entre Região Intermediária e Estadual, e que foi baseada no cálculo de *Spatial Lag*, no qual são consideradas todas as Regiões Imediatas que são vizinhas à Região Imediata da cidade em análise.

<!-- podia fazer melhor kkkkkk  preguiça-->
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Metodologia Proposta e Teste de Sanidade**
 <img src="../imgs/Interpretacoes_geral.png" width="1000" />

Sobre as relações locais preservadas com a inclusão de novos casos (mudança de Domínio mantendo nível de agrupamento), observa-se que a relação entre quartis, na região Imediata de São Carlos (primeira linha) e considerando as mesmas cidades na região Intermediária (segunda linha), se mantem, ou seja, quartis maiores continuam maiores e vice e versa. SObre a mudança de agrupamento mantendo o mesmo Domínio (segunda e terceira linhas), nota-se o efeito suavizador obtido ao aumentar a granularidade do agrupamento. Por fim, nota-se que aumentar o Domínio considerado, assim como aumentar a granularidade no mesmo Domínio, tem efeitos de revelar *Hot/Cold spots* .



### Influência regional depende da perspectiva
Seguindo o raciocínio anterior, os resultados experimentais revelam os principais efeitos da variação de vizinhança para agrupamento. O primeiro diz respeito às mudanças no *Spatial Lag*, em que a suavização é proporcional à granularidade, ou seja, uqanto maior a vizinhança a ser agrupada (Região Intermediária, como exemplificado abaixo) maior a suavização do *Spatial Lag*. O outro efeito, já notado anteriormente, é a emergência de 8Hot/Cold spots* no mesmo Domínio com o aumento da vizinhança agrupada.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Impacto da variação da vizinhança para agrupamento**
  <img src="../imgs/Interpretacoes_regional.png" width="1000" />

 A princípio, as conclusões expostas dos resultados experimentais, nesse ponto do projeto, indicavam que as análises deveriam ser direcionadas considerando Domínios mais abrangentes e vizinhanças amplas. Porém, uma vez que o objetivo do projeto é explorar a dinâmica de relevância/influência regional, não era desejado perder dados sobre lideranças locais. Além disso, todas as conclusões foram tiradas tomando em conta somente o ano de 2020, e verificar essa dinâmica ao longo do tempo é o tema da próxima análise.



### Quartis como métrica de comparação/avaliação

Buscando a comparabilidade dos resultados e robustez contra as variações entre municípios (tamanho da população e riqueza por exemplo), e a exemplo da escolha do PIB *per capita* ao invés dos valores absolutos descrito em seção anterior, elege-se os quartis "regionais" como métrica. Essa era uma escolha natural pelo andamento da análise, por ser uma forma adimensional de ordenar os casos, permitindo comparações imediatas.  Pelas razões já descritas, é feita a análise temporal (primeira linha mostra as distribuições dos quartis em cada ano, para cada domínio), e os resultados das variações no Domínio (segunda linha, para cada tipo de agrupamento) e na vizinhança a ser agrupada (terceira linha, para cada Domínio), com os resultados e uma explicação visual abaixo.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Análise Temporal dos Quartis "Regionais"**
 <img src="../imgs/Demo_analise.gif" width="1000" />

Interpretando os resultados, nota-se que a Região Agregada proposta promove o diferencial de imbuir múltiplas perspectivas da relevância de uma cidade. Aliado às conclusões obtidas anteriormente, de que Domínios maiores induzem à uma maior suavização e detecção de *Hot/Cold spots*, é decidido trabalhar nas **análises finais com os Domínios de Região Agregada e Estadual, e agrupamento feito com vizinhanças de Região Intermediária.**

## Escolha da variável de análise: PIB x Investimentos

### Explorando padrões à nivel Estadual

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **Casos selecionados para análise espaço-temporal**
 <img src="../imgs/Stats_Spatial.gif" width="1000" />


### Considerando dimensão Temporal - Quartis


<!-- podia fazer melhor kkkkkk  preguiça-->
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a) Resultados PIB per capita dos municípios&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; b) Resultados Investimentos Federais
<p float="left">
  <img src="../imgs/base_invest_quartis_frame.gif" width="500" />
  <img src="../imgs/base_pib_quartis_frame.gif" width="500" /> 
</p>




### Considerando dimensão Temporal - Diff e HOtCold 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a) Resultados *Hot/Cold spots*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   b) Resultados Diferença entre quartis **Agregada - Estadual**
<p float="left">
  <img src="../imgs/base_pib_spot.gif" width="500" />
  <img src="../imgs/base_pib_diff.gif" width="500" /> 
</p>



