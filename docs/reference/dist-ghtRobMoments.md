# Robust Moments for the GHT

Computes the first four robust moments for the generalized hyperbolic
Student-t.

## Usage

``` r
ghtMED(beta = 0.1, delta = 1, mu = 0, nu = 10)
ghtIQR(beta = 0.1, delta = 1, mu = 0, nu = 10)
ghtSKEW(beta = 0.1, delta = 1, mu = 0, nu = 10)
ghtKURT(beta = 0.1, delta = 1, mu = 0, nu = 10)
```

## Arguments

- beta:

  skewness parameter in the range `(0, alpha)`.

- delta:

  scale parameter, must be zero or positive.

- mu:

  location parameter, by default 0.

- nu:

  a numeric value, the number of degrees of freedom. Note, `alpha` takes
  the limit of `abs(beta)`, and `lambda=-nu/2`.

## Details

The parameters are those of the first parameterization.

## Value

a named numerical value. The name is one of `MED`, `IQR`, `SKEW`, or
`KURT`, obtained by dropping the `ght` prefix from the name of the
corresponding function.

## Author

Diethelm Wuertz.

## Examples

``` r
## ghtMED -
   # Median:
   ghtMED(beta = 0.1, delta = 1, mu = 0, nu = 10)
#>        MED 
#> 0.01111361 

## ghtIQR -
   # Inter-quartile Range:
   ghtIQR(beta = 0.1, delta = 1, mu = 0, nu = 10)
#>     IQR 
#> 0.44269 

## ghtSKEW -
   # Robust Skewness:
   ghtSKEW(beta = 0.1, delta = 1, mu = 0, nu = 10)
#>        SKEW 
#> 0.002441764 

## ghtKURT -
   # Robust Kurtosis:
   ghtKURT(beta = 0.1, delta = 1, mu = 0, nu = 10)
#>    KURT 
#> 1.27687 
```
