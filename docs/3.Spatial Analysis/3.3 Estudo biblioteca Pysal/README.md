# Experimentos com biblioteca **PySAL**

**Créditos e fonte dos códigos *Spatial lag:* ** https://pysal.org/esda/


Nessa seção são exibidos os resultados de experimentos realizados para conhecer as funcionalidades da biblioteca Pysal, que implementa ferramentas de GIS (*Geographic Information System*). São utilizados tutoriais disponíveis na documentação da biblioteca, e é feita a referência à documentação original por sua completude, exemplos diversos e explicação detalhada sobre o método. Dessa maneira, o leitor tem acesso à uma material com implementação e vasta exploração da literatura - e pode explorar os outros módulos da biblioteca. [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/pysal/esda/blob/main/notebooks/Spatial%20Autocorrelation%20for%20Areal%20Unit%20Data.ipynb)


## *Spatial lag* e Análise de *Hot/Cold spots*
 Os resultados obtidos para a suavização através do uso de *Spatial Lag* e para a definição de *Hot/Cold spots* são exibidos abaixo.
 
### Definição de conceitos

A definição de *Spatial lag* dada na biblioteca, e para a vizinhança $$i$$ é definido como:

$$ylag_i = \sum_j w_{i,j} y_j$$

Onde:
* $$w_{i,j}$$ é o peso aplicado entre as vizinhanças $$i$$ e $$j$$, e pode ser visto uma medida de adjacência espacial. No experimento, utiliza-se o peso "*Queen*", baseado no movimento da peça no xadrez, ou seja, o peso vai ser igual a 1 para qualquer região adjacente e 0 caso contrário.

*Spatial lag* pode ser definido, de forma simplificada ao extremo, como um método de regularização, que leva em conta os valores da vizinhança para definir uma média suavizada.

Sobre *Hot/Cold spots*, é utilizada a estatística **I** de Moran, uma medida da concentração geral dos dados espaciais. É definida como:

$$
I = \frac{N}{W} \cdot \frac{\sum_{i=1}^N \sum_{j=1}^N w_{ij}(x_i - \bar{x})(x_j - \bar{x})}{\sum_{i=1}^N (x_i - \bar{x})^2}
$$

Onde:
- $$N$$ é o número de unidades espaciais indexadas por $$i$$ e $$j$$;
- $$x$$ é a variável de interesse;
- $$\bar{x}$$ é a média de $$x$$;
* $$w_{ij}$$ são os elementos de uma matriz de pesos espaciais com zeros na diagonal (ou seja, $$w_{ii} = 0$$);
* $$W$$ é a soma de todos os $$w_{ij}$$ (ou seja, $$W = \sum_{i=1}^N \sum_{j=1}^N w_{ij} $$).

Ou seja, é uma medida de variância local. A definição *Hot/Cold spots* é feita utilizando os quadrantes da estatística de Moran (ver a documentação Pysal, muito bem explicada por sinal, para entendimento real do método), e é feita como:
- *Hot spot:* Primeiro quadante - determina os valores de *Spatial Lag* que aumentam em conjunto com o valor real;
- *Cold spot:* Terceiro quadrante - determina os valores de *Spatial Lag* que diminuem em conjunto com o valor real;
- *Doughnut :* Segundo quadrante - serve como um *buffer* entre os dois primeiros casos, ou seja, uma situação intermediária;
- *Diamond :* Quarto quadrante - Um caso a parte de *Cold spot*, em que o valor de um caso "puxa" a vizinhança de forma significante;

### Resultados experimentais

Para clarificar as definições acima, e consolidar o domínio da bilbioteca antes de aplicá-la indiscriminadamente nos dados, é feita uma implementação experimental com os dados de PIB *per capita*. Em primeiro momento é calculada a média da vizinhança de cada cidade, ou seja, é definida a Região Imediata como vizinhança e calculada a média do PIB *per capita* das cidades que a compõem. Os resultados são exibidos abaixo, com as cores representado os quartis, sendo os tons mais escuros relativos ao primeiro e segundo quartis (PIB *per capita* mais baixo) e os tons mais claros para o terceiro e quarto quartis. São considerados  na visualização abaixo diferentes *Domínios*, a saber *Nacional, Interrregional* (Sul e Sudeste), *Regional* (Sudeste) e *Estadual* (SP), respectivamente.

TODO: TERMINAR

# Conclusão Terceira Etapa

Considera-se que foi possível dominar com certa confiança as funcionalidades da biblioteca, e portanto esta será empregada no restante das análises. Nesse ponto do desenvolvimento do projeto foi tomada uma **decisão importante**. Os resultados exibidos acima não foram imediatos, e a curva de aprendizagem não foi tão suave, porém levantou uma questão importante. Para viabilizar fazer uma regressão a nível espacial, e inferir como valores de supostos benefícios de investimentos públicos seriam dsitribuídos e afetariam sua vizinhança, uma investigação mais aprofundada é necessária.

O conhecimento da dinâmica de relevância regional é necessário, e portanto é decidido continuar a etapa de análise exploratória, a fim de determinar a **relevância regional utilizando dados de investimento e PIB *per capita***

Próxima etapa: **Dinâmica de Influência/Relevância regional** [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.4%20An%C3%A1lise%20Espacial)
