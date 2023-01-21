# Qui-quadrado

O **qui-quadrado** é um teste estatístico que é usado para verificar se há uma diferença significativa entre as frequências observadas de uma variável categórica e as frequências esperadas. Ele é usado para determinar se há alguma relação entre duas ou mais variáveis categóricas.

Para calcular o **qui-quadrado**, é necessário construir uma tabela de contingência, que mostra as frequências observadas para cada combinação de valores das variáveis. O **qui-quadrado** é então calculado como a soma dos quadrados das diferenças entre as frequências observadas e esperadas, dividido pela frequência esperada.


Exemplo de tabela de contigência (grau de satisfação x faixa etaria)
|   | Alto | Médio | Baixo | Total |
|---|-------------|-------------|-------------|-------|
| 18-29 | 25 | 30 | 15 | 70 |
| 30-49 | 20 | 25 | 10 | 55 |
| 50+ | 15 | 15 | 20 | 50 |
| Total | 60 | 70 | 45 | 175 |


Se o **qui-quadrado** é alto, isso sugere que há uma diferença significativa entre as frequências observadas e esperadas, indicando que há uma relação entre as variáveis. Se o **qui-quadrado** é baixo, isso sugere que não há diferença significativa entre as frequências observadas e esperadas, indicando que não há relação entre as variáveis.

$$\chi^2 = \sum_{i=1}^{n} \frac{(O_i-E_i)^2}{E_i}$$

onde:

$\chi^2$ é o valor **qui-quadrado**

$n$ é o número de categorias

$O_i$ é o número observado de ocorrências na categoria i

$E_i$ é o número esperado de ocorrências na categoria i, calculado como $(O_{total} * E_{total}) / n$

$O_{total}$ é o número total de ocorrências observadas

$E_{total}$ é o número total de ocorrências esperadas


### Exemplo em Python
```python
from scipy.stats import chi2_contingency

# tabela de contingência
tabela = [[25, 30, 15], [20, 25, 10], [15, 15, 20]]

stat, p, dof, expected = chi2_contingency(tabela)
print('Valor de qui-quadrado:', stat)
print('p-value:', p)
```

O resultado é a estatística de qui-quadrado (stat) e o valor de p (p-value). O p-value é utilizado para testar a hipótese nula de independência entre as variáveis.
Se o p-value for menor que o nível de significância (geralmente 0,05) é possível rejeitar a hipótese nula e afirmar que existe uma relação entre as variáveis.

### Referências
- http://www.leg.ufpr.br/lib/exe/fetch.php/disciplinas:ce001:teste_do_qui-quadrado.pdf
- https://bookdown.org/luisfca/docs/qui-quadrado.html
- https://www.bmj.com/about-bmj/resources-readers/publications/statistics-square-one/8-chi-squared-tests
- https://www.statisticshowto.com/probability-and-statistics/chi-square/