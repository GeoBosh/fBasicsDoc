# Two sample scale tests

Tests if two series differ in their distributional scale parameter.

## Usage

``` r
scaleTest(x, y, method = c("ansari", "mood"), 
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

The `method="ansari"` performs the Ansari-Bradley two-sample test for a
difference in scale parameters. The test returns for any sizes of the
series `x` and `y` the exact p value together with its asymptotic limit.

The `method="mood"`, is another test which performs a two-sample test
for a difference in scale parameters. The underlying model is that the
two samples are drawn from *f(x-l)* and *f((x-l)/s)/s*, respectively,
where *l* is a common location parameter and *s* is a scale parameter.
The null hypothesis is *s=1*.

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

Moore, D.S. (1986); *Tests of the chi-squared type*, In: D'Agostino,
R.B. and Stephens, M.A., eds., Goodness-of-Fit Techniques, Marcel
Dekker, New York.

## Author

R-core team for hypothesis tests implemented from R's package `ctest`.

## Examples

``` r
## Generate Series:
x = rnorm(50)
y = rnorm(50)
   
scaleTest(x, y, "ansari")
#> 
#> Title:
#>  Ansari-Bradley Test for Scale
#> 
#> Test Results:
#>   STATISTIC:
#>     AB: 1235
#>   P VALUE:
#>     Alternative Two-Sided        : 0.5812 
#>     Alternative Two-Sided | Exact: 0.5875 
#>     Alternative      Less        : 0.7094 
#>     Alternative      Less | Exact: 0.711 
#>     Alternative   Greater        : 0.2906 
#>     Alternative   Greater | Exact: 0.2937 
#>   CONFIDENCE INTERVAL:
#>     Two-Sided | Asymptotic : 0.7648, 1.7165
#>     Two-Sided |      Exact : 0.7648, 1.7165
#>     Less      | Asymptotic : 0, 1.5864
#>     Less      |      Exact : 0, 1.5865
#>     Greater   | Asymptotic : 0.817, Inf
#>     Greater   |      Exact : 0.817, Inf
#> 
scaleTest(x, y, "mood")
#> 
#> Title:
#>  Mood Two-Sample Test of Scale
#> 
#> Test Results:
#>   STATISTIC:
#>     Z: 0.556
#>   P VALUE:
#>     Alternative Two-Sided: 0.5782 
#>     Alternative      Less: 0.7109 
#>     Alternative   Greater: 0.2891 
#> 
```
