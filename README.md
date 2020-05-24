# A Somewhat Different Distribution Clustering Method

##### Sample usage
1. Define a metric function based on the below implementation
2. Load the function as a custom distance metric to sklearn hierarichal clustering [[ref]](https://docs.scipy.org/doc/scipy/reference/cluster.hierarchy.html)
```
from scipy.cluster.hierarchy import fclusterdata
fclusterdata(X, 1.0, metric=DistributionClusteringMetric)
```

##### Implementation

<!-- Equations generated with https://www.codecogs.com/latex/eqneditor.php -->

1. For subvariable x^1 with time series length i:

<a href="https://www.codecogs.com/eqnedit.php?latex=x^1=[x_1^1&space;,x_2^1&space;,x_3^1&space;...x_i^1&space;]&space;...&space;[1]" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x^1=[x_1^1&space;,x_2^1&space;,x_3^1&space;...x_i^1&space;]&space;...&space;[1]" title="x^1=[x_1^1 ,x_2^1 ,x_3^1 ...x_i^1 ] ... [1]" /></a>

2. We normalize the time series data across all subvariables:

<a href="https://www.codecogs.com/eqnedit.php?latex=N(x^1)=[N(x_1^1)&space;,N(x_2^1)&space;,N(x_3^1)&space;...N(x_i^1)&space;]&space;...&space;[2]" target="_blank"><img src="https://latex.codecogs.com/gif.latex?N(x^1)=[N(x_1^1)&space;,N(x_2^1)&space;,N(x_3^1)&space;...N(x_i^1)&space;]&space;...&space;[2]" title="N(x^1)=[N(x_1^1) ,N(x_2^1) ,N(x_3^1) ...N(x_i^1) ] ... [2]" /></a>

3. Generate distributions with n bins (e.g. n=100):

<a href="https://www.codecogs.com/eqnedit.php?latex=D(N(x^1))=[d_1...&space;d_n]_n^{x^1}&space;...&space;[3]" target="_blank"><img src="https://latex.codecogs.com/gif.latex?D(N(x^1))=[d_1...&space;d_n]_n^{x^1}&space;...&space;[3]" title="D(N(x^1))=[d_1... d_n]_n^{x^1} ... [3]" /></a>

4. Calculate DTW distance (recommended), correlation, or other distance functions between distributions of 2 products:

<a href="https://www.codecogs.com/eqnedit.php?latex=Dist(D(N(x^1),&space;D(N(x^2))&space;...&space;[4]" target="_blank"><img src="https://latex.codecogs.com/gif.latex?Dist(D(N(x^1),&space;D(N(x^2))&space;...&space;[4]" title="Dist(D(N(x^1), D(N(x^2)) ... [4]" /></a>
