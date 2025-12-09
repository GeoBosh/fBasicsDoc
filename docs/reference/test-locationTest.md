# Two sample location tests

Tests if two series differ in their distributional location parameter.

## Usage

``` r
locationTest(x, y, method = c("t", "kw2"), title = NULL,
    description = NULL)
```

## Arguments

- x, y:

  numeric vectors of data values.

- method:

  a character string naming which test should be applied.

- title:

  an optional title string, if not specified the input's data name is
  deparsed.

- description:

  optional description string, or a vector of character strings.

## Details

The `method = "t"` can be used to determine if the two sample means are
equal for unpaired data sets. Two variants are used, assuming equal or
unequal variances.

The `method = "kw2"` performs a Kruskal-Wallis rank sum test of the null
hypothesis that the central tendencies or medians of two samples are the
same. The alternative is that they differ. Note, that it is not assumed
that the two samples are drawn from the same distribution. It is also
worth to know that the test assumes that the variables under
consideration have underlying continuous distributions.

## Value

an object from class
[`fHTEST`](https://geobosh.github.io/fBasicsDoc/reference/fHTEST-class.md)

## Note

Some of the test implementations are selected from R's `ctest` package.

## References

Conover, W. J. (1971); *Practical nonparametric statistics*, New York:
John Wiley & Sons.

Lehmann E.L. (1986); *Testing Statistical Hypotheses*, John Wiley and
Sons, New York.

## Author

R-core team for hypothesis tests implemented from R's package `ctest`.

## Examples

``` r
x <- rnorm(50)
y <- rnorm(50)
  
locationTest(x, y, "t")
#> 
#> Title:
#>  t Test
#> 
#> Test Results:
#>   PARAMETER:
#>     x Observations: 50
#>     y Observations: 50
#>     mu: 0
#>   SAMPLE ESTIMATES:
#>     Mean of x: 0.2137
#>     Mean of y: -0.2064
#>     Var  of x: 0.8717
#>     Var  of y: 0.672
#>   STATISTIC:
#>                 T: 2.3905
#>     T | Equal Var: 2.3905
#>   P VALUE:
#>     Alternative Two-Sided: 0.01877 
#>     Alternative      Less: 0.9906 
#>     Alternative   Greater: 0.009384 
#>     Alternative Two-Sided | Equal Var: 0.01873 
#>     Alternative      Less | Equal Var: 0.9906 
#>     Alternative   Greater | Equal Var: 0.009367 
#>   CONFIDENCE INTERVAL:
#>     Two-Sided: 0.0713, 0.7688
#>          Less: -Inf, 0.7119
#>       Greater: 0.1282, Inf
#>     Two-Sided | Equal Var: 0.0714, 0.7687
#>          Less | Equal Var: -Inf, 0.7118
#>       Greater | Equal Var: 0.1283, Inf
#> 
locationTest(x, y, "kw2")
#> 
#> Title:
#>  Kruskal-Wallis Two Sample Test
#> 
#> Test Results:
#>   PARAMETER:
#>     x Observations: 50
#>     y Observations: 50
#>   SAMPLE ESTIMATES:
#>     Mean of x: 0.2137
#>     Mean of y: -0.2064
#>     Var  of x: 0.8717
#>     Var  of y: 0.672
#>   STATISTIC:
#>     KW chi-squared: 4.7156
#>   P VALUE:
#>     0.02989 
#> 
```
