# Agrupamento hierárquico

Agrupamento hierárquico é um método de clusterização em que os dados são agrupados em uma hierarquia de clusters. Ele é dividido em duas abordagens: aglomeração hierárquica (agrupamento bottom-up) e divisão hierárquica (agrupamento top-down).

Na abordagem de aglomeração, cada observação inicialmente é considerada como um cluster individual. Em seguida, os clusters são combinados iterativamente, formando novos clusters até que todas as observações estejam agrupadas em um único cluster.

Na abordagem de divisão, o cluster inicial é o conjunto de todas as observações e é dividido iterativamente em subclusters menores até que cada observação esteja em um cluster individual.

Existem vários métodos para medir a distância entre os clusters, como a distância média, a distância mínima e a distância completa.

### Em Python

```python
# importando as bibliotecas necessárias
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage
from sklearn.cluster import AgglomerativeClustering
from sklearn.preprocessing import StandardScaler

# conjunto de dados
base = [[20,1000],[27,1200],[21,2900],[37,1850],[46,900],
                 [53,950],[55,2000],[47,2100],[52,3000],[32,5900],
                 [39,4100],[41,5100],[39,7000],[48,5000],[48,6500]]

# normalizar os dados
scaler = StandardScaler()
base = scaler.fit_transform(base)


# utilizando o método de linkage ward
Z = linkage(base, method = 'ward')


# plotando o dendrograma
dendrograma = dendrogram(Z)
plt.title('Dendrograma')
plt.xlabel('Pessoas')
plt.ylabel('Distância Euclidiana')
plt.show()

# previsões
hc = AgglomerativeClustering(n_clusters = 3, affinity = 'euclidean', linkage = 'ward')
previsoes = hc.fit_predict(base)

# plotando o gráfico de dispersão com os clusters previstos
plt.scatter(base[previsoes == 0, 0], base[previsoes == 0, 1], s = 50, c = 'red', label = 'Cluster 1')
plt.scatter(base[previsoes == 1, 0], base[previsoes == 1, 1], s = 50, c = 'blue', label = 'Cluster 2')
plt.scatter(base[previsoes == 2, 0], base[previsoes == 2, 1], s = 50, c = 'green', label = 'Cluster 3')
plt.xlabel('Idade')
plt.ylabel('Salário')
plt.legend()
plt.show()
```


### Conceitos
- **Medida de dissimilaridade**: é usada para calcular a distância entre os pontos de dados ou as observações. Em **agrupamento hierárquico**, existem várias medidas de dissimilaridade comuns, incluindo a distância Euclidiana, a distância de Manhattan e a distância de Jaccard. Cada medida de dissimilaridade tem suas próprias características e é mais adequada para certos tipos de dados. Essas medidas são utilizadas para determinar como as observações devem ser agrupadas em cada nível do dendograma gerado. Em geral, o algoritmo de agrupamento hierárquico irá unir os grupos que têm a menor dissimilaridade (maior similaridade) entre si, utilizando uma das medidas mencionadas acima.

- **Distância média**: é uma medida de dissimilaridade entre dois grupos de observações, calculada como a média das distâncias entre cada observação do primeiro grupo e cada observação do segundo grupo.

- **Distância mínima**: é uma medida de dissimilaridade entre dois grupos de observações, calculada como a menor distância entre cada observação do primeiro grupo e cada observação do segundo grupo.

- **Distância completa**: é uma medida de dissimilaridade entre dois grupos de observações, calculada como a soma das distâncias entre cada observação do primeiro grupo e cada observação do segundo grupo.

- **Encadeamento por completa**: também conhecido como *encadeamento máximo*, *complete linkage* ou encadeamento de Ward é o tipo de encadeamento em que a distância entre agrupamentos é baseada na distância máxima entre todos os pontos de cada agrupamento. Esse tipo de encadeamento tende a formar agrupamentos de tamanho similar e é comumente utilizado quando se deseja agrupar os dados de acordo com suas características similares.

- **Encadeamento por média**: também conhecido como encadeamento *average linkage* é o tipo de encadeamento em que a distância entre agrupamentos é baseada na média das distâncias entre todos os pontos de cada agrupamento. Esse tipo de encadeamento tende a formar agrupamentos de tamanho desigual e é comumente utilizado quando se deseja agrupar os dados de acordo com suas características similares, mas sem se preocupar com o tamanho dos agrupamentos.

- **Encadeamento por simples**: também conhecido como encadeamento *single linkage* ou *encadeamento mínimo* é o tipo de encadeamento em que a distância entre agrupamentos é baseada na distância mínima entre todos os pontos de cada agrupamento. Esse tipo de encadeamento tende a formar agrupamentos longos e estreitos e é comumente utilizado quando se deseja identificar tendências ou padrões no conjunto de dados.


### Referências
- https://towardsdatascience.com/understanding-the-concept-of-hierarchical-clustering-technique-c6e8243758ec
- https://medium.com/@will.lucena/agrupamento-hier%C3%A1rquico-329e30a9f32d
- https://www.computersciencemaster.com.br/como-funciona-o-algoritmo-de-agrupamento-hierarquico/
- https://edu.taugc.com/blog/agrupamento-hierarquico-hierarchical-clustering/
- https://uc-r.github.io/hc_clustering
- https://www.javatpoint.com/hierarchical-clustering-in-machine-learning
- https://www.geeksforgeeks.org/hierarchical-clustering-in-data-mining/
