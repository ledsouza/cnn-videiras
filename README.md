# Classificação de Videiras

![Static Badge](https://img.shields.io/badge/Status-Finalizado-green)

## Descrição

Este projeto visa construir um modelo de Machine Learning capaz de classificar imagens de videiras em quatro classes: BlackMeasles, BlackRot, HealthyGrapes e LeafBlight. O modelo utiliza uma rede neural convolucional (CNN) pré-treinada com o dataset ImageNet e técnicas de aumento de dados para melhorar a generalização.

## Tecnologias Utilizadas

- Python
- TensorFlow
- Keras
- PIL
- Plotly

## Descrição Detalhada

O notebook `classificacao_videiras.ipynb` detalha o processo de construção, treinamento e avaliação do modelo. Abaixo, um resumo das etapas:

1. **Carregamento dos Dados:** As imagens das videiras são carregadas a partir de um diretório local, organizado em subpastas correspondentes às classes.
2. **Verificação dos Dados:** O número de imagens por classe e as dimensões das imagens são verificados para garantir a consistência do dataset.
3. **Preparo dos Dados:** O dataset é dividido em conjuntos de treino e validação, com 80% das imagens para treino e 20% para validação.
4. **Criação do Modelo:** Um modelo sequencial é criado utilizando a arquitetura InceptionV3 pré-treinada. A camada de classificação original é substituída por camadas densas para se adequar ao problema de classificação de quatro classes.
5. **Treinamento do Modelo:** O modelo é treinado com o conjunto de treino, utilizando o otimizador Adam e a função de perda `sparse_categorical_crossentropy`. A acurácia é utilizada como métrica de avaliação.
6. **Visualização dos Resultados:** Os resultados do treinamento são visualizados em gráficos, mostrando a evolução da acurácia e da perda ao longo das épocas.
7. **Aumento de Dados:** Técnicas de aumento de dados, como rotações, flips e zoom aleatórios, são aplicadas às imagens de treino para aumentar a diversidade do dataset e melhorar a generalização do modelo.
8. **Critério de Parada:** Um callback é implementado para interromper o treinamento quando a acurácia do conjunto de treino atingir 93%.
9. **Salvamento do Modelo:** O modelo treinado é salvo em formato `.keras` para uso posterior.
10. **Quantização do Modelo:** O modelo é quantizado para reduzir seu tamanho e melhorar a performance em dispositivos com recursos limitados. O modelo quantizado é salvo em formato `.tflite`.

## Resultados

O modelo treinado com aumento de dados e critério de parada alcançou uma acurácia de validação acima de 90%. A quantização do modelo resultou em uma redução significativa do seu tamanho, sem comprometer a acurácia.
