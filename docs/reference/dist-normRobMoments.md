# Robust moments for the Normal distribution

Computes the first four robust moments for the Normal distribution.

## Usage

``` r
normMED(mean = 0, sd = 1)
normIQR(mean = 0, sd = 1)
normSKEW(mean = 0, sd = 1)
normKURT(mean = 0, sd = 1)
```

## Arguments

- mean:

  locaiton parameter.

- sd:

  scale parameter.

## Value

a named numerical value. The name is one of `MED`, `IQR`, `SKEW`, or
`KURT`, obtained by dropping the `gh` prefix from the name of the
corresponding function.

## Author

Diethelm Wuertz

## Examples

``` r
## normMED -
   # Median:
   normMED(mean = 0, sd = 1)
#> MED 
#>   0 

## normIQR -
   # Inter-quartile Range:
   normIQR(mean = 0, sd = 1)
#>     IQR 
#> 1.34898 

## normSKEW -
   # Robust Skewness:
   normSKEW(mean = 0, sd = 1)
#> SKEW 
#>    0 

## normKURT -
   # Robust Kurtosis:
   normKURT(mean = 0, sd = 1)
#>     KURT 
#> 1.233095 
```
