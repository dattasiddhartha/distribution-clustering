# A Somewhat Different Distribution Clustering Method

##### Sample usage
1. Define a metric function based on the below implementation
2. Load the function as a custom distance metric to sklearn hierarichal clustering
```
from scipy.cluster.hierarchy import fclusterdata
fclusterdata(X, 1.0, metric=DistributionClusteringMetric)
```

##### Implementation

For product $x^1$ with time series length $i$:
$$ x1=[x11 ,x21 ,x31 ...xi1 ] ... [1] $$
