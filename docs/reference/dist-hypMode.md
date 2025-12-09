# Hyperbolic mode

Computes the mode of the hyperbolic distribution.

## Usage

``` r
hypMode(alpha = 1, beta = 0, delta = 1, mu = 0, pm = 1)
```

## Arguments

- alpha:

  shape parameter, a positive number. `alpha` can also be a vector of
  length four, containing `alpha`, `beta`, `delta` and `mu` (in that
  order).

- beta:

  skewness parameter, `abs(beta)` is in the range `(0, alpha)`.

- delta:

  scale parameter, must be zero or positive.

- mu:

  location parameter, by default 0.

- pm:

  an integer value between `1` and `4` for the selection of the
  parameterization. The default takes the first parameterization.

## Value

a numeric value, the mode in the appropriate parameterization for the
hyperbolic distribution.

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

## Author

David Scott for code implemented from R's contributed package
`HyperbolicDist`.

## Examples

``` r
## hypMode -
   hypMode()
#> [1] 0
```
