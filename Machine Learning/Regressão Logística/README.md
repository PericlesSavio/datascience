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

# Carrega os dados
df = pd.read_csv("data.csv")

# Divide os dados em atributos e rótulo
X = df.drop("label", axis=1)
y = df["label"]

# Divide os dados em treino e teste
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Cria o modelo de regressão logística
clf = LogisticRegression()

# Treina o modelo com os dados de treino
clf.fit(X_train, y_train)

# Realiza as previsões com os dados de teste
y_pred = clf.predict(X_test)

# Avalia o desempenho do modelo
score = clf.score(X_test, y_test)
print("Acurácia: ", score)
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
