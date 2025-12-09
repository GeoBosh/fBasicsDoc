# Generalized Hyperbolic Student-t distribution

Density, distribution function, quantile function and random generation
for the generalized hyperbolic Student-t distribution.

## Usage

``` r
dght(x, beta = 0.1, delta = 1, mu = 0, nu = 10, log = FALSE)
pght(q, beta = 0.1, delta = 1, mu = 0, nu = 10)
qght(p, beta = 0.1, delta = 1, mu = 0, nu = 10)
rght(n, beta = 0.1, delta = 1, mu = 0, nu = 10)
```

## Arguments

- x, q:

  a numeric vector of quantiles.

- p:

  a numeric vector of probabilities.

- n:

  number of observations.

- beta:

  numeric value, the skewness parameter in the range `(0, alpha)`.

- delta:

  numeric value, the scale parameter, must be zero or positive.

- mu:

  numeric value, the location parameter, by default 0.

- nu:

  a numeric value, the number of degrees of freedom. Note, `alpha` takes
  the limit of `abs(beta)`, and `lambda=-nu/2`.

- log:

  a logical, if TRUE, probabilities `p` are given as `log(p)`.

## Details

`dght` gives the density, `pght` gives the distribution function, `qght`
gives the quantile function, and `rght` generates random deviates.

The parameters are as in the first parameterization.

## Value

numeric vector

## References

Atkinson, A.C. (1982); *The simulation of generalized inverse Gaussian
and hyperbolic random variables*, SIAM J. Sci. Stat. Comput. 3, 502–515.

Barndorff-Nielsen O. (1977); *Exponentially decreasing distributions for
the logarithm of particle size*, Proc. Roy. Soc. Lond., A353, 401–419.

Barndorff-Nielsen O., Blaesild, P. (1983); *Hyperbolic distributions. In
Encyclopedia of Statistical Sciences*, Eds., Johnson N.L., Kotz S. and
Read C.B., Vol. 3, pp. 700–707. New York: Wiley.

Raible S. (2000); *Levy Processes in Finance: Theory, Numerics and
Empirical Facts*, PhD Thesis, University of Freiburg, Germany, 161
pages.

## Examples

``` r
## ght -
   #
```
