# Distribution check

Tests properties of an R implementation of a distribution, i.e., of all
four of its “dpqr” functions.

## Usage

``` r
distCheck(fun = "norm", n = 1000, robust = TRUE, subdivisions = 100, ...)
```

## Arguments

- fun:

  a character string, the name of the distribution.

- n:

  an integer specifying the number of random variates to be generated.

- robust:

  logical flag, should robust estimates be used? By default `TRUE`.

- subdivisions:

  integer specifying the numbers of subdivisions in integration.

- ...:

  the distributional parameters.

## Examples

``` r
distCheck("norm", mean = 1, sd = 1)
#> 
#> Distribution Check for: norm 
#>  Call: distCheck(fun = "norm", mean = 1, sd = 1)
#> 
#> 1. Normalization Check:
#>  NORM 1 with absolute error < 1.6e-05
#> 
#> 2. [p-pfun(qfun(p))]^2 Check:
#>     [,1] [,2] [,3] [,4] [,5] [,6]  [,7]
#> p 0.001 0.01  0.1  0.5  0.9 0.99 0.999
#> P 0.001 0.01  0.1  0.5  0.9 0.99 0.999
#>         RMSE 
#> 2.205081e-17 
#> 
#> 3. r(1000) Check:
#>        MEAN   VAR
#> SAMPLE 0.99 0.897
#>    X   1 with absolute error < 4.4e-07
#>    X^2 2 with absolute error < 7.9e-07
#>        MEAN VAR
#> EXACT     1   1
#> 
#>    normCheck    rmseCheck meanvarCheck 
#>         TRUE         TRUE        FALSE 

distCheck("lnorm", meanlog = 0.5, sdlog = 2, robust=FALSE)
#> 
#> Distribution Check for: lnorm 
#>  Call: distCheck(fun = "lnorm", robust = FALSE, meanlog = 0.5, sdlog = 2)
#> 
#> 1. Normalization Check:
#>  NORM 0.9999976 with absolute error < 7.6e-05
#> 
#> 2. [p-pfun(qfun(p))]^2 Check:
#>     [,1] [,2] [,3] [,4] [,5] [,6]  [,7]
#> p 0.001 0.01  0.1  0.5  0.9 0.99 0.999
#> P 0.001 0.01  0.1  0.5  0.9 0.99 0.999
#>         RMSE 
#> 2.205081e-17 
#> 
#> 3. r(1000) Check:
#>        MEAN  VAR
#> SAMPLE  9.1 2170
#>    X   12.18247 with absolute error < 0.0012
#>    X^2 8103.065 with absolute error < 0.64
#>        MEAN  VAR
#> EXACT  12.2 7950
#> 
#>    normCheck    rmseCheck meanvarCheck 
#>         TRUE         TRUE        FALSE 
## here, true E(X) = exp(mu + 1/2 sigma^2) = exp(.5 + 2) = exp(2.5) = 12.182
## and      Var(X) = exp(2*mu + sigma^2)*(exp(sigma^2) - 1) =       7954.67
```
