<img src="https://cdn.pixabay.com/photo/2013/07/12/17/00/accident-151668_1280.png" alt="Descrição da Imagem" width="700" height="300">

# Análise Descritiva de Acidentes no Brasil

Projeto da disciplina de Introdução à Análise de Dados no Curso de Pós-Graduação Lato Sensu em Visão Computacional, uma proposta de um sistema de Análise Descritiva de Acidentes no Brasil baseado em dados do DENATRAM coletados entre 2017-2019

## Descrição do Projeto

Este projeto tem como objetivo realizar uma análise descritiva dos acidentes ocorridos nas rodovias federais do Brasil, com foco específico nas rodovias da região Nordeste durante o ano de 2018. A análise foi conduzida utilizando técnicas de visualização de dados e bibliotecas de ciência de dados para fornecer insights valiosos sobre a distribuição e características dos acidentes.

## Estrutura do Projeto

### 1. Coletar Dados

A primeira etapa do projeto envolve a coleta dos dados dos acidentes, que foram obtidos do arquivo CSV `datatran2018.csv` contendo informações detalhadas sobre os acidentes nas rodovias brasileiras.

### 2. Importação de Bibliotecas

```python
# coleta, tratamento e manipulação dos dados
import numpy as np
import pandas as pd

# visualização e geração de mapas de calor
import folium
from folium import plugins
import branca.colormap as cm

# visualização e geração dos gráficos
import matplotlib.pyplot as plt
from datetime import time
```

### 3. Filtragem dos Dados
Os dados foram filtrados para incluir apenas os acidentes ocorridos na região Nordeste do Brasil.

```python
# Lê o dataset de acidentes no Brasil armazenado no arquivo csv
df = pd.read_csv("datatran2018.csv", encoding='latin', sep=";", error_bad_lines=False)

# Cria um filtro para selecionar apenas acidentes no Nordeste
filter_northeast = ((df["uf"] == "BA") | (df["uf"] == "PE") | (df["uf"] == "AL") |
                    (df["uf"] == "MA") | (df["uf"] == "CE") | (df["uf"] == "PB") |
                    (df["uf"] == "PI") | (df["uf"] == "RN") | (df["uf"] == "CE"))

# Atualiza o dataframe apenas com os acidentes no Nordeste
df = df[filter_northeast]

# Mostra o número de linhas (acidentes) e colunas (informações) do dataframe de acidentes
df.shape
```

## Resultados

Os dados foram analisados para identificar padrões e tendências nos acidentes, incluindo a localização geográfica, causas comuns e outros fatores relevantes.

## Como Usar Este Repositório
1. Pré-requisitos: Python 3.x, bibliotecas como numpy, pandas, folium, branca, matplotlib.
2. Instalação:
  ```bash
  pip install -r requirements.txt
  ```
3.  Executar o Projeto:
- Importe as bibliotecas necessárias.
- Carregue e filtre os dados conforme descrito.
- Visualize e analise os dados usando os scripts fornecidos.

Este repositório contém todo o código necessário para reproduzir os resultados apresentados e pode servir como base para futuros trabalhos na área de análise de acidentes de trânsito utilizando ciência de dados.
