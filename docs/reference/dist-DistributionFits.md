# Fit normal, Student-t and stable distributions

A collection of moment and maximum likelihood estimators to fit the
parameters of a distribution.  

The functions are:

|             |                                                 |
|-------------|-------------------------------------------------|
| `nFit`      | MLE parameter fit for a normal distribution,    |
| `tFit`      | MLE parameter fit for a Student t-distribution, |
| `stableFit` | MLE and Quantile Method stable parameter fit.   |

## Usage

``` r
nFit(x, doplot = TRUE, span = "auto", title = NULL, description = NULL, ...)

tFit(x, df = 4, doplot = TRUE, span = "auto", trace = FALSE, title = NULL, 
    description = NULL, ...)
    
stableFit(x, alpha = 1.75, beta = 0, gamma = 1, delta = 0, 
    type = c("q", "mle"), doplot = TRUE, control = list(),
    trace = FALSE, title = NULL, description = NULL)
```

## Arguments

- x:

  a numeric vector.

- doplot:

  a logical flag. Should a plot be displayed?

- span:

  x-coordinates for the plot, by default 100 values automatically
  selected and ranging between the 0.001, and 0.999 quantiles.
  Alternatively, you can specify the range by an expression like
  `span=seq(min, max, times = n)`, where, `min` and `max` are the left
  and right endpoints of the range, and `n` gives the number of the
  intermediate points.

- control:

  a list of control parameters, see function `nlminb`.

- alpha, beta, gamma, delta:

  The parameters are `alpha`, `beta`, `gamma`, and `delta`:  
  value of the index parameter `alpha` with `alpha = (0,2]`; skewness
  parameter `beta`, in the range \[-1, 1\]; scale parameter `gamma`; and
  shift parameter `delta`.

- description:

  a character string which allows for a brief description.

- df:

  the number of degrees of freedom for the Student distribution,
  `df > 2`, maybe non-integer. By default a value of 4 is assumed.

- title:

  a character string which allows for a project title.

- trace:

  a logical flag. Should the parameter estimation process be traced?

- type:

  a character string which allows to select the method for parameter
  estimation: `"mle"`, the maximum log likelihood approach, or `"qm"`,
  McCulloch's quantile method.

- ...:

  parameters to be parsed.

## Value

an object from class
`"`[`fDISTFIT`](https://geobosh.github.io/fBasicsDoc/reference/fDISTFIT-class.md)`"`.

Slot `fit` has components `estimate`, `minimum`, `code` and `gradient`
(but for `nFit` `code` is `NA` and `gradient` is missing).

## Details

**Stable Parameter Estimation:**

Estimation techniques based on the quantiles of an empirical sample were
first suggested by Fama and Roll \[1971\]. However their technique was
limited to symmetric distributions and suffered from a small asymptotic
bias. McCulloch \[1986\] developed a technique that uses five quantiles
from a sample to estimate `alpha` and `beta` without asymptotic bias.
Unfortunately, the estimators provided by McCulloch have restriction
`alpha>0.6`.

*Remark:* The parameter estimation for the stable distribution via the
maximum Log-Likelihood approach may take a quite long time.

## Examples

``` r
set.seed(1953)
s <- rnorm(n = 1000, 0.5, 2) 

nFit(s, doplot = TRUE) 

#> 
#> Title:
#>  Normal Parameter Estimation 
#> 
#> Call:
#>  nFit(x = s, doplot = TRUE)
#> 
#> Model:
#>  Normal Distribution
#> 
#> Estimated Parameter(s):
#>      mean        sd 
#> 0.4952318 2.0767958 
#> 
```
