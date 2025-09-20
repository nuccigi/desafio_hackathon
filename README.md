# desafio_hackathon

## Objetivo:
O desafio consiste em prever a **quantidade semanal de vendas** por **PDV (Ponto de Venda)** e **SKU (Produto)** para as **5 primeiras semanas de janeiro/2023**, utilizando como base o histórico de vendas de 2022.  
A previsão serve para apoiar o varejo na **reposição de produtos**.

## Tecnologias Utilizadas:
- Python 3.10+
- Pandas
- Scikit-learn

## Metodologia:
Nesta primeira versão foi implementado um Baseline Média Móvel (4 semanas): 
  - Para cada combinação `PDV × SKU`, a previsão é a média das últimas 4 semanas de 2022.  
  - Esse valor é replicado para as 5 semanas de janeiro/2023.

### Validação:
Para validar a estratégia, usamos como “teste” as semanas 49–52 de 2022.  

Resultados obtidos:
- MAE: 3.14
- WMAPE: 49.45%
- Accuracy (1 - WMAPE): 50.55%

O baseline da média móvel superou outros métodos testados (Last Week e LightGBM).

## Instruções de Execução:

### 1. Clonar o repositório
```bash
git clone https://github.com/SEU_USUARIO/hackathon-forecast-2025.git
cd hackathon-forecast-2025
````


### 2. Instalar dependências
```bash
pip install -r requirements.txt
````

### 3. Extrair os dados
No notebook, ajustamos para ler diretamente os arquivos .parquet extraídos do .zip fornecido na competição.

## 4. Rodar o notebook
Abra o Jupyter ou Google Colab e execute o notebook principal:
```bash
notebooks/solucao_baseline.ipynb
````

## 5. Gerar a previsão final
O notebook gera automaticamente os arquivos de submissão:
- previsao.csv 
- previsao.parquet
