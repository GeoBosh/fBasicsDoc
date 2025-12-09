# Robust moments for the GLD

Computes the first four robust moments for the Normal Inverse Gaussian
Distribution.

## Usage

``` r
sampleMED(x)
sampleIQR(x)
sampleSKEW(x)
sampleKURT(x)
```

## Arguments

- x:

  numeric vector, the sample values.

## Value

a named numerical value. The name is one of `MED`, `IQR`, `SKEW`, or
`KURT`, obtained by dropping the `sample` prefix from the name of the
corresponding function.

## Author

Diethelm Wuertz

## Examples

``` r
## Sample
x <- rt(100, 4)
   
## Median
sampleMED(x)
#>         MED 
#> -0.01580327 
 
## Inter-quartile Range
sampleIQR(x)
#>      IQR 
#> 1.391907 
 
## Robust Skewness
sampleSKEW(x)
#>        SKEW 
#> 0.009924021 
   
## Robust Kurtosis
sampleKURT(x)
#>     KURT 
#> 1.340701 
```
