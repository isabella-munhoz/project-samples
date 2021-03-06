# Descrição do problema

Nesse folder, temos a cross-validação de um modelo para a resolução de um problema de classificação de imagens.
<br> O dataset é composto por imagens de folhas de videira saudáveis (classe 0) e folhas que apresentam <i>black rot</i> (classe 1). <i>Black rot</i> é um nome genérico usado para descrever uma doença que gera manchas nas folhas; essa doença pode ser causada pela ação de fungos e/ou bactérias. </br>
<br> O dataset está disponível no Kaggle, através do link: <a>https://www.kaggle.com/piyushmishra1999/plantvillage-grape</a>.

<br> Nota: No dados originais, encontramos imagens de folhas de videiras acometidas por outras doenças. Esse estudo, contudo, utilizou somente as imagens das folhas saudáveis e das folhas acometidas por <i>black rot</i>.

# Descrição do dataset

O dataset usado é composto por 1603 imagens, das quais 423 são pertencentes à classe 0 (saudável) e 1180 pertencem à classe 1 (<i>black rot</i>).

# Descrição do modelo utilizado

O modelo consiste em:
* Camada Convolucional: 50 filtros (5,5)
* Camada Bacth Normalization
* Camada Max Pooling: (2,2)
* Camada Convolucional: 32 filtros (5,5)
* Camada Bacth Normalization
* Camada Max Pooling: (2,2)
* Camada Flatten
* Camada Densa: 128 neurônios
* Camada Dropout: 20%
* Camada Densa: 128 neurônios
* Camada Dropout: 20%
* Camada Densa (saída): 1 neurônio

Os hiperparâmetros selecionados foram:
* Função custo: binary crossentropy
* Otimizador: Adam (com as configurações <i>default</i> do keras)
* Batch Size: 50
* Epochs: 25
* Class weights: classe 0 -> 1.89479 | classe 1 -> 0.67923
* Threshold usado nos dados de validação: 0.5

# Métricas avaliadas

AUC, accuracy, precision, recall, F1 score.

# Considerações

O modelo apresentou ótimo resultado em todas as métricas avaliadas (>95%, em média, para todas as métricas). Como o dataset é desbalanceado, o uso do <i>class_weight</i> durante o treinamento foi diferencial para atingir os resultados satisfatórios.

