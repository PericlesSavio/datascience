# Regressão Linear
Uma análise de regressão gera uma equação para descrever a relação estatística entre um ou mais preditores e a variável de resposta e para predizer novas observações. A regressão linear normalmente usa o método de estimativa de mínimos quadrados ordinários que deriva a equação minimizando a soma dos resíduos quadrados.

### Conceitos
* **R²**: coeficiente de determinação, coeficiente de ajuste ou coeficiente de explicação. Quanto mais alto o valor de **R²** melhor o modelo ajusta seus dados. O valor de **R²** está sempre entre 0 e 100%. Indica o percentual de variância da variável Y que é devido ao comportamento de variação conjunta das variáveis explicativas X. O **R²** sempre aumenta quando você adiciona mais preditores a um modelo.   Por exemplo, o melhor modelo de cinco preditores terá sempre um **R²** que é pelo menos tão elevado quanto o melhor modelo de quatro preditores.

* **Modelos lineares generalizados**:  (GLMs, na sigla em inglês) são uma classe de modelos estatísticos que permitem uma ampla variedade de distribuições para a variável dependente. Eles são uma generalização dos modelos lineares tradicionais, como a regressão linear, e permitem lidar com dados que não sejam normalmente distribuídos, por exemplo, dados com distribuição binomial ou Poisson.

* **Teste F**: É usado para avaliar se um conjunto de variáveis independentes, também chamadas de preditoras, tem um efeito significativo sobre a variável dependente em um modelo de regressão linear. O teste compara a variabilidade explicada pelo modelo (também chamada de soma de quadrados de regressão) com a variabilidade não explicada (também chamada de soma de quadrados residual) para determinar se o modelo é significativo. O valor F é a relação entre a variabilidade explicada e não explicada, e a significância é avaliada usando um valor p.

* **ANOVA (Analysis of Variance)**: É uma técnica estatística que permite comparar a variância entre as médias de dois ou mais grupos. Na regressão linear, a ANOVA é utilizada para testar a hipótese de que pelo menos uma das variáveis independentes tem um efeito significativo na variável dependente.


### Referências
* https://support.minitab.com/pt-br/minitab/20/help-and-how-to/statistical-modeling/regression/supporting-topics/basics/types-of-regression-analyses/
* https://blog.minitab.com/pt/entendendo-analise-de-variancia-anova-e-o-teste-f
* https://medium.com/data-hackers/interpretando-ml-modelos-lineares-bccbd9f5d6a0
* http://leg.ufpr.br/~lucambio/GLM/GLM.html
* https://geokrigagem.com.br/analise-de-variancia-anova-e-regressao-linear-multipla-parte-1/
