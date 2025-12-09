# Basic time series statistics

Computes basic financial time series statistics.

## Usage

``` r
basicStats(x, ci = 0.95)
```

## Arguments

- x:

  an object of class `"timeSeries"` or any other object which can be
  transformed by the function `as.timeSeries` into an object of class
  `"timeSeries"`. The latter case, other than `"timeSeries"` objects, is
  more or less untested.

- ci:

  confidence interval, a numeric value, by default 0.95, i.e. 95%.

## Details

Computes a number of sample statistics for each column of `x`. The
statistics should be clear from the row names of the returned data
frame.

`"LCL"` and `"UCL"` stand for lower/upper confidence limits, computed
under the null hypothesis of i.i.d.

`"Kurtosis"` represents the *excess kurtosis*, so its theoretical value
for the normal distribution is zero, not 3.

These statistics are often computed as a first step in the study of
returns on financial assets. In that case any inference on these
statistics (including the confidence intervals for the mean) should be
considered exploratory, since returns are virtually never i.i.d.

## Value

a data frame with one column for each column of `x` and the following
rows:

- "nobs":

  number of observations,

- "NAs":

  number of `NA`s

- "Minimum":

  minimum,

- "Maximum ":

  maximum,

- "1. Quartile":

  lower quartile,

- "3. Quartile":

  upper quartile,

- "Mean":

  mean,

- "Median":

  median,

- "Sum":

  sum of the values,

- "SE Mean":

  standard error of the mean,

- "LCL Mean":

  lower limit of the CI for the mean,

- "UCL Mean":

  upper limit of the CI for the mean,

- "Variance":

  variance,

- "Stdev":

  standard deviation,

- "Skewness":

  skewness coefficient,

- "Kurtosis":

  excess kurtosis.

## Examples

``` r
## Simulated Monthly Return Data
tS <- timeSeries(matrix(rnorm(12)), timeDate::timeCalendar())
basicStats(tS)
#>                  TS.1
#> nobs        12.000000
#> NAs          0.000000
#> Minimum     -2.345698
#> Maximum      1.084441
#> 1. Quartile -0.917125
#> 3. Quartile  0.315353
#> Mean        -0.442263
#> Median      -0.555542
#> Sum         -5.307153
#> SE Mean      0.265001
#> LCL Mean    -1.025526
#> UCL Mean     0.141000
#> Variance     0.842706
#> Stdev        0.917990
#> Skewness    -0.233217
#> Kurtosis    -0.571935
```
