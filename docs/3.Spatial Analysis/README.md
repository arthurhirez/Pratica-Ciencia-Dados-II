# Visão do projeto

A necessidade de aplicações de Aprendizado de Máquina auditáveis, em conformidade com a legislação do Brasil (Regulamento sobre o uso de IA - Projeto de Lei nº 2338/2023) e da União Europeia (*AI Act* para regulamentação sobre o uso da IA ​​a partir de 03/2024), por exemplo, demanda a busca por soluções que possam ser facilmente interpretáveis. Portanto, nesse projeto é dada especial atenção à documentação dos passos, à descrição detalhada das decisões e à checagem da coerência dos resultados. Desta maneira, o foco principal nas etapas foi utilizar as ferramentas e interpretar os resultados buscando informação, e não apenas números, como será observado no desenvolvimento do projeto.


# Importação dos dados de Maturidade dos municípios da plataforma inteli.gente (MCTI)

Plataforma do Ministério da Ciência, Tecnologia e Inovação (MCTI) que define cidades inteligentes como:

"... **cidades comprometidas com o desenvolvimento urbano sustentável e a transformação digital**, em seus aspectos econômico, meio ambiente, sociocultural e de capacidade institucional, ... e **utilizam tecnologias para solucionar problemas concretos, criar oportunidades, oferecer serviços com eficiência, reduzir desigualdades,** aumentar a resiliência **e melhorar a qualidade de vida de todas as pessoas**, garantindo o **uso seguro e responsável de dados** e das **tecnologias da informação e comunicação.**"

<br><br>

<img src="imgs/art_dimensoes.png" alt="Sample Plot" width="1000"/>
**fonte:** https://inteligente.mcti.gov.br/


Nesse contexto, é feito um estudo sobre como fatores geográficos, e considerando indicadores econômicos das cidades, influenciam no nível de maturidade dos municípios brasileiros. Porém, para esse objetivo é necessária uma investigação minunciosa da interrelação entre localidades, em especial como definir Influência/Relevância regional das cidades.

# Detalhamento da análise espacial

## Contextualização
O projeto é dividido em 5 etapas, que são brevemente descritas como:
1. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.1%20An%C3%A1lise%20Explorat%C3%B3ria) **Análise exploratória e pré-processamento** : Detalha a coleta e descrição das bases escolhidas. As decisões de projeto relativas ao pré-processamento são descritas, e as visualizações iniciais que motivaram as próximas etapas são exibidas.
2. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.2%20Avalia%C3%A7%C3%A3o%20Amostragem) **Análise geográfica e Avaliação da amostra** : Uma vez que é encontrado o desafio da esparsidade geográfica dos Investimentos, explora-se a representatividade das localidades que receberam investimentos em 2023, frente à totalidade dos municípios brasileiros.
3. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.3%20Estudo%20biblioteca%20Pysal) **Exploração biblioteca GIS - PySAL** : O objetivo inicial seria modelar a distribuição dos investimentos regionalmente. Para isso, é escolhida a biblioteca PySAL, buscando explorar a dinâmica de influênia regional. Porém, o estudo da ferramenta levanta dúvidas quanto à viabilidade dessa abordagem, e é feita a decisão de estudar mais a fundo elementos que regem essa dinâmica de influência.
4. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.4%20An%C3%A1lise%20Espacial) **Dinâmica de Influência/Relevância regional**: É feita a descrição do experimento realizado, com pormenorização das considerações e conclusões. Destaca-se a importância da nova granularidade de vizinhança (denominada Região Agregada) para a análise espaço-temporal, uma vez que permite incluir diferentes perspectivas das localidades de interesse na análise.
5. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.5%20Rela%C3%A7%C3%A3o%20com%20n%C3%ADveis%20de%20Maturidade) **Estatísticas Espaciais e Níveis de Maturidade**: É feita a relação entre as denominadas estatísticas espaciais, obtidas no item anterior, com as informações de Maturidade obtidas na primeira etapa. Verifica-se que as estatística espaciais conseguem descrever de forma satisfatória cidades com diferentes níveis de maturidade, mesmo em casos em que a variável original falha na tarefa.


## Preview resultados - Modelagem da Influência/Relevância Regional dos Municípios

