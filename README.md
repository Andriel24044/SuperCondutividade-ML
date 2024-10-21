# SuperCondutividade-ML

## Motivação
No presente trabalho, utilizou-se uma base de dados de supercondutividade com o intuito de estudar o comportamento dos materiais supercondutores em elevados níveis de temperatura e, assim, estimar seu valor crítico. Este dataset encontra-se presente no repositório [1](#ref1).

## Atributos
Os atributos utilizados para a análise posterior foram determinados com base no método de seleção de atributos pelo fator de inflação de variância (VIF). Inicialmente, eram compostos por 81 atributos, que foram reduzidos a 29 a partir deste método. Abaixo seguem os atributos selecionados:

| **Atributo**                       | **Significado**                                                                                              |
|------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **mean_atomic_mass**               | Média da massa atômica dos elementos.                                                                         |
| **wtd_range_atomic_mass**          | Intervalo ponderado da massa atômica.                                                                         |
| **std_atomic_mass**                | Desvio padrão da massa atômica.                                                                                 |
| **gmean_fie**                      | Média geométrica da energia de ionização (fie = First Ionization Energy).                                      |
| **wtd_range_fie**                  | Intervalo ponderado da energia de ionização.                                                                   |
| **mean_atomic_radius**             | Média do raio atômico dos elementos.                                                                          |
| **wtd_range_atomic_radius**        | Intervalo ponderado do raio atômico.                                                                          |
| **std_atomic_radius**              | Desvio padrão do raio atômico.                                                                                 |
| **wtd_entropy_Density**            | Entropia ponderada da densidade dos elementos.                                                                 |
| **range_Density**                  | Intervalo da densidade dos elementos.                                                                          |
| **wtd_range_Density**              | Intervalo ponderado da densidade.                                                                              |
| **mean_ElectronAffinity**          | Média da afinidade eletrônica dos elementos (energia liberada ao adicionar um elétron).                        |
| **wtd_gmean_ElectronAffinity**     | Média geométrica ponderada da afinidade eletrônica.                                                            |
| **wtd_entropy_ElectronAffinity**   | Entropia ponderada da afinidade eletrônica.                                                                    |
| **range_ElectronAffinity**         | Intervalo da afinidade eletrônica.                                                                             |
| **wtd_std_ElectronAffinity**       | Desvio padrão ponderado da afinidade eletrônica.                                                               |
| **gmean_FusionHeat**               | Média geométrica do calor de fusão dos elementos.                                                              |
| **range_FusionHeat**               | Intervalo do calor de fusão.                                                                                   |
| **wtd_range_FusionHeat**           | Intervalo ponderado do calor de fusão.                                                                         |
| **wtd_std_FusionHeat**             | Desvio padrão ponderado do calor de fusão.                                                                     |
| **mean_ThermalConductivity**       | Média da condutividade térmica dos elementos.                                                                  |
| **wtd_gmean_ThermalConductivity**  | Média geométrica ponderada da condutividade térmica.                                                           |
| **entropy_ThermalConductivity**    | Entropia da condutividade térmica.                                                                             |
| **wtd_entropy_ThermalConductivity**| Entropia ponderada da condutividade térmica.                                                                   |
| **wtd_range_ThermalConductivity**  | Intervalo ponderado da condutividade térmica.                                                                  |
| **gmean_Valence**                  | Média geométrica da valência (número de elétrons de valência).                                                 |
| **range_Valence**                  | Intervalo do número de elétrons de valência.                                                                   |
| **wtd_range_Valence**              | Intervalo ponderado do número de elétrons de valência.                                                         |
| **wtd_std_Valence**                | Desvio padrão ponderado do número de elétrons de valência.                                                     |

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
1. Importação dos Dados

Primeiramente, importou-se o dataset da base de dados.

```
from ucimlrepo import fetch_ucirepo 

superconductivty_data = fetch_ucirepo(id=464) 
```

2. Tratamento de Dados

Após a importação, foi necessário tratar os dados para evitar casos de multicolinearidade e, para isso, utilizou-se o algoritmo VIF para eliminar variáveis altamente correlacionadas.
```
def selecao_vif(df_atributos, limiar_vif):
...
    return df

limiar_VIF = 10

X_modificado = selecao_vif(X, limiar_VIF)
```

3. Otimização de Hiperparâmetros com Optuna

Optuna é uma ferramenta útil para otimizar hiperparâmetros de modelos.

```
from optuna import create_study

NOME_DO_ESTUDO = "supercondutividade-knn-dataset1"

objeto_de_estudo = create_study(
    direction="minimize",
    study_name=NOME_DO_ESTUDO,
    storage=f"sqlite:///{NOME_DO_ESTUDO}.db",
    load_if_exists=True,
)
```

4. Avaliação com RMSE

Após a otimização, os modelos são avaliados com base no erro quadrático médio (RMSE).

```
from sklearn.metrics import mean_squared_error

RMSE_knn = mean_squared_error(y_teste, y_previsto) ** (1/2)
```

5. Comparação dos Resultados

Os resultados de diferentes modelos foram comparados através dos RMSEs.


## Abordagem das ferramentas

### Optuna
Optuna é um framework agnóstico (não está associado a nenhuma tecnologia em específico). Dada essa liberdade, vem sendo utilizado em diversos meios para a otimização de hiperparâmetros, permitindo um melhor desempenho do modelo a ser desenvolvido. Através de uma abordagem baseada em busca adaptativa, o Optuna ajusta automaticamente os parâmetros do modelo, permitindo alcançar um melhor desempenho.[2](#ref2)

### Fator de Inflação de Variância (VIF)
O VIF (Variance Inflation Factor) é uma importante ferramenta para análise de multicolinearidade, utilizada para identificar e filtrar grupos de atributos que apresentam alta colinearidade. A presença de multicolinearidade pode prejudicar a performance do modelo, dificultando a interpretação dos coeficientes e levando a um aumento no erro posterior. Dessa forma, as variáveis que apresentam um VIF elevado são eliminadas ou ajustadas, visando melhorar a robustez e a precisão do modelo.[3](#ref3)

### BaseLine
O modelo baseline atua como um parâmetro para avaliar a eficiência de modelos mais complexos, sendo composto pela média ou mediana da variável alvo no caso de problemas de regressão.[4](#ref4)
### Modelo Linear
O modelo linear baseia-se na predição estatística através de métodos de aproximação, como o de mínimos quadrados. Sua principal característica é a geração de funções polinomiais que tentam representar a relação entre variáveis independentes e a variável dependente. Os coeficientes do modelo são obtidos minimizando a soma dos quadrados das diferenças entre os valores observados e os valores preditos.[5](#ref5)

### Modelo Bayesiano
  Ao contrário do modelo linear tradicional, a regressão bayesiana utiliza o Teorema de Bayes para estimar os parâmetros do modelo. Nessa abordagem, os parâmetros são tratados como variáveis aleatórias, e as distribuições a priori são definidas com base em conhecimentos ou suposições anteriores. A partir dos dados observados, a distribuição posterior dos parâmetros é calculada, levando em consideração tanto a informação prévia quanto os dados disponíveis.[5](#ref5)

### K-NN
O algoritmo K-NN (K-Nearest Neighbors) estima a classe ou valor de um elemento desconhecido com base na distância entre os dados. Para isso, ele considera os K elementos mais próximos, um número que deve ser definido pelo usuário. Diferentes técnicas podem ser usadas para calcular a distância, como a Euclidiana, Manhattan, Minkowski ou Ponderada. Por fim, o algoritmo analisa esses vizinhos mais próximos e faz a estimativa com base na proximidade entre eles.[6](#ref6)
### Floresta aleatória
- #### Árvore de Decisão
  O algoritmo de árvore de decisão organiza os dados em uma estrutura de árvore, o que facilita a análise e a interpretação dos atributos. No entanto, para dados mais complexos, é comum ocorrer overfitting, onde o modelo se ajusta muito bem aos dados de treino, mas não generaliza adequadamente para novos dados.

Para evitar o overfitting, o algoritmo de floresta aleatória se mostra eficiente. Ele combina várias pequenas árvores de decisão, onde cada árvore é treinada com um subconjunto aleatório de dados e de atributos. Esse processo, cria um modelo mais robusto e menos suscetível ao overfitting, pois as árvores trabalham juntas para melhorar a precisão do modelo. Ao utilizar pequenas amostras de dados em cada árvore, a floresta aleatória otimiza a função de predição e aumenta a sua capacidade de generalização.[7](#ref7)

## RMSE
A RMSE (Root Mean Square Error) é uma métrica utilizada para avaliar o desempenho de um modelo de regressão. Ela é calculada pela raiz quadrada da média dos quadrados dos erros, oferecendo uma medida direta da diferença entre os valores previstos e os valores observados. Como a RMSE é sensível a outliers, deve-se ter cuidado, pois grandes desvios podem influenciar significativamente o resultado.[8](#ref8)

## Referências
[1]<a id="ref1"></a>UCI Machine Learning Repository. Disponível em: [url](<https://archive.ics.uci.edu/dataset/464/superconductivty+data>) <br>
[2]<a id="ref2"></a>Optuna - A hyperparameter optimization framework. Disponível em: [url](<https://optuna.org/>)  <br>
[3]<a id="ref3"></a> YEMULWAR, S. Feature Selection Techniques. Disponível em: [url](<https://medium.com/analytics-vidhya/feature-selection-techniques-2614b3b7efcd>) <br>
[4]<a id="ref4"></a> PRAKASH, P. Understanding Baseline Models in Machine Learning. Disponível em: [url](<https://medium.com/@preethi_prakash/understanding-baseline-models-in-machine-learning-3ed94f03d645>)<br>
[5]<a id="ref5"></a> KOEHRSEN, W. Introduction to Bayesian Linear Regression. Disponível em: [url](<https://towardsdatascience.com/introduction-to-bayesian-linear-regression-e66e60791ea7>) <br>
[6]<a id="ref6"></a> JOSÉ, I. KNN (K-Nearest Neighbors) #1. Disponível em: [url](<https://medium.com/brasil-ai/knn-k-nearest-neighbors-1-e140c82e9c4e>) <br>
[7]<a id="ref7"></a> PESSANHA, C. Random Forest: como funciona um dos algoritmos mais populares de ML. Disponível em: [url](<https://medium.com/cinthiabpessanha/random-forest-como-funciona-um-dos-algoritmos-mais-populares-de-ml-cc1b8a58b3b4>)<br>
[8]<a id="ref8"></a>FILHO, M. RMSE (Raiz Do Erro Quadrático Médio) Em Machine Learning. Disponível em: [url](<https://mariofilho.com/rmse-raiz-do-erro-quadratico-medio-em-machine-learning/>)

‌
‌

‌

‌

‌
