# Regressão Linear
Uma análise de regressão gera uma equação para descrever a relação estatística entre um ou mais preditores e a variável de resposta e para predizer novas observações. A regressão linear normalmente usa o método de estimativa de mínimos quadrados ordinários que deriva a equação minimizando a soma dos resíduos quadrados.

### Conceitos
##### R²
Coeficiente de determinação, coeficiente de ajuste ou coeficiente de explicação. Quanto mais alto o valor de **R²** melhor o modelo ajusta seus dados. O valor de **R²** está sempre entre 0 e 100%. Indica o percentual de variância da variável Y que é devido ao comportamento de variação conjunta das variáveis explicativas X. O **R²** sempre aumenta quando você adiciona mais preditores a um modelo.   Por exemplo, o melhor modelo de cinco preditores terá sempre um **R²** que é pelo menos tão elevado quanto o melhor modelo de quatro preditores.

##### Modelos lineares generalizados (GLMs, na sigla em inglês)
São uma classe de modelos estatísticos que permitem uma ampla variedade de distribuições para a variável dependente. Eles são uma generalização dos modelos lineares tradicionais, como a regressão linear, e permitem lidar com dados que não sejam normalmente distribuídos, por exemplo, dados com distribuição binomial ou Poisson.

##### Teste T
Ele é usado para testar a significância individual dos parâmetros do modelo, ou seja, para determinar se cada variável independente tem um efeito significativo na variável dependente, controlando os efeitos das outras variáveis independentes no modelo.

Se o valor absoluto do teste t for maior que um certo valor crítico, geralmente determinado pelo nível de significância e pelos graus de liberdade, pode-se concluir que o parâmetro é significativo e contribui para explicar a variabilidade da variável dependente.

Quando há multicolinearidade, o teste t pode apresentar resultados enganosos, indicando que uma variável não é significativa quando na verdade ela é importante no modelo. Nesses casos, outras medidas, como a análise de tolerância e o fator de inflação de variância, podem ser utilizadas para diagnosticar a multicolinearidade e avaliar a importância das variáveis independentes.

##### Teste F
É usado para avaliar se um conjunto de variáveis independentes, também chamadas de preditoras, tem um efeito significativo sobre a variável dependente em um modelo de regressão linear. O teste compara a variabilidade explicada pelo modelo (também chamada de soma de quadrados de regressão) com a variabilidade não explicada (também chamada de soma de quadrados residual) para determinar se o modelo é significativo. O valor F é a relação entre a variabilidade explicada e não explicada, e a significância é avaliada usando um valor p.

##### ANOVA (Analysis of Variance)
É uma técnica estatística que permite comparar a variância entre as médias de dois ou mais grupos. Na regressão linear, a ANOVA é utilizada para testar a hipótese de que pelo menos uma das variáveis independentes tem um efeito significativo na variável dependente.

##### Tolerância
É uma medida de detecção de multicolinearidade entre variáveis independentes. Ela é definida como a proporção da variação de uma variável independente que não é explicada pelas outras variáveis independentes no modelo.

$$Tolerância = 1 - R²$$

Uma tolerância próxima de zero indica uma alta multicolinearidade, o que significa que a variável está altamente correlacionada com outras variáveis independentes e pode não ser necessária para o modelo. Por outro lado, uma tolerância próxima de um indica que a variável está pouco correlacionada com as outras variáveis independentes e é importante para o modelo.

##### Fator de inflação da variância (VIF)
O VIF é uma medida numérica da multicolinearidade que mede o grau em que a variância do coeficiente de regressão é aumentada em relação a uma situação em que as variáveis independentes são ortogonais.

$$VIF = 1/Tolerância$$

Onde varia de 1 até ∞, sendo que quanto mais baixo o VIF, menor a multicolinearidade.

##### Multicolinearidade
É um fenômeno em que duas ou mais variáveis independentes em um modelo de regressão linear estão altamente correlacionadas entre si, o que pode levar a problemas na interpretação dos coeficientes de regressão e na precisão das estimativas dos parâmetros do modelo.

A multicolinearidade pode levar a estimativas imprecisas ou instáveis dos coeficientes de regressão, dificultando a identificação das variáveis independentes mais importantes para o modelo. Além disso, pode aumentar o erro padrão dos coeficientes, reduzir a significância estatística das variáveis independentes e produzir valores de coeficientes que têm o sinal oposto do que se espera teoricamente.

Para detectar a multicolinearidade, geralmente se usa o coeficiente de correlação entre as variáveis independentes e a análise da matriz de correlação. Quando a multicolinearidade é detectada, algumas soluções incluem a remoção de uma ou mais variáveis independentes altamente correlacionadas ou a combinação delas em uma única variável.


### Em Python

```python
import statsmodels.formula.api as smf
import pandas as pd

# Carregando o dataset
data = pd.read_csv("dados.csv")

# Definindo a fórmula para a análise de regressão
formula = 'Y ~ X'

# Executando a análise de regressão
model = smf.ols(formula, data=data).fit()

# Exibindo os resultados
print(model.summary())
```

```python
import pandas as pd
from sklearn.linear_model import LinearRegression

# Carregando o dataset
df = pd.read_csv("dados.csv")

# Selecionando as variáveis independentes (X) e a variável dependente (y)
X = df[['var1', 'var2']]
y = df['var_dependente']

# Instanciando o modelo de regressão linear
reg = LinearRegression().fit(X, y)

# Realizando a previsão
previsao = reg.predict([[valor1, valor2]])
print(previsao)
```

### Referências
* https://support.minitab.com/pt-br/minitab/20/help-and-how-to/statistical-modeling/regression/supporting-topics/basics/types-of-regression-analyses/
* https://blog.minitab.com/pt/entendendo-analise-de-variancia-anova-e-o-teste-f
* https://medium.com/data-hackers/interpretando-ml-modelos-lineares-bccbd9f5d6a0
* http://leg.ufpr.br/~lucambio/GLM/GLM.html
* https://geokrigagem.com.br/analise-de-variancia-anova-e-regressao-linear-multipla-parte-1/
* https://edisciplinas.usp.br/pluginfile.php/2340848/mod_resource/content/0/Mayara_Multicolinearidade.pdf
* https://www4.eco.unicamp.br/docentes/gori/images/arquivos/EconometriaI/Econometria_Cap10_Multicolinearidade.pdf
* https://blog.minitab.com/pt/basta-lidando-com-a-multicolinearidade-na-analise-de-regressao
* https://support.minitab.com/pt-br/minitab/21/help-and-how-to/statistical-modeling/regression/supporting-topics/model-assumptions/multicollinearity-in-regression/