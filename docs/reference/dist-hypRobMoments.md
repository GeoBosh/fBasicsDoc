# Robust moments for the HYP

Computes the first four robust moments for the hyperbolic distribution.

## Usage

``` r
hypMED(alpha = 1, beta = 0, delta = 1, mu = 0)
hypIQR(alpha = 1, beta = 0, delta = 1, mu = 0)
hypSKEW(alpha = 1, beta = 0, delta = 1, mu = 0)
hypKURT(alpha = 1, beta = 0, delta = 1, mu = 0)
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

## Value

a named numerical value. The name is one of `MED`, `IQR`, `SKEW`, or
`KURT`, obtained by dropping the `hyp` prefix from the name of the
corresponding function.

## Author

Diethelm Wuertz

## Examples

``` r
## hypMED -
   # Median:
   hypMED(alpha = 1, beta = 0, delta = 1, mu = 0)
#>          MED 
#> 1.830888e-10 

## hypIQR -
   # Inter-quartile Range:
   hypIQR(alpha = 1, beta = 0, delta = 1, mu = 0)
#>      IQR 
#> 1.848932 

## hypSKEW -
   # Robust Skewness:
   hypSKEW(alpha = 1, beta = 0, delta = 1, mu = 0)
#>         SKEW 
#> 6.827298e-11 

## hypKURT -
   # Robust Kurtosis:
   hypKURT(alpha = 1, beta = 0, delta = 1, mu = 0)
#>     KURT 
#> 1.383927 
```
