# Fit of a Standardized NIG Distribution

Estimates the parameters of a standardized normal inverse Gaussian
distribution.

## Usage

``` r
snigFit(x, zeta = 1, rho = 0, scale = TRUE, doplot = TRUE, 
    span = "auto", trace = TRUE, title = NULL, description = NULL, ...)
```

## Arguments

- zeta, rho:

  shape parameter `zeta` is positive, skewness parameter `rho` is in the
  range (-1, 1).

- description:

  a character string which allows for a brief description.

- doplot:

  a logical flag. Should a plot be displayed?

- scale:

  a logical flag, by default `TRUE`. Should the time series be scaled by
  its standard deviation to achieve a more stable optimization?

- span:

  x-coordinates for the plot, by default 100 values automatically
  selected and ranging between the 0.001, and 0.999 quantiles.
  Alternatively, you can specify the range by an expression like
  `span=seq(min, max, times = n)`, where, `min` and `max` are the left
  and right endpoints of the range, and `n` gives the number of the
  intermediate points.

- title:

  a character string which allows for a project title.

- trace:

  a logical flag. Should the parameter estimation process be traced?

- x:

  a numeric vector.

- ...:

  parameters to be parsed.

## Value

an object from class
`"`[`fDISTFIT`](https://geobosh.github.io/fBasicsDoc/reference/fDISTFIT-class.md)`"`.

Slot `fit` is a list with the same components as the result from
`snigFit`.

## Examples

``` r
## Simulate Random Variates:
set.seed(1953)
s <- rsnig(n = 2000, zeta = 0.7, rho = 0.5) 

## snigFit -  
   # Fit Parameters:
   snigFit(s, zeta = 1, rho = 0, doplot = TRUE) 
#> 
#>  Objective Function Value:   -2637.572
#>  Parameter Estimates:        1 0 
#> 
#>  Objective Function Value:   -2637.572
#>  Parameter Estimates:        1 0 
#> 
#>  Objective Function Value:   -2637.572
#>  Parameter Estimates:        1 1.490116e-08 
#> 
#>  Objective Function Value:   -28782.33
#>  Parameter Estimates:        0.919416 0.9967478 
#> 
#>  Objective Function Value:   -2606.898
#>  Parameter Estimates:        0.9919416 0.09967478 
#> 
#>  Objective Function Value:   -2606.899
#>  Parameter Estimates:        0.9919897 0.09967478 
#> 
#>  Objective Function Value:   -2606.911
#>  Parameter Estimates:        0.9919416 0.09962666 
#> 
#>  Objective Function Value:   -2562.092
#>  Parameter Estimates:        0.9704989 0.298522 
#> 
#>  Objective Function Value:   -2550.865
#>  Parameter Estimates:        0.8431218 0.5874547 
#> 
#>  Objective Function Value:   -2550.865
#>  Parameter Estimates:        0.8431528 0.5874547 
#> 
#>  Objective Function Value:   -2550.865
#>  Parameter Estimates:        0.8431218 0.5874527 
#> 
#>  Objective Function Value:   -2563.069
#>  Parameter Estimates:        0.3791223 0.3758393 
#> 
#>  Objective Function Value:   -2546.375
#>  Parameter Estimates:        0.8371896 0.3893593 
#> 
#>  Objective Function Value:   -2546.375
#>  Parameter Estimates:        0.8372148 0.3893593 
#> 
#>  Objective Function Value:   -2546.375
#>  Parameter Estimates:        0.8371896 0.3893608 
#> 
#>  Objective Function Value:   -2540.91
#>  Parameter Estimates:        0.6467078 0.4440735 
#> 
#>  Objective Function Value:   -2540.91
#>  Parameter Estimates:        0.6467264 0.4440735 
#> 
#>  Objective Function Value:   -2540.91
#>  Parameter Estimates:        0.6467078 0.4440722 
#> 
#>  Objective Function Value:   -2549.238
#>  Parameter Estimates:        0.7913513 0.5795549 
#> 
#>  Objective Function Value:   -2540.581
#>  Parameter Estimates:        0.6574147 0.4800493 
#> 
#>  Objective Function Value:   -2540.581
#>  Parameter Estimates:        0.65741 0.4800493 
#> 
#>  Objective Function Value:   -2540.581
#>  Parameter Estimates:        0.6574147 0.4800471 
#> 
#>  Objective Function Value:   -2540.35
#>  Parameter Estimates:        0.6917205 0.4648174 
#> 
#>  Objective Function Value:   -2540.35
#>  Parameter Estimates:        0.6917027 0.4648174 
#> 
#>  Objective Function Value:   -2540.35
#>  Parameter Estimates:        0.6917205 0.4648187 
#> 
#>  Objective Function Value:   -2540.447
#>  Parameter Estimates:        0.7256555 0.4808584 
#> 
#>  Objective Function Value:   -2540.336
#>  Parameter Estimates:        0.6964065 0.4743132 
#> 
#>  Objective Function Value:   -2540.336
#>  Parameter Estimates:        0.6964023 0.4743132 
#> 
#>  Objective Function Value:   -2540.336
#>  Parameter Estimates:        0.6964065 0.4743115 
#> 
#>  Objective Function Value:   -2540.336
#>  Parameter Estimates:        0.7054868 0.4706739 
#> 
#>  Objective Function Value:   -2540.336
#>  Parameter Estimates:        0.7054778 0.4706739 
#> 
#>  Objective Function Value:   -2540.336
#>  Parameter Estimates:        0.7054868 0.4706753 
#> 
#>  Objective Function Value:   -2540.33
#>  Parameter Estimates:        0.7006596 0.4714624 
#> 
#>  Objective Function Value:   -2540.33
#>  Parameter Estimates:        0.7006637 0.4714624 
#> 
#>  Objective Function Value:   -2540.33
#>  Parameter Estimates:        0.7006596 0.4714609 
#> 
#>  Objective Function Value:   -2540.331
#>  Parameter Estimates:        0.6965967 0.468739 
#> 
#>  Objective Function Value:   -2540.329
#>  Parameter Estimates:        0.6988812 0.4702703 
#> 
#>  Objective Function Value:   -2540.329
#>  Parameter Estimates:        0.6988849 0.4702703 
#> 
#>  Objective Function Value:   -2540.329
#>  Parameter Estimates:        0.6988812 0.4702714 
#> 
#>  Objective Function Value:   -2540.329
#>  Parameter Estimates:        0.6988812 0.4702693 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6967674 0.4706101 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6967709 0.4706101 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6967674 0.4706107 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6967674 0.4706094 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961356 0.4707189 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961399 0.4707189 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961314 0.4707189 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961356 0.4707217 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961356 0.4707162 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961428 0.470719 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6962123 0.470719 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6960733 0.470719 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961428 0.4707481 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961428 0.47069 
#> 
#>  Objective Function Value:   -2540.328
#>  Parameter Estimates:        0.6961428 0.470719 
#> 
#>  Standardized Parameters: 
#>        zeta        rho fix.lambda 
#>  0.6961428  0.4707190 -0.5000000 
#> 
#>  1st Parameterization: 
#>       alpha       beta      delta         mu 
#>  1.0718480  0.5045392  0.7361345 -0.3927452 

#> 
#> Title:
#>  SNIG Parameter Estimation 
#> 
#> Call:
#>  snigFit(x = s, zeta = 1, rho = 0, doplot = TRUE)
#> 
#> Model:
#>  Standarized NIG Distribution
#> 
#> Estimated Parameter(s):
#>       zeta        rho fix.lambda 
#>  0.6961428  0.4707190 -0.5000000 
#> 
```
