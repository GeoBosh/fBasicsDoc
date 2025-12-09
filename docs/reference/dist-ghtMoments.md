# Generalized Hyperbolic Student-t Moments

Calculates moments of the generalized hyperbolic Student-t distribution.

## Usage

``` r
ghtMean(beta=0.1, delta=1, mu=0, nu=10)
ghtVar(beta=0.1, delta=1, mu=0, nu=10)
ghtSkew(beta=0.1, delta=1, mu=0, nu=10)
ghtKurt(beta=0.1, delta=1, mu=0, nu=10)

ghtMoments(order, type = c("raw", "central", "mu"),
    beta=0.1, delta=1, mu=0, nu=10)
```

## Arguments

- beta:

  numeric value, the skewness parameter in the range `(0, alpha)`.

- delta:

  numeric value, the scale parameter, must be zero or positive.

- mu:

  numeric value, the location parameter, by default 0.

- nu:

  a numeric value, the number of degrees of freedom. Note, `alpha` takes
  the limit of `abs(beta)`, and `lambda=-nu/2`.

- order:

  an integer value, the order of the moment.

- type:

  a character string, `"raw"` returns the moments about zero,
  `"central"` returns the central moments about the mean, and `"mu"`
  returns the moments about the location parameter `mu`.

## Value

a named numerical value. The name is one of `mean`, `var`, `skew`, or
`kurt`, obtained by dropping the `nig` prefix from the name of the
corresponding function and lowercasing it.

for `ghtMoments`, the name is obtained by `paste0("m", order, type)`.

## References

Scott, D.J., Wuertz, D. and Tran, T.T. (2008) *Moments of the
Generalized Hyperbolic Distribution*. Preprint.

## Author

Diethelm Wuertz

## Examples

``` r
## ghtMean -
   ghtMean(beta=0.2, delta=1.2, mu=-0.5, nu=4)
#>       mean 
#> -0.3560003 
   
## ghtKurt -
   ghtKurt(beta=0.2, delta=1.2, mu=-0.5, nu=4)
#>        kurt 
#> 20654306687 
   
## ghtMoments -
   ghtMoments(4, 
     beta=0.2, delta=1.2, mu=-0.5, nu=4)
#>       m4raw 
#> 20736476941 
   ghtMoments(4, "central",
     beta=0.2, delta=1.2, mu=-0.5, nu=4)
#>   m4central 
#> 20736506474 
```
