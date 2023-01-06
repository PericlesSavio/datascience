## Análise de Componentes Principais (PCA ou Principal Component Analysis)

## WIP

A análise de componentes principais (PCA) é uma técnica para reduzir a dimensionalidade de tais conjuntos de dados, aumentando a interpretabilidade, mas ao mesmo tempo minimizando a perda de informações. Ela faz isso criando novas variáveis não correlacionadas que maximizam sucessivamente a variância. 

PCA lida lida com variáveis **métricas** que possuem, entre si, consideráveis valores de correlação, a fim de se estabelecer nova(s) variável(is) que capture(m) o comportamento conjunto das variáveis originais. Essas variáveis têm o nome de **Fator**.

![Tux, the Linux mascot](https://programmathically.com/wp-content/uploads/2021/08/xpca-2-dimensions-1024x644.png.pagespeed.ic.QjLsspTdxx.webp)

#### Requisitos para usar PCA
* Variáveis métricas
* Variáveis com alto grau de correlação.

#### Objetivo
* Reduzir a dimensionalidade da base de dados
* Evidenciar variáveis ortogonais entre si;
* Validar constructos
* Elaborar rankings sem a utilização da ponderação arbitrária.


#### Bibliotecas mais utilizadas

```python

import pandas as pd # manipulação de dataframes
```


##### Etapas
* Teste da esfericidade de Bartlett
* Teste de Kaiser-Meyer-Olkin
* Matriz de correlação
* Calcular os Autovalores e Autovetores
* Definir a quantidade de Fatores
* Calcular os Scores Fatoriais
* Calcular as cargas fatoriais e a comunalidade











#### Referências

>https://royalsocietypublishing.org/doi/10.1098/rsta.2015.0202

>https://medium.com/@felipeverasaraujo/abrindo-a-caixa-preta-pca-an%C3%A1lise-de-componentes-principais-d5d400781dfe

>https://acervolima.com/analise-de-componentes-principais-com-python/

>https://phylos.net/2020-11-02/analise-fatorial-usando-python

>https://repositorio.enap.gov.br/bitstream/1/4790/1/Livro%20An%C3%A1lise%20Fatorial.pdf

>https://edisciplinas.usp.br/pluginfile.php/3381454/mod_resource/content/1/Resumo_PCA_FA.pdf

>https://programmathically.com/principal-components-analysis-explained-for-dummies/

>https://www.ibm.com/docs/pt-br/spss-statistics/29.0.0?topic=detection-kmo-bartletts-test

>https://medium.com/@felipeverasaraujo/abrindo-a-caixa-preta-pca-an%C3%A1lise-de-componentes-principais-d5d400781dfe

