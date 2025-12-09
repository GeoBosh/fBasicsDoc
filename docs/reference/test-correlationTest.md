# Correlation tests

Tests if two series are correlated.

## Usage

``` r
correlationTest(x, y, method = c("pearson", "kendall", "spearman"), 
    title = NULL, description = NULL)

pearsonTest(x, y, title = NULL, description = NULL) 
kendallTest(x, y, title = NULL, description = NULL)
spearmanTest(x, y, title = NULL, description = NULL)
```

## Arguments

- x,y:

  numeric vectors of data values.

- method:

  a character string naming which test should be applied.

- title:

  an optional title string, if not specified the input's data name is
  deparsed.

- description:

  optional description string, or a vector of character strings.

## Details

These functions test for association/correlation between paired samples
based on the Pearson's product moment correlation coefficient (a.k.a.
sample correlation), Kendall's tau, and Spearman's rho coefficients.

`pearsonTest`, `kendallTest`, and `spearmanTest` are wrappers of base
R's [`cor.test`](https://rdrr.io/r/stats/cor.test.html) with simplified
interface. They provide 'exact' and approximate p-values for all three
alternatives (two-sided, less, and greater), as well as 95% confidence
intervals. This is particularly convenient in interactive use.

Instead of calling the individual functions, one can use
`correlationTest` and specify the required test with argument `method`.

## Value

an object from class
[`fHTEST`](https://geobosh.github.io/fBasicsDoc/reference/fHTEST-class.md)

## References

Conover, W. J. (1971); *Practical nonparametric statistics*, New York:
John Wiley & Sons.

Lehmann E.L. (1986); *Testing Statistical Hypotheses*, John Wiley and
Sons, New York.

## See also

[`locationTest`](https://geobosh.github.io/fBasicsDoc/reference/test-locationTest.md),
[`scaleTest`](https://geobosh.github.io/fBasicsDoc/reference/test-scaleTest.md),
[`varianceTest`](https://geobosh.github.io/fBasicsDoc/reference/test-varianceTest.md)

## Examples

``` r
x <- rnorm(50)
y <- rnorm(50)
  
correlationTest(x, y, "pearson")
#> 
#> Title:
#>  Pearson's Correlation Test
#> 
#> Test Results:
#>   PARAMETER:
#>     Degrees of Freedom: 48
#>   SAMPLE ESTIMATES:
#>     Correlation: 0.267
#>   STATISTIC:
#>     t: 1.9199
#>   P VALUE:
#>     Alternative Two-Sided: 0.06082 
#>     Alternative      Less: 0.9696 
#>     Alternative   Greater: 0.03041 
#>   CONFIDENCE INTERVAL:
#>     Two-Sided: -0.0122, 0.5077
#>          Less: -1, 0.4728
#>       Greater: 0.0337, 1
#> 
correlationTest(x, y, "kendall")
#> 
#> Title:
#>  Kendall's tau Correlation Test
#> 
#> Test Results:
#>   SAMPLE ESTIMATES:
#>     tau: 0.1559
#>   STATISTIC:
#>     z: 1.5977
#>     T | Exact: 708
#>   P VALUE:
#>     Alternative         Two-Sided: 0.1101 
#>     Alternative Two-Sided | Exact: 0.1123 
#>     Alternative              Less: 0.9449 
#>     Alternative      Less | Exact: 0.9457 
#>     Alternative           Greater: 0.05506 
#>     Alternative   Greater | Exact: 0.05615 
#> 

spearmanTest(x, y)
#> 
#> Title:
#>  Spearman's rho Correlation Test
#> 
#> Test Results:
#>   SAMPLE ESTIMATES:
#>     rho: 0.2346
#>   STATISTIC:
#>     S: 15940
#>   P VALUE:
#>     Alternative Two-Sided: 0.1011 
#>     Alternative      Less: 0.9495 
#>     Alternative   Greater: 0.05053 
#> 
```
