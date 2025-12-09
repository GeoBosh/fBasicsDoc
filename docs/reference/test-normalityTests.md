# Tests for normality

A collection of functions of one sample tests for testing normality of
financial return series.  

The functions for testing normality are:

|                  |                                    |
|------------------|------------------------------------|
| `ksnormTest`     | Kolmogorov-Smirnov normality test, |
| `shapiroTest`    | Shapiro-Wilk's test for normality, |
| `jarqueberaTest` | Jarque-Bera test for normality,    |
| `dagoTest`       | D'Agostino normality test.         |

Functions for high precision Jarque Bera LM and ALM tests:

|          |                                                      |
|----------|------------------------------------------------------|
| `jbTest` | Performs finite sample adjusted JB, LM and ALM test. |

Additional functions for testing normality from the 'nortest' package:

|              |                                                 |
|--------------|-------------------------------------------------|
| `adTest`     | Anderson–Darling normality test,                |
| `cvmTest`    | Cramer–von Mises normality test,                |
| `lillieTest` | Lilliefors (Kolmogorov-Smirnov) normality test, |
| `pchiTest`   | Pearson chi-square normality test,              |
| `sfTest`     | Shapiro-Francia normality test.                 |

For SPlus/Finmetrics Compatibility:

|              |                                      |
|--------------|--------------------------------------|
| `normalTest` | test suite for some normality tests. |

## Usage

``` r
ksnormTest(x, title = NULL, description = NULL)

jbTest(x, title = NULL, description = NULL)
shapiroTest(x, title = NULL, description = NULL)
normalTest(x, method = c("sw", "jb"), na.rm = FALSE)

jarqueberaTest(x, title = NULL, description = NULL)
dagoTest(x, title = NULL, description = NULL)

adTest(x, title = NULL, description = NULL)
cvmTest(x, title = NULL, description = NULL)
lillieTest(x, title = NULL, description = NULL)
pchiTest(x, title = NULL, description = NULL)
sfTest(x, title = NULL, description = NULL)
```

## Arguments

- x:

  a numeric vector of data values or an S4 object of class
  `"timeSeries"`.

- title:

  an optional character string, if not specified the inputs data name is
  deparsed.

- description:

  optional description string, or a vector of character strings.

