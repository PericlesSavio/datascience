# K-means

K-means é um dos mais simples e mais conhecidos algoritmos de aprendizado **não supervisionados**.

Em geral, clustering usa técnicas iterativas para agrupar casos de um conjunto de dados em clusters que contenham características semelhantes. Esses agrupamentos são úteis para explorar dados, identificando anomalias nos dados e criar previsões. Modelos de clustering também podem ajudar a identificar relações em um conjunto de dados que você pode não derivar logicamente por meio de navegação ou simples observação. Por esses motivos, clustering é frequentemente usado nas fases iniciais da tarefa de aprendizado de máquina para explorar os dados e descobrir correlações inesperadas.

### Etapas (por dentro do K-means)
1. Definir o número de clusters que você deseja identificar em seus dados. Este é o "K" no agrupamento K-means.
2. O algoritmo começa com um conjunto inicial de centroides escolhidos aleatoriamente.
3. É calculado a distância de todos os pontos para os centroides.
4. É associado os pontos mais próximos de cada centroide.
5. Novos centroides são calculados.
6. O processo é repetido (a partir do item 2) até não haver mais movimentações dos centroides.

![Animação](centroides_animacao.gif "Animação")

### Conceitos
- Centroide: O centroide é um ponto representativo de cada cluster. O algoritmo K-means atribui cada ponto de dados de entrada a um dos clusters minimizando a soma de quadrados dentro do cluster.

### Características
- É sensível a posição dos primeiros centroides.
- Pode ser necessário rodar várias vezes.
- Variáveis categóricas e não categóricas
- O mecanismo de clusterização se baseia na diminuição das distâncias das observações de um cluster e seu centroide.

#### Algumas bibliotecas

```python
# normalizar os dados
from sklearn.preprocessing import StandardScaler

# modelo
from sklearn.cluster import KMeans

# análise de variância (ANOVA)
import statsmodels.api as sm
```

### Referências
 - https://learn.microsoft.com/pt-br/azure/machine-learning/component-reference/k-means-clustering
 - https://mubaris.com/posts/kmeans-clustering/
 - https://www.kaggle.com/code/satishgunjal/tutorial-k-means-clustering
 - https://www.youtube.com/watch?v=njRYKzRKBPY
 - https://github.com/liadadash/K-Means