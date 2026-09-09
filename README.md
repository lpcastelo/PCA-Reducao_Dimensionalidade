# PCA-Reducao_Dimensionalidade
Aqui você irá encontrar a atividade do módulo 37 do curso de Cientista de Dados da Ebac.

A atividade consiste em aplicar a técnica de redução de dimensionalidade PCA (Principal Component Analysis) e avaliar seu impacto no desempenho de modelos de Machine Learning utilizados para prever quais clientes estão mais propensos a realizar compras em uma loja online.

Durante a atividade serão abordados temas como:

Redução de dimensionalidade com PCA (Principal Component Analysis)
Regressão Logística
Modelo Random Forest
Classificação supervisionada
Comparação de desempenho com e sem PCA
Avaliação do impacto da redução de dimensionalidade nos modelos

O objetivo é compreender como o PCA pode ser utilizado para reduzir a quantidade de variáveis de um conjunto de dados, simplificando a modelagem e analisando seus efeitos sobre a capacidade preditiva dos algoritmos de Machine Learning.

## Dados

Base `marketing_campaign.csv` (campanha de marketing de e-commerce), tratada com: imputação de `Income` pela média, remoção de outliers de nascimento e de renda (valor de 666.666 descartado), correção de categorias inconsistentes em `Marital_Status` (`Alone`→`Single`, remoção de `Absurd`/`YOLO`), remoção de `Recency` e `Complain` por baixa correlação com o alvo. Variável alvo: `WebPurchases`.

## Etapas realizadas

Após o tratamento, as variáveis categóricas foram codificadas (`OrdinalEncoder` para `Education`, `OneHotEncoder` para `Marital_Status`) e as numéricas padronizadas (`StandardScaler`), seguido de PCA retendo 98% da variância explicada para reduzir a dimensionalidade gerada pelo one-hot encoding.

## Resultados

| Modelo | Acurácia | AUC |
|---|---|---|
| Regressão Logística (com PCA) | 87% | 0,87 |
| Random Forest (com PCA) | 89% | 0,89 |

O Random Forest apresentou o melhor desempenho geral, com maior recall para a classe positiva (94% vs. 86% da Regressão Logística), ainda que com precisão levemente inferior.

## Tecnologias

- Python, pandas, numpy
- scikit-learn (PCA, ColumnTransformer, OneHotEncoder, OrdinalEncoder, RandomForestClassifier, LogisticRegression)
- matplotlib, seaborn

## Como executar

1. Instale as dependências: `pip install pandas numpy scikit-learn matplotlib seaborn`.
2. Coloque `marketing_campaign.csv` no mesmo diretório do notebook.
3. Execute `Profissao Cientista de Dados M37 Projeto.ipynb` em ordem.
