#### Forward Propagation

$$
\begin{aligned}
z^{(l)} &=w^{(l)} a^{(l-1)}+b^{(l)} \\
a^{(l)} &=g^{(l)}\left(z^{(l)}\right)
\end{aligned}
$$



#### Backpropagation

Following the computation of the activations during the forward propagation step, we can then calculate the partial derivative of the cost function $J$ with respect to the weights and biases in our network. If our cost and activations are defined as:

$$
\begin{aligned}
J &= (a^{(l)} - y)^2\\
a^{(l)} &= \sigma(z^{(l)}) \\
&=\frac{1}{1 + e^{-z^{(l)}}}
\end{aligned}
$$

then for a given layer $l$:

$$
\begin{align}
\frac{\partial J_{0}}{\partial w^{(l)}}&=\frac{\partial J_{0}}{\partial a^{(l)}} \times \frac{\partial a^{(l)}}{\partial z^{(l)}} \times \frac{\partial z^{(l)}}{\partial w^{(l)}} \\
&=\frac{\partial}{\partial a^{(l)}}(a^{(l)} - y)^2 \times \frac{\partial}{\partial z^{(l)}}\left(\frac{1}{1 + e^{-z^{(l)}}}\right) \times \frac{\partial}{\partial w^{(l)}}(w^{(l)} a^{(l-1)}+b^{(l)})  \\
&=2(a^{(l)} - y) \times \sigma(z^{(l)}) \times (1 - \sigma(z^{(l)})) \times a^{(l-1)}
\end{align}
$$

$$
\frac{\partial J}{\partial w^{(l)}}=\frac{1}{n} \sum_{k=0}^{n-1} \frac{\partial J_{k}}{\partial w^{(l)}}
$$


Notice how the equation:

$$
\frac{\partial J_{0}}{\partial z^{(l)}} = \frac{\partial J_{0}}{\partial a^{(l)}} \frac{\partial a^{(l)}}{\partial z^{(l)}}
$$

is repeated in both equations.

#### Gradient Descent Update

Once we have computed our gradients, we can use them to take a step in the direction of steepest descent using gradient descent:

$$
\begin{align}
w^{(l)}&=w^{(l)}-\alpha \frac{\partial J}{\partial w^{(l)}} \\
b^{(l)}&=b^{(l)}-\alpha \frac{\partial J}{\partial b^{(l)}}
\end{align}
$$