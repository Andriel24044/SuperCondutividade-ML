# Arquivos adicionais - Optuna

Esta pasta contém os arquivos gerados pelo Optuna na otimização dos hiperparâmetros. A seguir, explicita-se o que cada pasta e arquivo representa

- Primeiro Dataset: representa o dataset principal → arquivo 'train.csv' do <i>Superconductivity</i>.
    - `knn-apenas-primeiro.db`: seleção de hiperparâmetros do optuna para o modelo K-nn com o primeiro dataset
    - `random_forest_apenas_primeiro.db`: seleção de hiperparâmetros do optuna para o modelo de floresta aleatória com o primeiro dataset

- Segundo dataset: representa o segundo dataset → arquivo 'unique-m.csv' do <i>Superconductivity</i>.
    - `knn-superconduct-unique-m.db`: seleção de hiperparâmetros do optuna para o modelo K-nn com o segundo dataset
    - `random_forest_supercond_unique_m.db`: seleção de hiperparâmetros do optuna para o modelo de floresta aleatória com o segundo dataset

  - Terceiro dataset: representa a junção de ambos os datasets → VIF no primeiro dataset + segundo dataset (original)
      - `superconductivty_ambos_datasets`: seleção de hiperparâmetros do optuna para o modelo K-nn com o terceiro dataset
      - `random_forest_supercond_ambos`: seleção de hiperparâmetros do optuna para o modelo de floresta aleatória com o terceiro dataset
