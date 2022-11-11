# Principal Component Analysis

=== "scikit-learn"

	```python
	from sklearn.decomposition import PCA
	import numpy as np

	X = np.array([[-1, -1], [-2, -1], [-3, -2], [1, 1], [2, 1], [3, 2]])
	pca = PCA(n_components=2)
	pca.fit(X)

	print(f'Explained variance ratio: {pca.explained_variance_ratio_}')
	print(f'Singular values: {pca.singular_values_}')
	```

References:

- [sklearn docs](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html){:target="_blank"}
