![Inteli.Gente Banner](images/Inteli.Gente.Banner.png)

# SCC0957 - Prática em Ciência de Dados II

Este repositório possui os scripts, em formato Python Notebook (IPynb), utilizados para aquisição e análise dos dados do nosso projeto na disciplina.

## Links Rápidos para Acesso dos Notebooks pelo Google Colab:
1. Análise Exploratória dos Investimentos de cada Cidade: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/Exploratoria_Investimentos.ipynb)
2. Scrapper utilizado para extrair os dados da plataforma Inteli.Gente: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/Scrapper%20(PCDII).ipynb)
3. Análise Exploratória do Número de Pessoas em cada Nível Educacional de cada Cidade: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/RAIS_ESC_FREQ%20(PCDII).ipynb)
4. Análise Exploratória da Renda em cada Setor Industrial de cada Cidade: [![Open with Colab](https://img.shields.io/badge/Open_In_Colab-0?logo=GoogleColab&color=525252)](https://colab.research.google.com/github/Rafaelsoz/Pratica-Ciencia-Dados-II/blob/main/RAIS_RENDA%20(PCDII).ipynb)

## Resumo das Análises

#### 1. Análise Exploratória dos Investimentos de cada Cidade
Resumo da Análise

#### 2. Scrapper utilizado para extrair os dados da plataforma Inteli.Gente
Explicação do Scrapper

## Documentação

### Escolha do Tema e Conjunto de Dados - 08/08/2024
Optamos explorar a relação entre o nível de maturidade econômica de um município, calculado com base em indicadores como acesso à água, transporte e tecnologia, e seus dados de investimento público, emprego e  renda.

<p align="center">
  <img src="images/inteli.gente.png" height="250" title="Exemplo da Cidade de São Carlos na Plataforma Inteli.Gente">
  <br>
  <a>Fonte: </a>
  <a href="https://inteligente.mcti.gov.br/municipios/sao-carlos-sp">https://inteligente.mcti.gov.br/municipios/sao-carlos-sp<a/>
</p>

### Web-Scraping e Download dos Conjuntos de Dados Iniciais - 15/08/2024

Para obter os dados necessários, realizamos webscraping dos dados de maturidade, juntamente com dados espaciais como código, nome, latitude e longitude dos municípios. Diferentemente dos demais dados, que estavam disponíveis em arquivos CSV.

Os dados de cada cidade foram extraídos pelo end-point da API da plataforma Inteli.Gente: <br>
```https://inteligente-backend.mcti.gov.br/api/cities/{codigo}```

Para listar o código e cada cidade disponível no dataset da plataforma, utilizamos o end-point: 
<br>
```https://inteligente-backend.mcti.gov.br/api/cities/autocomplete```
<br>
junto do parâmetro de requisição GET ```term``` que é sobrecarregado com os caracteres que o usuário digita no campo de busca da plataforma.

<p align="center">
  <img src="images/Inteli.Gente.Search.png" height="250" title="Exemplo da Cidade de São Carlos na Plataforma Inteli.Gente">
  <br>
  <a>Fonte: </a>
  <a href="https://inteligente.mcti.gov.br/">https://inteligente.mcti.gov.br/<a/>
</p>

```json
[
    {
        "id": 1507102,
        "friendlyName": "sao-caetano-de-odivelas",
        "result": "São Caetano de Odivelas, PA"
    },
    {
        "id": 3548807,
        "friendlyName": "sao-caetano-do-sul",
        "result": "São Caetano do Sul, SP"
    },
    {
        "id": 2613107,
        "friendlyName": "sao-caitano",
        "result": "São Caitano, PE"
    }
    ...
]
```
*Exemplo de Resposta da API da plataforma Inteli.Gente no endpoint ```autocomplete```*

Esse end-point é utilizado pela plataforma para sugerir opções de cidades na hora da busca, enquanto o usuário digita. Para catalogar todas as cidades disponíveis no banco de dados da plataforma, o script pesquisa todas letras do alfabeto, de A até Z, e extrai as keys ```result``` e ```friendlyName``` para cada um dos resultados. 
