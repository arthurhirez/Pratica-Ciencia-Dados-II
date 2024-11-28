# Clusterização dos Municipios

Este tópico foi dedicado à tentativa de clusterizar os dados com o objetivo de verificar se seria interessante considerar os clusters formados, em vez das regiões e estados definidos pelo [IBGE](https://www.ibge.gov.br/). Para isso, foi utilizado o algoritmo Hierarchical Clustering, permitindo uma abordagem visual para observar o comportamento dos clusters formados.

<p align="center">
  <img src="https://github.com/user-attachments/assets/3375b31a-b922-454a-9c9c-2b0991319113" height="400" title="Exemplo da Cidade de São Carlos na Plataforma Inteli.Gente">
  <br>
  <a href="https://uc-r.github.io/hc_clustering">Fonte: https://uc-r.github.io/hc_clustering</a>
</p>

Para a formação dos clusters, foi considerado apenas os conjuntos de dados analisados nos tópicos anteriores,**EDA Setor Industrial** [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/1.%20EDA%20Setor%20Industrial) e **EDA Pessoas em Cada Nível Educacional** [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/2.%20EDA%20Pessoas%20em%20Cada%20Nivel%20Educacional), combinados com diferentes formas de pré-processamento e uma amostragem aleatória (Bootstrap), com o objetivo de gerar resultados mais significativos, avaliados a partir da **Medida de Silhueta** e **Davies Bouldin Score**.

## Dendogram
A fim de adotar uma abordagem visual na análise, foi inicialmente construído um dendrograma utilizando os dados disponíveis. Esses dados foram concatenados com base nos códigos dos municípios e, posteriormente, normalizados por meio da estratégia **MinMaxScale**. Esse processo de normalização é indispensável, pois o dendrograma se baseia em um critério de distância, o que poderia ser distorcido por variáveis com escalas discrepantes.

Entretanto, ao aplicar o algoritmo, constatou-se que, devido à heterogeneidade dos dados, as distâncias entre alguns clusters principais formados eram consideravelmente elevadas, indicando baixa similaridade entre eles. Essa característica dificultou a identificação clara da distribuição dos municípios nos grandes clusters gerados, além da formação de clusters desbalanceados.

<p align="center">
  <img src="Images/dendo1.png" alt="Descrição da imagem" width="800"/>
</p>
<p align="center">

Para aprimorar a compreensão dos clusters formados, foi definido um novo *threshold* baseado na distância. Contudo, como observado anteriormente, para identificar novos agrupamentos dentro do dendrograma, é necessário estabelecer um thresholder de valor baixo. Ao definir uma distância de $0.2$, formando 37 clusters ao total, tornou-se possível visualizar com maior clareza a formação de grupos mais bem delineados. Entretanto, também foi notada a formação de clusters com um número muito reduzido de municípios. Esse comportamento reforça, mais uma vez, a elevada diversidade presente nos dados analisados, ou até mesmo a presença de outliers.

<p align="center">
  <img src="Images/dendo3.png" alt="Descrição da imagem" width="800"/>
</p>
<p align="center">

Com o objetivo de determinar um número ideal de clusters cm base em uma métrica significativa, foi inicialmente empregada a medida de silhueta, sem a utilização da técnica de bootstrap — que será aplicada posteriormente para complementação da análise. Esse processo resultou na definição de 10 clusters.

<p align="center">
  <img src="Images/sil1.png" alt="Descrição da imagem" width="500"/>
</p>
<p align="center">

Contudo, o resultado final não apresentou uma visualização satisfatória. Além disso, observou-se novamente a formação de clusters altamente desbalanceados, o que reforça a complexidade de agrupar os dados disponíveis. Alguns clusters mostraram-se extremamente grandes e internamente muito heterogêneos, com altas distâncias entre os elementos. Por outro lado, alguns clusters menores apresentaram-se mais limitados em tamanho, o que pode ser um indicativo da presença de ruídos nos dados analisados.

<p align="center">
  <img src="Images/dendo2.png" alt="Descrição da imagem" width="800"/>
</p>
<p align="center">

Esse aspecto que também foi identificado nos resultados da análise **EDA Pessoas em Cada Nível Educacional** [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/2.%20EDA%20Pessoas%20em%20Cada%20Nivel%20Educacional), na seção de **Outliers**, no qual, evidenciou que a geração de clusters consistentes - utilizando o algoritmo **KMeans**, também baseado em distância - é um processo desafiador, quando se considera apenas os dados disponíveis, sem integrar o contexto espacial dos dados.

## Bootstrap e Normalização MinMax
A transformação **MinMax** foi aplicada aos dados de entrada antes da execução do algoritmo de clusterização, escalonando os dados para um intervalo fixo entre 0 e 1.

- **Silhuete Score:** Sem alterações, em cada amostra aleatória o melhor número de clusters permaneceu consistentemente como 2.
- **Davies Bouldin Score:** Apresentou variações ao longo das amostras aleatórias, indicando valores maiores, como 5 clusters em alguns casos. Contudo, a maioria dos resultados manteve-se concentrada em torno de 2 a 3 clusters.

<div style="display: flex; justify-content: center; align-items: center;">
  <figure> 
    <img src="Images/sil_pais.png" alt="Medida de Silhueta" width="435"/> 
  </figure> 
  <figure> 
    <img src="Images/db_pais.png" alt="Curva do Cotovelo" width="435"/>
</div>


## Boostrap e Normalização por Tamanho da Populção
Divisão dos atributos do município pela sua população estimada, antes da aplicação do algoritmo de clusterização, visando ajustar os dados e eliminar o impacto da magnitude populacional.

- **Silhuete Score:** Sem alterações, em cada amostra aleatória o melhor número de clusters permaneceu consistentemente como 2.
- **Davies Bouldin Score:** Apresentou variações ao longo das amostras aleatórias, indicando valores maiores, como 5 clusters em alguns casos. Contudo, a maioria dos resultados manteve-se concentrada em torno de 2 a 3 clusters.
- **Resultado:** Não muito satisfatório.
<div style="display: flex; justify-content: center; align-items: center;">
  <figure> 
    <img src="Images/sil_minmax.png" alt="Medida de Silhueta" width="435"/> 
  </figure> 
  <figure> 
    <img src="Images/db_minmax.png" alt="Curva do Cotovelo" width="435"/>
</div>

A abordagem não se mostrou eficaz na criação de clusters significativos. O modelo acabou separando os dados em apenas dois clusters, que foram:
1. 5.488 municípios com características diversas.
2. São Paulo e Rio de Janeiro, que foram agrupados devido os altos valores das suas características econômicas e populacionais.
    
## Boostrap e Normalização pelo Atributo Total (Renda e Frequência)
Divisão dos atributos do município pela soma total dos seus respectivos atributos. Esse processo ajuda a ajustar as variáveis para refletirem a proporção de cada atributo em relação ao total, de modo a minimizar o efeito de discrepâncias nas magnitudes dos atributos.

- **Silhuete Score:** Apresentou variações ao longo das amostras aleatórias, definindo o melhor número de clusters como 3.
- **Davies Bouldin Score:** Apresentou variações ao longo das amostras aleatórias, indicando valores maiores, como 14 clusters em alguns casos. Contudo, a maioria dos resultados manteve-se concentrada em torno de 3 a 4 clusters.
<div style="display: flex; justify-content: center; align-items: center;">
  <figure> 
    <img src="Images/sil_tot.png" alt="Medida de Silhueta" width="435"/> 
  </figure> 
  <figure> 
    <img src="Images/db_tot.png" alt="Curva do Cotovelo" width="435"/>
</div>

Abordagem, no qual, se teve o resultado mais satisfatorio em compração aos outros, no entanto, apresentando um número de clusters muito pequeno comparado a complexidade dos dados exposta nas analises anteriores. 
1. Cluster com 5480 cidades, desbalanceado
2. Cluster com municipio de São Paulo
3. Cluster com 8 capitais brasileiras
4. Cluster contentdo o municipio do Rio de janeiro

   
## Considerações Finais 
Ao analisarmos os clusters formados por cada estratégia, observamos que eles variam conforme a abordagem de pré-processamento utilizada. Uma estratégia interessante para lidar com os outliers, a **Normalização pelo Atributo Total**, conseguiu capturar mais diferenças entre os dados ao trabalharmos com as proporções. No entanto, como foi mostrado anteriormente, os clusters formados apresentaram um grande desequilíbrio em todos os casos, evidenciando a complexidade de gerar agrupamentos significativos e consistentes, considerando apenas os dados de escolaridade e setor industrial. Isso indica a necessidade de uma abordagem mais sofisticada, que leve em conta as interações espaciais e geográficas, entre outras informações do município. Nesse sentido, uma alternativa interessante seria adotar uma das divisões propostas pelo **IBGE**, que pode fornecer uma estrutura de agrupamentos definidos pelo governo brasileiro.
