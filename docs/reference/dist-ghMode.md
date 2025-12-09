# Generalized Hyperbolic Mode

Computes the mode of the generalized hyperbolic function.

## Usage

``` r
ghMode(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
```

## Arguments

- alpha:

  first shape parameter.

- beta:

  second shape parameter, should in the range `(0, alpha).`

- delta:

  scale parameter, must be zero or positive.

- mu:

  location parameter, by default 0.

- lambda:

  defines the sublclass, by default \\-1/2\\.

## Details

The meanings of the parameters correspond to the first parameterization,
see [`gh`](https://geobosh.github.io/fBasicsDoc/reference/dist-gh.md)
for further details.

## Value

a numeric value, the mode of the generalized hyperbolic distribution

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
## ghMode -
   ghMode()
#> [1] -1.344762e-08
```
