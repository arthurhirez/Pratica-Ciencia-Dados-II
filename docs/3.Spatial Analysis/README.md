# Maturidade dos municípios da plataforma inteli.gente (MCTI)

Plataforma do Ministério da Ciência, Tecnologia e Inovação (MCTI) que define cidades inteligentes como:

"... **cidades comprometidas com o desenvolvimento urbano sustentável e a transformação digital**, em seus aspectos econômico, meio ambiente, sociocultural e de capacidade institucional, ... e **utilizam tecnologias para solucionar problemas concretos, criar oportunidades, oferecer serviços com eficiência, reduzir desigualdades,** aumentar a resiliência **e melhorar a qualidade de vida de todas as pessoas**, garantindo o **uso seguro e responsável de dados** e das tecnologias da informação e comunicação.**"
<br><br>
<img src="imgs/art_dimensoes.png" alt="Sample Plot" width="1000"/>
**fonte:** https://inteligente.mcti.gov.br/


# Detalhamento da análise espacial
O projeto desenvolvido busca relacionar dados econômicos dos municípios com seus níveis de Maturidade, e a documentação faz uma descrição das etapas envolvidas, os desafios encontrados e superados e as conclusões do prjeto

## Contextualização
O projeto é dividido em 5 etapas, que são brevemente descritas como:
1. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.1%20An%C3%A1lise%20Explorat%C3%B3ria) **Análise exploratória e pré-processamento** : Detalha a coleta e descrição das bases escolhidas. As decisões de projeto relativas ao pré-processamento são descritas, e as visualizações iniciais que motivaram as próximas etapas são exibidas.
2. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.2%20Avalia%C3%A7%C3%A3o%20Amostragem) **Qualidade da amostra** : Uma vez que é encontrado o desafio da esparsidade geográfica dos Investimentos, explora-se a representatividade das localidades que receberam investimentos em 2023 frente à totalidade dos municípios brasileiros.
3. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.3%20Estudo%20biblioteca%20Pysal) **Exploração biblioteca GIS - PySAL** : O objetivo inicial seria modelar a distribuição dos investimentos regionalmente. Para isso é escolhida a biblioteca PySAL, buscando explorar a dinâmica de influênia/relevância regional. Porém, o estudo da ferramenta levanta dúvidas quanto à viabilidade dessa abordagem, e é feita a decisão de estudar mais a fundo elementos que regem essa dinâmica de influência.
4. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.4%20An%C3%A1lise%20Espacial) **Dinâmica de Influência/Relevância regional**:
5. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.5%20Rela%C3%A7%C3%A3o%20com%20n%C3%ADveis%20de%20Maturidade) **Estatísticas Espaciais e Níveis de Maturidade**: 

