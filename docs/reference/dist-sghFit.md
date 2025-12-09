# Standardized GH distribution fit

Estimates the distributional parameters for a standardized generalized
hyperbolic distribution.

## Usage

``` r
sghFit(x, zeta = 1, rho = 0, lambda = 1, include.lambda = TRUE,
    scale = TRUE, doplot = TRUE, span = "auto", trace = TRUE, 
    title = NULL, description = NULL, ...)
```

## Arguments

- x:

  a numeric vector.

- zeta, rho, lambda:

  shape parameter `zeta` is positive, skewness parameter `rho` is in the
  range (-1, 1). and index parameter `lambda`, by default 1.

- include.lambda:

  a logical flag, by default `TRUE`. Should the index parameter `lambda`
  included in the parameter estimate?

- scale:

  a logical flag, by default `TRUE`. Should the time series be scaled by
  its standard deviation to achieve a more stable optimization?

- doplot:

  a logical flag. Should a plot be displayed?

- span:

  x-coordinates for the plot, by default 100 values automatically
  selected and ranging between the 0.001, and 0.999 quantiles.
  Alternatively, you can specify the range by an expression like
  `span=seq(min, max, times = n)`, where, `min` and `max` are the left
  and right endpoints of the range, and `n` gives the number of the
  intermediate points.

- trace:

  a logical flag. Should the parameter estimation process be traced?

- title:

  a character string which allows for a project title.

- description:

  a character string which allows for a brief description.

- ...:

  parameters to be parsed.

## Value

an object from class `"fDISTFIT"`. Slot `fit` is a list, currently with
components `estimate`, `minimum`, `code`, `param`, `mean` (mean of the
original data), `var` (variance of original data).

## Examples

``` r
set.seed(1953)
s <- rsgh(n = 2000, zeta = 0.7, rho = 0.5, lambda = 0) 

sghFit(s, zeta = 1, rho = 0, lambda = 1, include.lambda = TRUE, 
       doplot = TRUE, trace = FALSE)

#> 
#> Title:
#>  SGH Parameter Estimation 
#> 
#> Call:
#>  sghFit(x = s, zeta = 1, rho = 0, lambda = 1, include.lambda = TRUE, 
#>     doplot = TRUE, trace = FALSE)
#> 
#> Model:
#>  Standarized GH Distribution
#> 
#> Estimated Parameter(s):
#>       zeta        rho     lambda 
#>  0.6700175  0.5262540 -0.1766919 
#> 
```
