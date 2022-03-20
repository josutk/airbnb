# airbnb

1) Como foi a definição da sua estratégia de modelagem?

Devido os dados de revisão se tratarem de diversos idiomas, foi escolhi um modelo multilingual baseado na arquitetura dos transformers, aplicando no final uma camada linear para para poder realizar o valor de regressão, o modelo foi treinado com 3 epocas e 2 folds dos dados dividios entre treino e teste devido o tempo de GPU que eu tinha disponivel para utilizar. A arquitetura de modelagem aplicada foi o Bert, o distill bert também foi testado mas não obteve resultados tão bons quanto o bert durante a validação do modelo.


2) Como foi definida a função de custo utilizada?

Por se tratar de um dado usou-se a MSELoss.

3) Qual foi o critério utilizado na seleção do modelo final?

O dado foi splitado utilizando kfolds duas vezes, onde os dados foram segmentados em treino e teste durante algumas epocas
Foram observadas o loss de validação do modelo, o modelo que obteve menor loss foi utilizado para as predições.

4) Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método?

O valor da função de loss durante. Pois com um baixo valor da função de loss utilizando o MSE conseguimos avaliar o modelo de regressão e temos a informação do quanto

5) Quais evidências possui de que seu modelo é suficientemente bom?

Loss de validação de loss e os valores mse no notebook de avaliação demonstra que 1000 amostras selecionadas do dataset de treino tem um MSE de 0.10 então o modelo conseguiu se adaptar bem aos valores originais, porém o dado tem uma média alta, o que reflete geralmente avaliações positivas então precisariamos de um dataset mais bem distribuido com avaliações com pontuações mais baixas permitindo assim uma representação com modelagem mais próxima de uma ambiente real
