---
title: Linear Algebra
---

## Vectors

Size of a vector (modulus):

$$
|\textbf{r}|= \sqrt{\sum_{i=1}^{n} r_i^2}
$$

Dot product of two vectors:

$$
\textbf{r}.\textbf{s} = \sum_{i=1}^{n} r_1 s_1 + r_2 s_2 + ... + r_n s_n
$$

The dot product is:

- Commutative: $\textbf{r}.\textbf{s} = \textbf{s}.\textbf{r}$
- Distributive over addition: $\textbf{r}.(\textbf{s}+\textbf{t}) = \textbf{r}.\textbf{s} + \textbf{r}.\textbf{t}$
- Associative over scalar multiplication: $\textbf{r}.(a \textbf{s}) = a (\textbf{r}.\textbf{s})$

$$
\textbf{r}.\textbf{r} = \sum_{i=1}^n r_i^2 = \left(\sqrt{\sum_{i=1}^{n} r_i^2}\right)^2 = |\textbf{r}|^2
$$

i.e. the size of a vector is the square root of the dot product of the vector with itself.

From the [cosine rule](https://en.wikipedia.org/wiki/Law_of_cosines):

$$
\textbf{r}.\textbf{s}=|\textbf{r}||\textbf{s}|\cos \theta
$$

which tells us the extent to which the vectors go in the same direction. Therefore using the dot product, we can get the angle between the two vectors.

If:

- $\theta = 0^{\circ}, \cos \theta = 1, \therefore \textbf{r}.\textbf{s} = |\textbf{r}||\textbf{s}|$
- $\theta = 90^{\circ}, \cos \theta = 0, \therefore \textbf{r}.\textbf{s} = 0$ (vectors are orthogonal)
- $\theta = 180^{\circ}, \cos \theta = -1, \therefore \textbf{r}.\textbf{s} = -|\textbf{r}||\textbf{s}|$

### Scalar Projection

Scalar projection of $\textbf{s}$ onto $\textbf{r}$ (how much $\textbf{s}$ goes along $\textbf{r}$):

$$
\frac{\textbf{r}.\textbf{s}}{|\textbf{r}|} = |\textbf{s}| \cos \theta
$$

The scalar projection is 0 if the vectors are orthogonal.

### Vector Projection

$$
\textbf{r} \frac{\textbf{r}.\textbf{s}}{|\textbf{r}||\textbf{r}|} = \textbf{r} \frac{\textbf{r}.\textbf{s}}{\textbf{r}.\textbf{r}}
$$

which is the unit length vector $\frac{\textbf{r}}{|\textbf{r}|} \times$ scalar projection of $\textbf{s}$ onto $\textbf{r}$.

The triangle inequality states that the sum of any two sides of a triangle must be greater than or equal to the size of the remaining side. For every pair of vectors $\textbf{a}$ and $\textbf{b}$:

$$
|\textbf{a}| + |\textbf{b}| \geq |\textbf{a}+\textbf{b}|
$$