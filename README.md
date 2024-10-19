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
O modelo baseline atua como um parâmetro para avaliar a eficiência de modelos mais complexos, sendo composto pela média ou mediana da variável alvo no caso de problemas de regressão.
### Modelo Linear
O modelo linear baseia-se na predição estatística através de métodos de aproximação, como o de mínimos quadrados. Sua principal característica é a geração de funções polinomiais que tentam representar a relação entre variáveis independentes e a variável dependente. Os coeficientes do modelo são obtidos minimizando a soma dos quadrados das diferenças entre os valores observados e os valores preditos.

### Modelo Bayesiano
  Ao contrário do modelo linear tradicional, a regressão bayesiana utiliza o Teorema de Bayes para estimar os parâmetros do modelo. Nessa abordagem, os parâmetros são tratados como variáveis aleatórias, e as distribuições a priori são definidas com base em conhecimentos ou suposições anteriores. A partir dos dados observados, a distribuição posterior dos parâmetros é calculada, levando em consideração tanto a informação prévia quanto os dados disponíveis.

### K-NN
O algoritmo K-NN (K-Nearest Neighbors) estima a classe ou valor de um elemento desconhecido com base na distância entre os dados. Para isso, ele considera os K elementos mais próximos, um número que deve ser definido pelo usuário. Diferentes técnicas podem ser usadas para calcular a distância, como a Euclidiana, Manhattan, Minkowski ou Ponderada. Por fim, o algoritmo analisa esses vizinhos mais próximos e faz a estimativa com base na proximidade entre eles.
### Floresta aleatória
- #### Árvore de Decisão
  O algoritmo de árvore de decisão organiza os dados em uma estrutura de árvore, o que facilita a análise e a interpretação dos atributos. No entanto, para dados mais complexos, é comum ocorrer overfitting, onde o modelo se ajusta muito bem aos dados de treino, mas não generaliza adequadamente para novos dados.

Para evitar o overfitting, o algoritmo de floresta aleatória se mostra eficiente. Ele combina várias pequenas árvores de decisão, onde cada árvore é treinada com um subconjunto aleatório de dados e de atributos. Esse processo, cria um modelo mais robusto e menos suscetível ao overfitting, pois as árvores trabalham juntas para melhorar a precisão do modelo. Ao utilizar pequenas amostras de dados em cada árvore, a floresta aleatória otimiza a função de predição e aumenta a sua capacidade de generalização.
## Referências
[1] UCI Machine Learning Repository. Disponível em: [url](<https://archive.ics.uci.edu/dataset/464/superconductivty+data>) <br>
[2] Optuna - A hyperparameter optimization framework. Disponível em: [url](<https://optuna.org/>)  <br>
[3] YEMULWAR, S. Feature Selection Techniques. Disponível em: [url](<https://medium.com/analytics-vidhya/feature-selection-techniques-2614b3b7efcd>) <br>
[4] PRAKASH, P. Understanding Baseline Models in Machine Learning. Disponível em: [url](<https://medium.com/@preethi_prakash/understanding-baseline-models-in-machine-learning-3ed94f03d645>)<br>
[5] KOEHRSEN, W. Introduction to Bayesian Linear Regression. Disponível em: [url](<https://towardsdatascience.com/introduction-to-bayesian-linear-regression-e66e60791ea7>) <br>
[6] JOSÉ, I. KNN (K-Nearest Neighbors) #1. Disponível em: [url](<https://medium.com/brasil-ai/knn-k-nearest-neighbors-1-e140c82e9c4e>) <br>
[7] PESSANHA, C. Random Forest: como funciona um dos algoritmos mais populares de ML. Disponível em: [url](<https://medium.com/cinthiabpessanha/random-forest-como-funciona-um-dos-algoritmos-mais-populares-de-ml-cc1b8a58b3b4>)

‌

‌

‌

‌
