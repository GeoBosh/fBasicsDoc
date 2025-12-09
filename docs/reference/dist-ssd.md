# Spline Smoothed Distribution

Density, distribution function, quantile function and random generation
from smoothing spline estimates.

## Usage

``` r
dssd(x, param, log = FALSE)
pssd(q, param)
qssd(p, param)
rssd(n, param)
```

## Arguments

- x, q:

  a numeric vector of quantiles.

- p:

  a numeric vector of probabilities.

- n:

  number of observations.

- param:

  an object as returned by the function `ssdFit`.

- log:

  a logical flag by default `FALSE`. Should labels and a main title
  drawn to the plot?

## Details

`dssd` gives the density, `pssd` gives the distribution function, `qssd`
gives the quantile function, and `rssd` generates random deviates.

## Value

numeric vector

## Author

Diethelm Wuertz, Chong Gu for the underlying `gss` package.

## References

Gu, C. (2002), *Smoothing Spline ANOVA Models*, New York
Springer–Verlag.

Gu, C. and Wang, J. (2003), *Penalized likelihood density estimation:
Direct cross-validation and scalable approximation*, Statistica Sinica,
13, 811–826.

## Examples

``` r
## ssdFit -
   set.seed(1953)
   r = rnorm(500)
   hist(r, breaks = "FD", probability = TRUE,
     col = "steelblue", border = "white")
 
## ssdFit - 
   param = ssdFit(r)
   
## dssd -  
   u = seq(min(r), max(r), len = 301)
   v = dssd(u, param)
   lines(u, v, col = "orange", lwd = 2)
```
