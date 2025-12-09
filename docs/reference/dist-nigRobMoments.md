# Robust Moments for the NIG

Computes the first four robust moments for the Normal Inverse Gaussian
Distribution.

## Usage

``` r
nigMED(alpha = 1, beta = 0, delta = 1, mu = 0)
nigIQR(alpha = 1, beta = 0, delta = 1, mu = 0)
nigSKEW(alpha = 1, beta = 0, delta = 1, mu = 0)
nigKURT(alpha = 1, beta = 0, delta = 1, mu = 0)
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

a named numerical value. The name is one of `MED`, `IQR`, `SKEW`, or
`KURT`, obtained by dropping the `nig` prefix from the name of the
corresponding function.

## Author

Diethelm Wuertz.

## Examples

``` r
## nigMED -
   # Median:
   nigMED(alpha = 1, beta = 0, delta = 1, mu = 0)
#>           MED 
#> -1.058612e-07 

## nigIQR -
   # Inter-quartile Range:
   nigIQR(alpha = 1, beta = 0, delta = 1, mu = 0)
#>      IQR 
#> 1.079179 

## nigSKEW -
   # Robust Skewness:
   nigSKEW(alpha = 1, beta = 0, delta = 1, mu = 0)
#>          SKEW 
#> -8.292074e-08 

## nigKURT -
   # Robust Kurtosis:
   nigKURT(alpha = 1, beta = 0, delta = 1, mu = 0)
#>     KURT 
#> 1.387172 
```
