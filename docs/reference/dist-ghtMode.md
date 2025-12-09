# Generalized Hyperbolic Student-t Mode

Computes the mode of the generalized hyperbolic Student-t distribution.

## Usage

``` r
ghtMode(beta = 0.1, delta = 1, mu = 0, nu = 10)
```

## Arguments

- beta:

  the skewness parameter in the range `(0, alpha).`

- delta:

  the scale parameter, must be zero or positive.

- mu:

  the location parameter, by default 0.

- nu:

  a numeric value, the number of degrees of freedom. Note, `alpha` takes
  the limit of `abs(beta)`, and `lambda=-nu/2`.

## Details

These are the parameters in the first parameterization.

## Value

a numeric value, the mode for the generalized hyperbolic Student-t
distribution.

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
## ghtMode -
   ghtMode()
#> [1] 0.009090738
```
