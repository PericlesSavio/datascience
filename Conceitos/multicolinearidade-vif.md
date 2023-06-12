# Multicolinearidade

A multicolinearidade é um fenômeno em que duas ou mais variáveis ​​preditoras em um modelo de regressão são altamente correlacionadas entre si, dificultando a determinação do efeito individual de cada variável na variável dependente.

# VIF (Variance Inflation Factor)

O VIF ou Fator de inflação da variância mede a multicolinearidade na análise de regressão. 

$$VIF = 1/Tolerância$$

ou

$$VIF = 1/(1-R^2)$$

Onde varia de 1 até ∞, sendo que quanto mais baixo o VIF, menor a multicolinearidade.


##### Referências
- https://quantifyinghealth.com/vif-threshold/
- https://corporatefinanceinstitute.com/resources/data-science/variance-inflation-factor-vif/
- https://www.statisticshowto.com/variance-inflation-factor/
- https://sparkbyexamples.com/machine-learning/variance-inflation-factor-vif/
- https://psicometriaonline.com.br/o-que-e-multicolinearidade/
- https://statisticsbyjim.com/regression/multicollinearity-in-regression-analysis/