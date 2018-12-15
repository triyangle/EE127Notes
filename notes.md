# Slides
## Lec 18
### Projection on probability simplex
#### Slide 15
$\begin{align*}
    g(\nu) &= \min_{x \geq 0} \mathcal{L}(x, \nu)
    \\
    &= \min_{x \geq 0} \frac{1}{2} \|x - z\|^{2}_{2} + \nu(1 -
    \mathbf{1}^{\top} x)
    \\
    &= \min_{x \geq 0} \frac{1}{2} z^{\top} z + \nu + \sum_{i = 1}^{n}
    \left(\frac{x_{i}^{2}}{2} - x_{i} (\nu + z_{i}) \right)
\end{align*}$

equivalent to

$\begin{align*}
    g(\nu) &= \max_{\lambda \geq 0} \min_{x} \mathcal{L}(x, \lambda, \nu)
    \\
    &= \max_{\lambda \geq 0} \min_{x} \frac{1}{2} \|x - z\|^{2}_{2} + \nu(1 -
    \mathbf{1}^{\top}x) + \lambda^{\top}(-x)
    \\
    &= \max_{\lambda \geq 0} \min_{x} \frac{1}{2} \|z\|^{2}_{2} + \nu + \sum_{i =
    1}^{n} \left(\frac{x_{i}^{2}}{2} - x_{i}(\nu + z_{i} + \lambda_{i}) \right)
    \\
    &= \max_{\lambda \geq 0} \frac{1}{2} \|z\|^{2}_{2} + \nu + \sum_{i =
    1}^{n}-\left(\frac{(\nu + z_{i} + \lambda_{i})^{2}}{2}\right) &
    \text{optimizing } x_{i} = \nu + z_{i} + \lambda_{i}
    \\
    &= \max_{\lambda \geq 0} \frac{1}{2} \|z\|^{2}_{2} + \nu + \sum_{i =
    1}^{n}\left(-\frac{(\nu + z_{i})^{2}}{2} - \frac{\lambda_{i}^{2}}{2} -
    \lambda_{i}(\nu + z_{i})\right)
    \\
    &= \frac{1}{2} \|z\|^{2}_{2} + \nu + \sum_{i =
    1}^{n}\left(-\frac{(\nu + z_{i})^{2}}{2} - \frac{1}{2} \max{(0, -(\nu +
    z_{i}))}^{2}\right)
    \\
    &= \frac{1}{2} \|z\|^{2}_{2} + \nu - \frac{1}{2}\sum_{i =
    1}^{n}\max{(0, \nu + z_{i})}^{2}
\end{align*}$

#### Slide 17
$\begin{align*}
    \frac{1}{2} \|x^{*}(\nu^{*}) - z\|^{2}_{2} &= \frac{1}{2} z^{\top} z +
    \frac{1}{2} \sum_{i = 1}^{n} \left(x_{i}^{*}(\nu^{*})^{2} -
    2x_{i}^{*}(\nu^{*}) z_{i}\right)
    \\
    &= \frac{1}{2} z^{\top} z - \frac{1}{2} \sum_{i = 1}^{n} \left(
    x_{i}^{*}(\nu^{*})^{2} - 2x_{i}^{*}(\nu^{*}) \nu^{*}\right)
    \\
    &= \frac{1}{2} z^{\top} z - \frac{1}{2} \sum_{i = 1}^{n} \left(
    x_{i}^{*}(\nu^{*})^{2}\right) + \nu^{*} = g(\nu^{*})
\end{align*}$

## Lec 19
### Minimum-norm solutions to linear equations
#### Slide 10
* See p. 280 Optimization Models (296 in djvu)

#### Slide 11
* $\nu^{*} = \left(AA^{\top}\right)^{-1}b$ → optimize $g(\nu)$ over $\nu$
    * $b - AA^{\top}v = 0$

### Dual of LASSO
#### Slide 13
* [See](https://piazza.com/class/jkbibfkncxd4pr?cid=454)
    * $\lambda w = A^{\top}\nu$ and $\|w\|_{\infty} \leq 1$ $\implies$
        $\|A^{\top} \nu\|_{\infty} \leq \lambda$

### Strong duality result (minimax game)
#### Slide 23
* Primal: $\min_{x, t} t : t \mathbf{1} \geq Mx, x \geq 0, \mathbf{1}^{\top}x =
    1$
    * Equivalent to $\min_{x, t} \max_{\lambda \geq 0, \mu} \mathcal{L}(x, t,
        \lambda, \mu)$
* Lagrangian: $\mathcal{L}(x, t, \lambda, \mu) = t + \lambda_{1}^{\top}(-x) +
    \lambda_{2}^{\top} \left( Mx - t \mathbf{1}\right) + \mu(\mathbf{1}^{\top}
    x - 1)$
* Dual:
    * $\begin{align*}
        \max_{\lambda \geq 0, \mu} \min_{x, t} \mathcal{L}(x, t, \lambda, \mu)
        &= \max_{\lambda \geq 0, \mu} \min_{x, t} t(1 - \lambda_{2}^{\top}
        \mathbf{1}) + x^{\top}(\mu \mathbf{1} - \lambda_{1} + M^{\top}
        \lambda_{2}) - \mu
        \\
        &= \max_{\lambda \geq 0, \mu} -\mu : \lambda_{2}^{\top} \mathbf{1} = 1,
        \mu \mathbf{1} \geq - M^{\top} \lambda_{2}
        \end{align*}$

#### Slide 25
* Should be $p^{*} = \min_{w, b} \log L(w, b)$
* Should be $\nu \in [-1, 0]^{m}$

## Lec 22
### Key Result
#### Slide 23
* $p^{*} = \min_{v, r} L\left(X^{\top} Xv\right) + \lambda\left(\|r\|^{2}_{2} + 2r^{\top}Xv + \|Xv\|_{2}^{2}\right)$

# OH
* Dualize constraints that couple variables together → try to decouple
    * Leave independent constraints as constraints
* $\min_{w} \|y - Xw\|^{2}_{2} + \lambda \|w\|_{1} \equiv \min_{w} \|y -
    Xw\|_{2}^{2} : \|w\|_{1} \leq \beta$ by [Lagrangian duality](https://math.stackexchange.com/questions/416099/lasso-constraint-form-equivalent-to-penalty-form)
