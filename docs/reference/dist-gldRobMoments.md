# Robust Moments for the GLD

Computes the first four robust moments for the Generalized Lambda
Distribution.

## Usage

``` r
gldMED(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
gldIQR(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
gldSKEW(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
gldKURT(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
```

## Arguments

- lambda1:

  location parameter

- lambda2:

  scale parameter

- lambda3:

  first shape parameter

- lambda4:

  second shape parameter

## Value

a named numerical value. The name is one of `MED`, `IQR`, `SKEW`, or
`KURT`, obtained by dropping the `gld` prefix from the name of the
corresponding function.

## Author

Diethelm Wuertz.

## Examples

``` r
## gldMED -
   # Median:
   gldMED(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
#> MED 
#>   0 
 
## gldIQR - 
   # Inter-quartile Range:
   gldIQR(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
#>       IQR 
#> 0.3051849 
 
## gldSKEW -  
   # Robust Skewness:
   gldSKEW(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
#> SKEW 
#>    0 
   
## gldKURT -
   # Robust Kurtosis:
   gldKURT(lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
#>     KURT 
#> 1.376754 
```
