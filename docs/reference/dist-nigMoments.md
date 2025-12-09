# Moments for the Normal Inverse Gaussian

Computes the first four moments for the normal inverse Gaussian
distribution.

## Usage

``` r
nigMean(alpha = 1, beta = 0, delta = 1, mu = 0)
nigVar(alpha = 1, beta = 0, delta = 1, mu = 0)
nigSkew(alpha = 1, beta = 0, delta = 1, mu = 0)
nigKurt(alpha = 1, beta = 0, delta = 1, mu = 0)
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

a named numerical value. The name is one of `mean`, `var`, `skew`, or
`kurt`, obtained by dropping the `nig` prefix from the name of the
corresponding function and lowercasing it.

## References

Scott, D. J., Wuertz, D. and Tran, T. T. (2008) *Moments of the
Generalized Hyperbolic Distribution*. Preprint.

## Author

Diethelm Wuertz.

## Examples

``` r
## nigMean -
   # Median:
   nigMean(alpha = 1, beta = 0, delta = 1, mu = 0)
#> mean 
#>    0 
 
## nigVar - 
   # Inter-quartile Range:
   nigVar(alpha = 1, beta = 0, delta = 1, mu = 0)
#> var 
#>   1 
 
## nigSKEW -  
   # Robust Skewness:
   nigSkew(alpha = 1, beta = 0, delta = 1, mu = 0)
#> skew 
#>    0 
   
## nigKurt -
   # Robust Kurtosis:
   nigKurt(alpha = 1, beta = 0, delta = 1, mu = 0)
#> kurt 
#>    3 
```
