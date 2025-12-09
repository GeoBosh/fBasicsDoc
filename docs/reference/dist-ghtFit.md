# GHT distribution fit

Estimates the distributional parameters for a generalized hyperbolic
Student-t distribution.

## Usage

``` r
ghtFit(x, beta = 0.1, delta = 1, mu = 0, nu = 10, 
    scale = TRUE, doplot = TRUE, span = "auto", trace = TRUE, 
    title = NULL, description = NULL, ...)
```

## Arguments

- beta, delta, mu:

  numeric values. `beta` is the skewness parameter in the range
  `(0, alpha)`; `delta` is the scale parameter, must be zero or
  positive; `mu` is the location parameter, by default 0. These are the
  parameters in the first parameterization.

- nu:

  defines the number of degrees of freedom. Note, `alpha` takes the
  limit of `abs(beta)`, and `lambda=-nu/2`.

- x:

  a numeric vector.

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

The function [`nlm`](https://rdrr.io/r/stats/nlm.html) is used to
minimize the "negative" log-likelihood function. `nlm` carries out a
minimization using a Newton-type algorithm.

## Value

an object from class `"fDISTFIT"`. Slot `fit` is a list, currently with
components `estimate`, `minimum` and `code`.

## Examples

``` r
## ghtFit -
   # Simulate Random Variates:
   set.seed(1953)
   
## ghtFit -  
   # Fit Parameters:
```
