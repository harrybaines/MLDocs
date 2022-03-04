# Norms

# $L_p$ Norm

Computes the size/length/magnitude of a vector

$$
\ell_p = \left(\sum^N_{i=1} |x_i|^p \right)^{1/p}, \text{for } p \geq 1
$$

!!! Implementation

    === "NumPy"

        ```python
        import numpy as np

        a = np.array([1,2,3,4,5])

        // L1 Norm
        l1_norm = np.linalg.norm(a, ord=1)

        // L2 Norm (Euclidean norm)
        l2_norm = np.linalg.norm(a, ord=2)

        // Squared L2 Norm
        l2_norm_sq = np.linalg.norm(a, ord=2) ** 2
        l2_norm_sq = a.T.dot(a)

        // L∞ Norm (Max Norm)
        linf_norm = np.linalg.norm(a, ord=np.inf)
        linf_norm = np.max(np.abs(a))
        ```

    === "From Scratch"

        ```python
        a = [1,2,3,4,5]

        // L1 Norm
        l1_norm = sum(abs(num) for num in a)
        
        // L2 Norm (Euclidean norm)
        l2_norm = sum([num ** 2 for num in a]) ** 0.5

        // Squared L2 Norm
        l2_norm_sq = sum([num ** 2 for num in a])
        
        // L∞ Norm (Max Norm)
        linf_norm = max(abs(num) for num in a)
        ```

- [NumPy reference for norms](https://numpy.org/doc/stable/reference/generated/numpy.linalg.norm.html)