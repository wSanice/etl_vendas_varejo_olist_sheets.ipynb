# ETL de Vendas Olist para Google Sheets

Este repositório contém um notebook Python (`.ipynb`) que executa um processo de **ETL (Extract, Transform, Load)** completo. Este Notebook contem um script que foi responsável por extrair os dados brutos do dataset Olist (varejo brasileiro), tratá-los e carregá-los em uma planilha Google Sheets, onde servem de base para um dashboard interativo.

## O que este notebook faz:

O arquivo `etl_vendas_varejo_olist_sheets.ipynb` é responsável pelas três etapas do ETL:

### 1. Extract
* Conecta-se à API do Kaggle para baixar o dataset público "Brazilian E-Commerce Public Dataset by Olist".
* Descompacta os 9 arquivos CSV que compõem o dataset.

### 2. Transform
* Utiliza a biblioteca **Pandas** para carregar os múltiplos arquivos CSV.
* Realiza a limpeza e tratamento dos dados (ex: conversão de tipos de data, tratamento de valores nulos).
* Executa os *merges* (joins) necessários para consolidar dados de pedidos, clientes, produtos e itens em uma única tabela-fato principal.
* Filtra e seleciona apenas os dados de um período específico (2018) e as colunas relevantes para a análise, otimizando o desempenho no Google Sheets.

### 3. Load
* Utiliza a biblioteca **Gspread** e a autenticação do Google Colab para se conectar à API do Google Sheets.
* Envia o DataFrame Pandas tratado e limpo diretamente para uma planilha Google Sheets específica, que serve como "banco de dados" para o dashboard.

---

Este notebook é o "back-end" do projeto. O "front-end" da análise (KPIs, filtros e gráficos) pode ser visualizado no dashboard interativo no link abaixo:

<img width="960" height="456" alt="front" src="https://github.com/user-attachments/assets/2934929e-07a2-4093-8ed6-502eddb97433" />

**[Link para o Dashboard Interativo no Google Sheets](https://docs.google.com/spreadsheets/d/1tUZLQqLxO3obK7nMH3b_4pIqfOW2FMw9F63Tvb3Vrec/edit?usp=sharing)**
