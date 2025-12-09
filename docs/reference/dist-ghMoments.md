# Generalized Hyperbolic Distribution Moments

Calculates moments of the generalized hyperbolic distribution.

## Usage

``` r
ghMean(alpha=1, beta=0, delta=1, mu=0, lambda=-1/2)
ghVar(alpha=1, beta=0, delta=1, mu=0, lambda=-1/2)
ghSkew(alpha=1, beta=0, delta=1, mu=0, lambda=-1/2)
ghKurt(alpha=1, beta=0, delta=1, mu=0, lambda=-1/2)

ghMoments(order, type = c("raw", "central", "mu"),
    alpha = 1, beta=0, delta=1, mu=0, lambda=-1/2)
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

- lambda:

  numeric value, defines the sublclass, by default \\-1/2\\.

- order:

  an integer value, the order of the moment.

- type:

  a character value, `"raw"` gives the moments about zero, `"central"`
  gives the central moments about the mean, and `"mu"` gives the moments
  about the location parameter `mu`.

## Value

a named numerical value. The name is one of `mean`, `var`, `skew`, or
`kurt`, obtained by dropping the `nig` prefix from the name of the
corresponding function and lowercasing it.

for `ghMoments`, the name is obtained by `paste0("m", order, type)`.

## References

Scott, D. J., Wuertz, D. and Tran, T. T. (2008) *Moments of the
Generalized Hyperbolic Distribution*. Preprint.

## Author

Diethelm Wuertz

## Examples

``` r
## ghMean -
   ghMean(alpha=1.1, beta=0.1, delta=0.8, mu=-0.3, lambda=1)
#>        mean 
#> -0.08410502 
   
## ghKurt -
   ghKurt(alpha=1.1, beta=0.1, delta=0.8, mu=-0.3, lambda=1)
#>     kurt 
#> 2.044599 
   
## ghMoments -
   ghMoments(4, 
     alpha=1.1, beta=0.1, delta=0.8, mu=-0.3, lambda=1)
#>    m4raw 
#> 23.96634 
   ghMoments(4, "central",
     alpha=1.1, beta=0.1, delta=0.8, mu=-0.3, lambda=1)
#> m4central 
#>  24.18639 
```
