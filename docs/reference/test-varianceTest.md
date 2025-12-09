# Two sample variance tests

Tests if two series differ in their distributional variance parameter.

## Usage

``` r
varianceTest(x, y, method = c("varf", "bartlett", "fligner"), 
    title = NULL, description = NULL)
```

## Arguments

- x, y:

  numeric vectors of data values.

- method:

  a character string naming which test should be applied.

- title:

  an optional title string, if not specified the inputs data name is
  deparsed.

- description:

  optional description string, or a vector of character strings.

## Details

The `method="varf"` can be used to compare variances of two normal
samples performing an F test. The null hypothesis is that the ratio of
the variances of the populations from which they were drawn is equal to
one.

The `method="bartlett"` performs the Bartlett test of the null
hypothesis that the variances in each of the samples are the same. This
fact of equal variances across samples is also called *homogeneity of
variances*. Note, that Bartlett's test is sensitive to departures from
normality. That is, if the samples come from non-normal distributions,
then Bartlett's test may simply be testing for non-normality. The Levene
test (not yet implemented) is an alternative to the Bartlett test that
is less sensitive to departures from normality.

The `method="fligner"` performs the Fligner-Killeen test of the null
that the variances in each of the two samples are the same.

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
   
varianceTest(x, y, "varf")
#> 
#> Title:
#>  F Test of Variances
#> 
#> Test Results:
#>   PARAMETER:
#>     Hypothesized Ratio: 1
#>     Numerator   df: 49
#>     Denumerator df: 49
#>   SAMPLE ESTIMATES:
#>     Ratio of Variances: 1.2973
#>   STATISTIC:
#>     F: 1.2973
#>   P VALUE:
#>     Alternative Two-Sided: 0.3655 
#>     Alternative      Less: 0.8173 
#>     Alternative   Greater: 0.1827 
#>   CONFIDENCE INTERVAL:
#>     Two-Sided: 0.7362, 2.286
#>          Less: 0, 2.0851
#>       Greater: 0.8071, Inf
#> 
varianceTest(x, y, "bartlett")
#> 
#> Title:
#>  Bartlett Test for Homogeneity of Variances
#> 
#> Test Results:
#>   STATISTIC:
#>     Bartlett's Chi-squared: 0.8191
#>   P VALUE:
#>     0.3655 
#> 
varianceTest(x, y, "fligner")
#> 
#> Title:
#>  Fligner-Killeen Test for Homogeneity of Variances
#> 
#> Test Results:
#>   STATISTIC:
#>     FK:med chi-squared: 0.6764
#>   P VALUE:
#>     0.4108 
#> 
```
