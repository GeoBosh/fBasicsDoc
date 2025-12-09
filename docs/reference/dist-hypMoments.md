# Hyperbolic distribution moments

Calculates moments of the hyperbolic distribution function.

## Usage

``` r
hypMean(alpha=1, beta=0, delta=1, mu=0)
hypVar(alpha=1, beta=0, delta=1, mu=0)
hypSkew(alpha=1, beta=0, delta=1, mu=0)
hypKurt(alpha=1, beta=0, delta=1, mu=0)

hypMoments(order, type = c("raw", "central", "mu"),
    alpha=1, beta=0, delta=1, mu=0)
```

## Arguments

- alpha:

  numeric value, the first shape parameter.

- beta:

  numeric value, the second shape parameter in the range `(0, alpha)`.

- delta:

  numeric value, the scale parameter, must be zero or positive.

- mu:

  numeric value, the location parameter, by default 0.

- order:

  an integer value, the order of the moment.

- type:

  a character string, `"raw"` returns the moments about zero,
  `"central"` returns the central moments about the mean, and `"mu"`
  returns the moments about the location parameter `mu`.

## Value

a named numerical value. The name is one of `mean`, `var`, `skew`, or
`kurt`, obtained by dropping the `hyp` prefix from the name of the
corresponding function and lowercasing it.

for `hypMoments`, the name is obtained by `paste0("m", order, type)`.

## References

Scott, D. J., Wuertz, D. and Tran, T. T. (2008) *Moments of the
Generalized Hyperbolic Distribution*. Preprint.

## Author

Diethelm Wuertz

## Examples

``` r
## hypMean -
   hypMean(alpha=1.1, beta=0.1, delta=0.8, mu=-0.3)
#>        mean 
#> -0.08410502 
   
## ghKurt -
   hypKurt(alpha=1.1, beta=0.1, delta=0.8, mu=-0.3)
#>     kurt 
#> 2.044599 
   
## hypMoments -
   hypMoments(4, alpha=1.1, beta=0.1, delta=0.8, mu=-0.3)
#>    m4raw 
#> 23.96634 
   hypMoments(4, "central", alpha=1.1, beta=0.1, delta=0.8, mu=-0.3)
#> m4central 
#>  24.18639 
```
