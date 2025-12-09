# Robust Moments for the GH

Computes the first four robust moments for the generalized hyperbolic
distribution.

## Usage

``` r
ghMED(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
ghIQR(alpha= 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
ghSKEW(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
ghKURT(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
```

## Arguments

- alpha:

  first shape parameter.

- beta:

  second shape parameter, should in the range `(0, alpha).`

- delta:

  scale parameter, must be zero or positive.

- mu:

  location parameter, by default 0.

- lambda:

  defines the sublclass, by default \\-1/2\\.

## Details

The meanings of the parameters correspond to the first parameterization,
see [`gh`](https://geobosh.github.io/fBasicsDoc/reference/dist-gh.md)
for further details.

## Value

a named numerical value. The name is one of `MED`, `IQR`, `SKEW`, or
`KURT`, obtained by dropping the `gh` prefix from the name of the
corresponding function.

## Author

Diethelm Wuertz.

## Examples

``` r
## ghMED -
   # Median:
   ghMED(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
#>         MED 
#> 1.19506e-08 

## ghIQR -
   # Inter-quartile Range:
   ghIQR(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
#>      IQR 
#> 1.079164 

## ghSKEW -
   # Robust Skewness:
   ghSKEW(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
#>          SKEW 
#> -1.680476e-08 

## ghKURT -
   # Robust Kurtosis:
   ghKURT(alpha = 1, beta = 0, delta = 1, mu = 0, lambda = -1/2)
#>     KURT 
#> 1.387174 
```
