### Teste de Hipótese

O teste de hipótese é um método estatístico utilizado para determinar se existe uma diferença significativa entre uma amostra e uma população. Ele permite ao pesquisador formular uma hipótese nula (H0) e uma hipótese alternativa (Ha) e usar dados estatísticos para decidir qual das hipóteses é mais provável. A hipótese nula é geralmente a de que não existe diferença significativa entre a amostra e a população, enquanto a hipótese alternativa é a de que existe tal diferença.

O nível de significância é usado para determinar se a diferença observada entre a amostra e a população é estatisticamente significativa ou se é apenas uma variação aleatória. O nível de significância é geralmente estabelecido em 5% ou 1%. Se o p-valor (probabilidade de obter os resultados observados ou mais extremos se a hipótese nula for verdadeira) for menor que o nível de significância, a hipótese nula é rejeitada e a hipótese alternativa é aceita.

```Python
from scipy import stats

# Dados de salários de funcionários
salarios = [3000, 3200, 2900, 3100, 3200, 3500, 3600, 3300, 2950, 3200]

# Realizando o teste t de uma amostra
t, p = stats.ttest_1samp(salarios, 3000)

# Nível de significância
alpha = 0.05

# Verificando o resultado
if p < alpha:
    print("Rejeitamos a hipótese nula, a média dos salários é diferente de R$ 3.000,00.")
else:
    print("Não rejeitamos a hipótese nula, a média dos salários é igual a R$ 3.000,00.")

print('O p-valor é:', p.round(4))    
```

##### Conceitos
- nível de significância
- confiança
- erro tipo I
- erro tipo II

##### Referências

- https://www.datacamp.com/tutorial/statistics-python-tutorial-probability-1
- https://www.statisticshowto.com/probability-and-statistics/hypothesis-testing/
- https://www.cin.ufpe.br/~rmcrs/ESAP/arquivos/TestesHipParametricosUmaAms.pdf
- http://www.im.ufrj.br/probest/Cap10_2013.pdf