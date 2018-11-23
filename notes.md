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
    \frac{1}{2} \|x^{*}(\nu^{*})\|^{2}_{2} &= \frac{1}{2} z^{\top} z +
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
### Minimum-norm solutions to linear eequations
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
