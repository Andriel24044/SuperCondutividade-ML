# SuperCondutividade-ML
## Motivação
No presente trabalho, utilizou-se uma base de dados de supercondutividade com o intuito de estudar o comportamento dos materiais supercondutores em elevados níveis de temperatura e, assim, estimar seu valor crítico. Este dataset encontra-se presente no repositório [1].

## Atributos
Os atributos utilizados para a análise posterior foram determinados com base no método de seleção de atributos pelo fator de inflação de variância (VIF). Inicialmente, eram compostos por 81 atributos, que foram reduzidos a 29 a partir deste método. Abaixo seguem os atributos selecionados:

[colar os atributos]

## Target
[adicionar]

## Estrutura do projeto 
Introdução
- Dataset
- Tratamento de dados

Modelos
- BaseLine
- Lineares
  - Linear
  - Bayesiano
- K-NN
- Floresta aleatória

Referências

## Guia
[explicar o código]

## Abordagem das ferramentas

### Optuna
Optuna é um framework agnóstico (não está associado a nenhuma tecnologia em específico). Dada essa liberdade, vem sendo utilizado em diversos meios para a otimização de hiperparâmetros, permitindo um melhor desempenho do modelo a ser desenvolvido. Buscando esta 

### Fator de Inflação de Variância (VIF)
O VIF, uma importante ferramenta para análise de multicolinearidade, é utilizado para filtrar grupos de atributos que possuem alta colinearidade, impactando na performance do modelo e no erro posterior. Sendo assim, essas variáveis são eliminadas.

### BaseLine

### Modelo Linear

### Modelo Bayesiano

### K-NN

### Floresta aleatória

## Referências
[1] UCI Machine Learning Repository. Disponível em: [url](<https://archive.ics.uci.edu/dataset/464/superconductivty+data>) <br>
[2] Optuna - A hyperparameter optimization framework. Disponível em: [url](<https://optuna.org/>)  <br>
[3] YEMULWAR, S. Feature Selection Techniques. Disponível em: [url](<https://medium.com/analytics-vidhya/feature-selection-techniques-2614b3b7efcd>) <br>
[4] PRAKASH, P. Understanding Baseline Models in Machine Learning. Disponível em: [url](<https://medium.com/@preethi_prakash/understanding-baseline-models-in-machine-learning-3ed94f03d645>)<br>
[5] KOEHRSEN, W. Introduction to Bayesian Linear Regression. Disponível em: [url](<https://towardsdatascience.com/introduction-to-bayesian-linear-regression-e66e60791ea7>) <br>
[6] JOSÉ, I. KNN (K-Nearest Neighbors) #1. Disponível em: [url](<https://medium.com/brasil-ai/knn-k-nearest-neighbors-1-e140c82e9c4e>)
[7] PESSANHA, C. Random Forest: como funciona um dos algoritmos mais populares de ML. Disponível em: [url](<https://medium.com/cinthiabpessanha/random-forest-como-funciona-um-dos-algoritmos-mais-populares-de-ml-cc1b8a58b3b4>)

‌

‌

‌

‌
