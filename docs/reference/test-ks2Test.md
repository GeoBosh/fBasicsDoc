# Two sample Kolmogorov-Smirnov test

Tests if two series are distributionally equivalent using two sample
Kolmogorov-Smirnov test.

## Usage

``` r
ks2Test(x, y, title = NULL, description = NULL)
```

## Arguments

- x, y:

  numeric vectors of data values.

- title:

  an optional title string, if not specified the inputs data name is
  deparsed.

- description:

  optional description string, or a vector of character strings.

## Details

The test `ks2Test` performs a Kolmogorov-Smirnov two sample test that
the two data samples, `x` and `y`, come from the same distribution, not
necessarily a normal distribution. That means that it is not specified
what that common distribution is.

`ks2Test` calls several times base R's
[`ks.test`](https://rdrr.io/r/stats/ks.test.html) p-values for all three
alternatives (two-sided, less, and greater), as well as the exact
p-value for the two-sided case.

Note that the p-values are computed under a hypothesis of i.i.d., which
is rarely the case for time series. So, the results should be
interpreted cautiosly if that is the case. The same applies when the
data are residuals from fitted models.

## Value

an object from class
[`fHTEST`](https://geobosh.github.io/fBasicsDoc/reference/fHTEST-class.md)

## References

Conover, W. J. (1971); *Practical nonparametric statistics*, New York:
John Wiley & Sons.

Lehmann E.L. (1986); *Testing Statistical Hypotheses*, John Wiley and
Sons, New York.

## Examples

``` r
x <- rnorm(50)
y <- rnorm(50)
  
ks2Test(x, y)
#> 
#> Title:
#>  Kolmogorov-Smirnov Two Sample Test
#> 
#> Test Results:
#>   STATISTIC:
#>     D | Two Sided: 0.24
#>        D^- | Less: 0.24
#>     D^+ | Greater: 0
#>   P VALUE:
#>     Alternative       Two-Sided: 0.1124 
#>     Alternative Exact Two-Sided: 0.1124 
#>     Alternative            Less: 0.0562 
#>     Alternative         Greater: 1 
#> 
```