### Quanto a correlação entre PIB *per capita* e Investimento Federais ao longo dos anos
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a) Resultados PIB *per capita*  dos municípios&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; b) Resultados Investimentos Federais
<p float="left">
  <img src="./imgs/base_pib_quartis_frame.gif" width="500" />
  <img src="./imgs/base_invest_quartis_frame.gif" width="500" /> 
</p>


### Métricas para quantificar Influência/Relevância Regional 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a) Resultados *Hot/Cold spots* considerando PIB *per capita* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; b) Resultados Diferença entre quartis **Agregada - Estadual**
<p float="left">
  <img src="./imgs/base_pib_spot.gif" width="500" />
  <img src="./imgs/base_pib_diff.gif" width="500" /> 
</p>



# Conclusões do projeto e expectativas futura
O presente projeto começou com a expectativa de estudar como Investimentos Federais influenciam o Nìvel da Maturidade Econômica (obtidos na plataforma Inteli.gente do Ministério da Ciência, Tecnologia e Inovação) dos municípios brasileiros. É verificado o desafio de que nem todas as localidades recebem investimentos, o que a princípio inviabilizaria a análise direta. Para lidar com esse obstáculo, levanta-se a suposição que os investimentos em uma cidade tem benefícios indiretos para seu entorno. Partindo dessa suposição, é feita uma análise quanto à representatividade da amostra (lugares que receberam investimentos em 2023) em relação à totalidade de cidades no Brasil. É verificado que o PIB *per capita* tem boa representatividade, e a estratégia traçada seria utilizar esse valor (que existe para todas as cidades) para modelar o efeito de distribuição regional local mencionado acima.

Um entrave para essa abordagem é a falta de domínio sobre a dinâmica de influência/relevância regional de cada cidade. Em dado momento, é feita uma tentativa de distribuir os valores regionalmente, porém conclui-se que esse tipo de abordagem pode gerar "resultados", porém não há confiança quanto à qualidade destes, sendo passada a impressão que são somente números - não informação. Nesse ponto do desenvolvimento do projeto, é feita a mudança de objetivo de pesquisa, sendo essa definida agora em continuar na investigação experimental de modelar influências regionais.

Essa etapa do projeto foi a mais desafiadora - e recompensadora. É utilizada uma ferramenta de GIS (Geographic Information System), implementada na biblioteca PySAL, para averiguar a dinâmica de relacionamentos espaciais. Após estudo dos recursos disponíveis, opta-se por conduzir a análise utilizando *Spatial Lag* (uma forma de regularização/suavização) e *Hot/COld spots* (utiliza a estatística *I* de Moran para definir localidades de interesse). É desenhado um experimento sobre os impactos de escolha de Domínio (quantidade de municípios considerados) e Vizinhança para agrupamento (crucial para o cálculo de *Spatial Lag* ). É feita a proposta de uma nova granularidade de vizinhança para agregação, sendo denominada Região Agregada, que permite explorar diferentes perspectivas do mesmo município.

As conclusões dessa etapa são que a proposta de R. Agregada como Domínio conduz a resultados relevantes, e quando aliada à consideração de vizinhanças amplas (R. Intermediária do IBGE), obtem-se resultados coerentes para a modelagem de influência regional. Com os reusltados consolidados, para Investimentos Federais e PIB *per capita*, é viabilizada a investigação das relações regionais, sendo possível inferir polos regionais, e observar a mudança de importância de certas localidades. A correlação entre Invesitmentos e PIB *per capita* é verificada, de forma superficial, e pode ser explorada mais a fundo em trabalhos futuros. Por fim, verifica-se que as estatísticas espaciais conseguem boa discriminação do nível de Maturidade, mesmo em casos em que a variável original (PIB *per capita*) falha em separar as observações.

Nesse contexto, considera-se que a pesquisa teve resultados satisfatórios, e além do esperado. Apesar de não concluir o objetivo inicial, foi possível desenvolver uma exploração da dinâmica de relevância regional, e trabalhos futuros podem aprofundar questões como a correlação entre diferentes variáveis (relacionando PIB *per capita* com ocupação da população e investimentos), e com esse resultado em mãos, avançar sobre o desafio de modelar o efeito de benefícios indiretos na vizinhança.
