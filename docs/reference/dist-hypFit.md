# Fit a hyperbolic distribution

Estimates the parameters of a hyperbolic distribution.

## Usage

``` r
hypFit(x, alpha = 1, beta = 0, delta = 1, mu = 0, 
    scale = TRUE, doplot = TRUE, span = "auto", trace = TRUE, 
    title = NULL, description = NULL, ...)
```

## Arguments

- x:

  a numeric vector.

- alpha:

  shape parameter, a positive number.

- beta:

  skewness parameter, `abs(beta)` is in the range `(0, alpha)`.

- delta:

  scale parameter, must be zero or positive.

- mu:

  location parameter, by default 0.

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

## Details

The meaning of the parameters given above corresponds to the first
parameterization, see
[`dhyp`](https://geobosh.github.io/fBasicsDoc/reference/dist-hyp.md) for
details.

The function [`nlm`](https://rdrr.io/r/stats/nlm.html) is used to
minimize the "negative" maximum log-likelihood function. `nlm` carries
out a minimization using a Newton-type algorithm.

## Value

an object from class
`"`[`fDISTFIT`](https://geobosh.github.io/fBasicsDoc/reference/fDISTFIT-class.md)`"`.
Slot `fit` is a list, currently with components `estimate`, `minimum`
and `code`.

## Examples

``` r
set.seed(1953)
s <- rhyp(n = 1000, alpha = 1.5, beta = 0.3, delta = 0.5, mu = -1.0) 

hypFit(s, alpha = 1, beta = 0, delta = 1, mu = mean(s), doplot = TRUE,
       trace = FALSE) 

#> 
#> Title:
#>  Hyperbolic Parameter Estimation 
#> 
#> Call:
#>  hypFit(x = s, alpha = 1, beta = 0, delta = 1, mu = mean(s), doplot = TRUE, 
#>     trace = FALSE)
#> 
#> Model:
#>  Hyperbolic Distribution
#> 
#> Estimated Parameter(s):
#>      alpha       beta      delta         mu 
#>  1.4203380  0.1913650  0.3637505 -0.9202180 
#> 
```
