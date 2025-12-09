# Normal Inverse Gaussian Mode

Computes the mode of the norm inverse Gaussian distribution.

## Usage

``` r
nigMode(alpha = 1, beta = 0, delta = 1, mu = 0)
```

## Arguments

- alpha:

  shape parameter.

- beta:

  skewness parameter `beta`, `abs(beta)` is in the range `(0, alpha)`.

- delta:

  scale parameter, must be zero or positive.

- mu:

  location parameter, by default 0.

## Value

a numeric value, the mode of the normal inverse Gaussian distribution

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
## nigMode -
   nigMode()
#> [1] -1.344761e-08
```
