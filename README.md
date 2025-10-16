# Análise e Previsão de Churn Bancário

## Visão Geral do Projeto

Este projeto utiliza um conjunto de dados de clientes de um banco para analisar os fatores que levam ao "churn" (cancelamento de conta) e para construir modelos de machine learning capazes de prever a probabilidade de um cliente cancelar seu relacionamento com o banco. A análise abrange desde a exploração inicial dos dados até a avaliação de diferentes algoritmos de classificação.

## Estrutura do Repositório

```
.
├── Bank_Churners.ipynb
├── Questions.txt
├── BankChurner.csv
└── README.md
```

## Arquivos

* **`Bank_Churners.ipynb`**: Um Jupyter Notebook que contém toda a análise, desde o carregamento dos dados até a avaliação dos modelos.
* **`BankChurners_Process.csv`**: O conjunto de dados processado e utilizado na análise.
* **`README.md`**: Este arquivo, com a documentação do projeto.

## Análise e Modelagem

O projeto é dividido nas seguintes etapas:

### 1. Análise Exploratória dos Dados (EDA)

Nesta fase, investigamos a distribuição e as características dos dados dos clientes. As principais observações incluem:

* **Gênero**: A base de clientes é bem distribuída entre homens e mulheres.
* **Categoria do Cartão**: A maioria esmagadora dos clientes possui o cartão "Blue".
* **Nível de Escolaridade**: A maior parte dos clientes possui graduação ou ensino médio.
* **Status de Churn**: O conjunto de dados é desbalanceado, com uma proporção muito maior de clientes ativos do que de clientes que cancelaram a conta (cerca de 16% de churn).

### 2. Pré-processamento de Dados

Antes de treinar os modelos, os dados passaram por um pré-processamento, que incluiu:

* **Codificação da Variável Alvo**: A coluna `Attrition_Flag` foi convertida para um formato numérico.
* **One-Hot Encoding**: As variáveis categóricas (como gênero, escolaridade, etc.) foram transformadas em variáveis dummy para serem utilizadas pelos algoritmos de machine learning.
* **Balanceamento de Classes (SMOTE)**: Para lidar com o desbalanceamento de classes, foi aplicada a técnica SMOTE (*Synthetic Minority Over-sampling Technique*), que cria novas amostras sintéticas da classe minoritária.

### 3. Modelagem Preditiva

Foram treinados e avaliados três modelos de classificação:

* **Random Forest**
* **XGBoost**
* **AdaBoost**

A performance dos modelos foi avaliada utilizando as seguintes métricas:

* **Acurácia**: Proporção de previsões corretas.
* **Relatório de Classificação**: Inclui precisão, recall e F1-score para cada classe.
* **Matriz de Confusão**: Mostra os erros e acertos do modelo.

### 4. Avaliação e Resultados

Os resultados dos modelos foram os seguintes:

* **Random Forest**: Atingiu uma acurácia de aproximadamente **94.9%**.
* **XGBoost**: Apresentou a melhor performance, com uma acurácia de cerca de **96.3%**.
* **AdaBoost**: O modelo foi treinado, mas sua avaliação detalhada não foi o foco principal.

## Como Executar o Projeto

### Pré-requisitos

* Python 3.x
* Jupyter Notebook ou Jupyter Lab
* As seguintes bibliotecas Python:
    * pandas
    * numpy
    * matplotlib
    * seaborn
    * plotly
    * scikit-learn
    * imbalanced-learn
    * xgboost
    * shap

### Instalação

Você pode instalar as dependências com o pip:

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn imbalanced-learn xgboost shap
```

### Execução

1.  Clone este repositório.
2.  Abra o Jupyter Notebook `Bank_Churners.ipynb`.
3.  Execute as células do notebook para reproduzir a análise e os resultados.

## Conclusões

* A análise exploratória forneceu insights valiosos sobre o perfil dos clientes.
* Os modelos de machine learning, especialmente o XGBoost, mostraram-se muito eficazes na previsão de churn.
* A análise de importância das características (com SHAP) pode ser utilizada para entender os principais fatores que influenciam o churn, permitindo a criação de estratégias de retenção mais direcionadas.

## Contribuição

Contribuições para este projeto são bem-vindas. Para contribuir:

1.  Faça um "fork" do projeto.
2.  Crie uma nova "branch" (`git checkout -b feature/nova-feature`).
3.  Faça o "commit" de suas alterações (`git commit -m 'Adiciona nova feature'`).
4.  Faça o "push" para a "branch" (`git push origin feature/nova-feature`).
5.  Abra um "Pull Request".
