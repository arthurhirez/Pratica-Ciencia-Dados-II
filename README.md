![Inteli.Gente Banner](images/Inteli.Gente.Banner.png)

# SCC0957 - Prática em Ciência de Dados II

Este repositório possui os scripts, em formato Python Notebook (IPynb), utilizados para aquisição e análise dos dados do nosso projeto na disciplina.


### Escolha do Tema e Conjunto de Dados - 08/08/2024
Optamos explorar a relação entre o nível de maturidade econômica de um município, calculado com base em indicadores como acesso à água, transporte e tecnologia, e seus dados de investimento público, emprego e  renda.

<p align="center">
  <img src="images/inteli.gente.png" height="250" title="Exemplo da Cidade de São Carlos na Plataforma Inteli.Gente">
  <br>
  <a>Fonte: </a>
  <a href="https://inteligente.mcti.gov.br/municipios/sao-carlos-sp">https://inteligente.mcti.gov.br/municipios/sao-carlos-sp<a/>
</p>


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


## Análises

### Seção 1 - Scrapping, Visualização e Seleção de Features
1. Web-Scraping na Plataforma Inteli.Gente (15/08/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/1.%20Scrapper)
2. Análise Inicial dos Dados do Inteli.Gente (12/09/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/1.%20(12-09-2024)%20An%C3%A1lise%20dos%20Dados%20do%20Scrapper.md)
3. Desenvolvimento do Gráfico Multi Scatter-plots 1D (19/09/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/2.%20(19-09-2024)%20Desenvolvimento%20do%20Gr%C3%A1fico%20Multi%20Scatter-plots%201-D.md)
4. Reordenação das Colunas no Gráfico Multi Scatter-plot (03/10/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/3.%20(03-10-2024)%20Reordena%C3%A7%C3%A3o%20das%20Colunas%20no%20Multi%20Scatter-plot.md)
5. Identificação de Atributos Aleatórios (10/10/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/4.%20(10-10-2024)%20Identifica%C3%A7%C3%A3o%20de%20Atributos%20Aleat%C3%B3rios.md)
6. Filtragem de Atributos Mal Comportados (07/11/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/5.%20(07-11-2024)%20Filtragem%20de%20Atributos%20Mal%20Comportados.md)
7. Análise Conjunta dos Atributos Bem Comportados e Mal Comportados (21/11/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/docs/1.%20Scrapper/Analises/6.%20(21-11-2024)%20An%C3%A1lise%20Conjunta%20dos%20Atributos%20Bem%20Comportados%20e%20Mal%20Comportados.md)

---

### Seção 2 - Análise Exploratória (EDA)
1. Análise do Comportamento do Nível Econômico sob uma Perspectiva Geográfica (10/09/2024 - 21/11/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/0.%20EDA%20Nivel%20Economico)
2. Análises Exploratórias do Comportamento do Nível Econômico, Educacional e Setores Industriais (12/08/2024 - 21/11/2024): [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/Rafaelsoz/Pratica-Ciencia-Dados-II/tree/main/docs/2.%20EDA/0.%20EDA%20Nivel%20Economico)

---

### Seção 3 - Análise Espacial (Spatial Analysis)
1. Análise e pré-processamento dos dados de Investimentos Federais/Maturidade: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.1%20An%C3%A1lise%20Explorat%C3%B3ria) 
2. Cobertura geográfica e Representatividade da amostra: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.2%20Avalia%C3%A7%C3%A3o%20Amostragem) 
3.  Exploração biblioteca GIS - PySAL : [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.3%20Estudo%20biblioteca%20Pysal)
4. Dinâmica de Influência/Relevância regional [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.4%20An%C3%A1lise%20Espacial) 
5. Estatísticas Espaciais e Níveis de Maturidade: [![Open with GitHub](https://img.shields.io/badge/Open_In_GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/arthurhirez/Pratica-Ciencia-Dados-II/tree/main/docs/3.Spatial%20Analysis/3.5%20Rela%C3%A7%C3%A3o%20com%20n%C3%ADveis%20de%20Maturidade)



