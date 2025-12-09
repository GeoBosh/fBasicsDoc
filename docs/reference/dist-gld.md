# Generalized Lambda Distribution

Density, distribution function, quantile function and random generation
for the generalized lambda distribution.

## Usage

``` r
dgld(x, lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8, log = FALSE)
pgld(q, lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
qgld(p, lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
rgld(n, lambda1 = 0, lambda2 = -1, lambda3 = -1/8, lambda4 = -1/8)
```

## Arguments

- lambda1:

  location parameter.

- lambda2:

  scale parameter.

- lambda3:

  first shape parameter.

- lambda4:

  second shape parameter.

- n:

  number of observations.

- p:

  a numeric vector of probabilities.

- x, q:

  a numeric vector of quantiles.

- log:

  a logical, if TRUE, probabilities `p` are given as `log(p)`.

## Details

`dgld` gives the density, `pgld` gives the distribution function, `qgld`
gives the quantile function, and `rgld` generates random deviates.

## Value

numeric vector

## Author

Chong Gu for code implemented from R's contributed package `gld`.

## Examples

``` r
## rgld -
   set.seed(1953)
   r = rgld(500, 
     lambda1=0, lambda2=-1, lambda3=-1/8, lambda4=-1/8)
   plot(r, type = "l", col = "steelblue",
     main = "gld: lambda1=0 lambda2=-1 lambda3/4=-1/8")

 
## dgld - 
   # Plot empirical density and compare with true density:
   hist(r, n = 25, probability = TRUE, border = "white", 
     col = "steelblue")
   x = seq(-5, 5, 0.25)
   lines(x, dgld(x, 
     lambda1=0, lambda2=-1, lambda3=-1/8, lambda4=-1/8))

 
## pgld -  
   # Plot df and compare with true df:
   plot(sort(r), ((1:500)-0.5)/500, main = "Probability", 
     col = "steelblue")
   lines(x, pgld(x, 
     lambda1=0, lambda2=-1, lambda3=-1/8, lambda4=-1/8))

   
## qgld -
   # Compute Quantiles:
   qgld(pgld(seq(-5, 5, 1), 
     lambda1=0, lambda2=-1, lambda3=-1/8, lambda4=-1/8), 
     lambda1=0, lambda2=-1, lambda3=-1/8, lambda4=-1/8) 
#>  [1] -5 -4 -3 -2 -1  0  1  2  3  4  5
```
