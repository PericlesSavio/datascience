# Regressão Logística

A regressão logística é um método estatístico utilizado para modelar e prever a probabilidade de ocorrência de um evento binário, ou seja, quando existem apenas dois resultados possíveis. É usado para modelar relacionamentos entre uma variável dependente $y$ e uma ou mais variáveis independentes ($x1$, $x2$, $x3$, ...). Usa a função logística (também chamada de função sigmoide) para modelar uma variável dependente binária. A função logística é uma curva em forma de S que mapeia qualquer valor de entrada para um valor entre $0$ e $1$. Isso permite que o modelo de regressão logística preveja a probabilidade de ocorrência do evento binário.

A equação geral da regressão logística é dada por:

$$p(y=1|x) = 1 / (1 + e^(-x))$$

Exemplo do gráfico:
![](arquivos/curva_reglog.png "Gráfico de exemplo de uma curva de regressão logística ajustada aos dados. A curva mostra a probabilidade de passar em um exame (variável dependente binária) versus horas de estudo (variável independente escalar).")

### Exemplo em Python
```python
import pandas as pd
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split

# criando dataset hipotético
dados = {'Anos_Fumando': [0, 20, 0, 25, 10, 35, 0, 45, 5],
          'Cancer': [0, 1, 0, 1, 1, 1, 0, 1, 0]}
df = pd.DataFrame(dados)

# dividindo os dados em treino e teste
X = df[['Anos_Fumando']]
y = df['Cancer']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# criando o modelo de regressão logística
log_reg = LogisticRegression()
log_reg.fit(X_train, y_train)

# fazendo previsões com os dados de teste
y_pred = log_reg.predict(X_test)

# avaliando o desempenho do modelo
score = log_reg.score(X_test, y_test)
print(score)
```

### Características
- É usada para prever a probabilidade de ocorrência de um evento binário.
- Pode ser usada para lidar com problemas de classificação.
- É capaz de lidar com múltiplas variáveis independentes.
- Pode ser usada para lidar com variáveis categóricas e numéricas.
- Pode ser usada para analisar a relação entre as variáveis independentes e dependentes.


### Referências

- https://aws.amazon.com/pt/what-is/logistic-regression/
- https://www.tibco.com/pt-br/reference-center/what-is-logistic-regression
- https://edisciplinas.usp.br/pluginfile.php/3769787/mod_resource/content/1/09_RegressaoLogistica.pdf
- https://monografias.ufma.br/jspui/bitstream/123456789/3572/1/LEANDRO-GONZALEZ.pdf
- https://www.youtube.com/watch?v=yIYKR4sgzI8
