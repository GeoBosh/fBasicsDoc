# Autocorrelation function plots

Produce plots of the autocorrelation function (ACF), the partial ACF,
the lagged ACF, and the Taylor effect plot.

## Usage

``` r
acfPlot(x, labels = TRUE, ...)
pacfPlot(x, labels = TRUE, ...) 

lacfPlot(x, n = 12, lag.max = 20, type = c("returns", "values"),
    labels = TRUE, ...)

teffectPlot(x, deltas = seq(from = 0.2, to = 3, by = 0.2), lag.max = 10, 
    ymax = NA, standardize = TRUE, labels = TRUE, ...)
```

## Arguments

- x:

  an uni- or multivariate time series of class `"timeSeries"` or any
  other object which can be transformed by the function
  [`as.timeSeries()`](https://geobosh.github.io/fBasicsDoc/reference/fBasics-reexports.md)
  into an object of class `"timeSeries"`.

- labels:

  a logical value, whether or not x- and y-axes should be automatically
  labeled and a default main title should be added to the plot. By
  default `TRUE`.

- n:

  an integer value, the number of lags.

- lag.max:

  maximum lag for which the autocorrelation should be calculated, an
  integer.

- type:

  a character string which specifies the type of the input series,
  either `"returns"` or `"values"`. In the case of a return series as
  input, the required value series is computed by cumulating the
  financial returns: `exp(colCumsums(x))`

- deltas:

  the exponents, a numeric vector, by default ranging from 0.2 to 3.0 in
  steps of 0.2.

- ymax:

  maximum y-axis value on plot. If `NA`, then the value is selected
  automatically.

- standardize:

  a logical value. Should the vector `x` be standardized?

- ...:

  arguments to be passed.

## Details

The following plots are described here:

|               |                                        |
|---------------|----------------------------------------|
| `acfPlot`     | autocorrelation function plot,         |
| `pacfPlot`    | partial autocorrelation function plot, |
| `lacfPlot`    | lagged autocorrelation function plot,  |
| `teffectPlot` | Taylor effect plot.                    |

### Autocorrelation Functions

The functions `acfPlot` and `pacfPlot`, plot and estimate
autocorrelation and partial autocorrelation function. The functions
allow to get a first view on correlations within the time series. The
functions are synonym function calls for R's `acf` and `pacf` from the
the `ts` package.

### Taylor Effect

The "Taylor Effect" describes the fact that absolute returns of
speculative assets have significant serial correlation over long lags.
Even more, autocorrelations of absolute returns are typically greater
than those of squared returns. From these observations the Taylor effect
states, that that the autocorrelations of absolute returns to the the
power of `delta`, `abs(x-mean(x))^delta` reach their maximum at
`delta = 1`. The function `teffect` explores this behaviour. A plot is
created which shows for each lag (from 1 to `max.lag`) the
autocorrelations as a function of the exponent `delta`. In the case that
the above formulated hypothesis is supported, all the curves should peak
at the same value around `delta = 1`.

## Value

for `acfPlot` and `pacfplot`, an object of class `"acf"`, see
[`acf`](https://rdrr.io/r/stats/acf.html);

for `teffectPlot`, a numeric matrix of order `deltas` by `max.lag` with
the values of the autocorrelations;

for `lacfPlot`, a list with the following two elements:

- Rho:

  the autocorrelation function,

- lagged:

  the lagged correlations.

## References

Taylor S.J. (1986); *Modeling Financial Time Series*, John Wiley and
Sons, Chichester.

Ding Z., Granger C.W.J., Engle R.F. (1993); *A long memory property of
stock market returns and a new model*, Journal of Empirical Finance 1,
83.

## See also

[`seriesPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`returnPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`cumulatedPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`drawdownPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md)

[`qqnormPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md),
[`qqnigPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md),
[`qqghtPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md),
[`qqgldPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md)

[`histPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-histPlot.md),
[`densityPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-histPlot.md),
[`logDensityPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-histPlot.md)

[`boxPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-boxPlot.md),
[`boxPercentilePlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-boxPlot.md)

[`scalinglawPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-scalinglawPlot.md)

[`returnSeriesGUI`](https://geobosh.github.io/fBasicsDoc/reference/plot-returnSeriesGUI.md)

## Examples

``` r
## data
data(LPP2005REC, package = "timeSeries")
SPI <- LPP2005REC[, "SPI"]
plot(SPI, type = "l", col = "steelblue", main = "SP500")
abline(h = 0, col = "grey")


## Taylor Effect:
teffectPlot(SPI)
```