- method:

  for `normalTest` only, indicates one of four different methods for the
  normality test, one of `"ks"` (Kolmogorov-Smirnov one-sample test, the
  the default), `"sw"` (Shapiro-Wilk test), `"jb"` (Jarque-Bera Test),
  and `"da"` (D'Agostino Test).

- na.rm:

  for `normalTest` only, a logical value. Should missing values removed
  before computing the tests? The default value is `FALSE`.

## Details

The hypothesis tests may be of interest for many financial and economic
applications, especially for the investigation of univariate time series
returns.

Several tests for testing if the records from a data set are normally
distributed are available. The input to all these functions may be just
a vector `x` or a univariate time series object `x` of class
`timeSeries`.

First, there exists a wrapper function which allows to call one from two
normal tests either the Shapiro–Wilks test or the Jarque–Bera test. This
wrapper was introduced for compatibility with S-Plus' FinMetrics
package.

Also available are the Kolmogorov–Smirnov one sample test and the
D'Agostino normality test.

The remaining five normal tests are the Anderson–Darling test, the
Cramer–von Mises test, the Lilliefors (Kolmogorov–Smirnov) test, the
Pearson chi–square test, and the Shapiro–Francia test. They are calling
functions from R's contributed package `nortest`. The difference to the
original test functions implemented in R and from contributed R packages
is that the Rmetrics functions accept time series objects as input and
give a more detailed output report.

The Anderson-Darling test is used to test if a sample of data came from
a population with a specific distribution, here the normal distribution.
The `adTest` goodness-of-fit test can be considered as a modification of
the Kolmogorov–Smirnov test which gives more weight to the tails than
does the `ksnormTest`.

Note that `jarqueBeraTest` computes the asymptotic statistic and
p-value, while `jbTesT` gives final sample approximations.

## Value

an object from class
[`fHTEST`](https://geobosh.github.io/fBasicsDoc/reference/fHTEST-class.md).

Slot `test` is a list containing the following (optionally empty)
elements (in addition to those described in
[`fHTEST`](https://geobosh.github.io/fBasicsDoc/reference/fHTEST-class.md)):

- ksnormTest:

  the 'D' statistic and p-values for the three alternatives 'two-sided,
  'less' and 'greater'.

- shapiroTest:

  the 'W' statistic and the p-value.

- jarqueberaTest:

  no additional elements.

- jbTest:

  the 'Chi-squared' statistic with 2 degrees of freedom and the
  asymptotic p-value. `jbTest` is the finite sample version of the
  Jarque Bera Lagrange multiplier, LM, and adjusted Lagrange multiplier
  test, ALM.

- dagoTest:

  the 'Chi-squared', the 'Z3' (Skewness) and 'Z4' (Kurtosis) statistic
  together with the corresponding p values.

- adTest:

  the 'A' statistic and the p-value.

- cvmTest:

  the 'W' statistic and the p-value.

- lillieTest:

  the 'D' statistic and the p-value.

- pchiTest:

  the value for the 'P' statistic and the p-values for the adjusted and
  not adjusted test cases. In addition the number of classes is printed,
  taking the default value due to Moore (1986) computed from the
  expression `n.classes = ceiling(2 * (n^(2/5)))`, where `n` is the
  number of observations.

- sfTest:

  the 'W' statistic and the p-value.

## Note

Some of the test implementations are selected from R's `ctest` and
`nortest` packages.

## References

Anderson T.W., Darling D.A. (1954); *A Test of Goodness of Fit*, JASA
49:765–69.

Conover, W. J. (1971); *Practical nonparametric statistics*, New York:
John Wiley & Sons.

D'Agostino R.B., Pearson E.S. (1973); *Tests for Departure from
Normality*, Biometrika 60, 613–22.

D'Agostino R.B., Rosman B. (1974); *The Power of Geary's Test of
Normality*, Biometrika 61, 181–84.

Durbin J. (1961); *Some Methods of Constructing Exact Tests*, Biometrika
48, 41–55.

Durbin,J. (1973); *Distribution Theory Based on the Sample Distribution
Function*, SIAM, Philadelphia.

Geary R.C. (1947); *Testing for Normality*; Biometrika 36, 68–97.

Lehmann E.L. (1986); *Testing Statistical Hypotheses*, John Wiley and
Sons, New York.

Linnet K. (1988); *Testing Normality of Transformed Data*, Applied
Statistics 32, 180–186.

Moore, D.S. (1986); *Tests of the chi-squared type*, In: D'Agostino,
R.B. and Stephens, M.A., eds., Goodness-of-Fit Techniques, Marcel
Dekker, New York.

Shapiro S.S., Francia R.S. (1972); *An Approximate Analysis of Variance
Test for Normality*, JASA 67, 215–216.

Shapiro S.S., Wilk M.B., Chen V. (1968); *A Comparative Study of Various
Tests for Normality*, JASA 63, 1343–72.

Thode H.C. (2002); *Testing for Normality*, Marcel Dekker, New York.

Weiss M.S. (1978); *Modification of the Kolmogorov-Smirnov Statistic for
Use with Correlated Data*, JASA 73, 872–75.

Wuertz D., Katzgraber H.G. (2005); *Precise finite-sample quantiles of
the Jarque-Bera adjusted Lagrange multiplier test*, ETHZ Preprint.

## Author

R-core team for the tests from R's ctest package,  
Adrian Trapletti for the runs test from R's tseries package,  
Juergen Gross for the normal tests from R's nortest package,  
James Filliben for the Fortran program producing the runs report,  
Diethelm Wuertz and Helmut Katzgraber for the finite sample JB tests,  
Diethelm Wuertz for the Rmetrics R-port.  
Earlier versions of theses functions were based on Fortran code of Paul
Johnson.

## Examples

``` r
x <- rnorm(100)

## Kolmogorov-Smirnov one-sampe test
ksnormTest(x)
#> 
#> Title:
#>  Asymptotic one-sample Kolmogorov-Smirnov test
#> 
#> Test Results:
#>   STATISTIC:
#>     D: 0.055
#>   P VALUE:
#>     Alternative Two-Sided: 0.9224 
#>     Alternative      Less: 0.6972 
#>     Alternative   Greater: 0.5456 
#> 

## Shapiro-Wilk test
shapiroTest(x)
#> 
#> Title:
#>  Shapiro - Wilk Normality Test
#> 
#> Test Results:
#>   STATISTIC:
#>     W: 0.9905
#>   P VALUE:
#>     0.7034 
#> 

## Jarque-Bera Test
jarqueberaTest(x)
#> 
#> Title:
#>  Jarque-Bera Normality Test
#> 
#> Test Results:
#>   STATISTIC:
#>     X-squared: 0.7091
#>   P VALUE:
#>     Asymptotic p Value: 0.7015 
#> 
jbTest(x)
#> 
#> Title:
#>  Jarque - Bera Normality Test
#> 
#> Test Results:
#>   PARAMETER:
#>     Sample Size: 100
#>   STATISTIC:
#>     LM: 0.709
#>     ALM: 0.607
#>   P VALUE:
#>     LM p-value: 0.667 
#>     ALM p-value: 0.713 
#>     Asymptotic: 0.701 
#> 
```
