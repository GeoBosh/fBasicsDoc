# Quantile-quantile plots

Produce quantile-quantile plots for the normal, inverse Gaussian,
generalized hyperbolic Student-t and the generalized lambda
distributions.

## Usage

``` r
qqnormPlot(x, labels = TRUE, col = "steelblue", pch = 19,
    title = TRUE, mtext = TRUE, grid = FALSE, rug = TRUE, 
    scale = TRUE, ...) 
qqnigPlot(x, labels = TRUE, col = "steelblue", pch = 19,
    title = TRUE, mtext = TRUE, grid = FALSE, rug = TRUE, 
    scale = TRUE, ...) 
qqghtPlot(x, labels = TRUE, col = "steelblue", pch = 19,
    title = TRUE, mtext = TRUE, grid = FALSE, rug = TRUE, 
    scale = TRUE, ...) 
qqgldPlot(x, labels = TRUE, col = "steelblue", pch = 19,
    title = TRUE, mtext = TRUE, grid = FALSE, rug = TRUE, 
    scale = TRUE, ...)
```

## Arguments

- x:

  an object of class `"timeSeries"` or any other object which can be
  transformed by `as.timeSeries`.

- labels:

  a logical flag, should the plot be returned with default labels and
  decorated in an automated way? By default `TRUE`.

- col:

  the color for the series. In the univariate case use just a color name
  like the default, `col = "steelblue"`, in the multivariate case we
  recommend to select the colors from a color palette, e.g.
  `col = heat.colors(ncol(x))`.

- pch:

  an integer value, by default 19. Which plot character should be used
  in the plot?

- title:

  a logical flag, by default `TRUE`. Should a default title be added to
  the plot?

- mtext:

  a logical flag, by default `TRUE`. Should a marginal text be printed
  on the third site of the graph?

- grid:

  a logical flag, should a grid be added to the plot? By default `TRUE`.

- rug:

  a logical flag, by default `TRUE`. Should a rug representation of the
  data be added to the plot?

- scale:

  a logical flag, by default `TRUE`. Should the plot be for the scaled
  time series? Used by `qqnormPlot` only, ignored silently by the
  others.

- ...:

  optional arguments passed to
  [`plot()`](https://rdrr.io/r/graphics/plot.default.html).

## Details

`qqnormPlot` produces a tailored Normal quantile-quantile plot.

`qqnigPlot` produces a tailored NIG quantile-quantile plot.

`qqghtPlot` produces a tailored GHT quantile-quantile plot.

`qqgldPlot` produces a tailored GLD quantile-quantile plot.

## Value

a list containing some of the quantities computed for the plot,
invisibly. Currently contains the following components:

- x:

  the quantiles of the reference distribution, used for the x-axis,

- y:

  the (possibly scaled) ordered values of the time series, used for the
  y-axis.

The list has attribute `"control"` containing the parameters of the
fitted distribution.

## Author

Diethelm Wuertz for the Rmetrics R-port.

## See also

[`seriesPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`returnPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`cumulatedPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`drawdownPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md)

[`histPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-histPlot.md),
[`densityPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-histPlot.md),
[`logDensityPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-histPlot.md)

[`boxPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-boxPlot.md),
[`boxPercentilePlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-boxPlot.md)

[`acfPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-acfPlot.md),
[`pacfPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-acfPlot.md),
[`teffectPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-acfPlot.md),
[`lacfPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-acfPlot.md)

[`scalinglawPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-scalinglawPlot.md)

[`returnSeriesGUI`](https://geobosh.github.io/fBasicsDoc/reference/plot-returnSeriesGUI.md)

## Examples

``` r
## data
data(LPP2005REC, package = "timeSeries")
SPI <- LPP2005REC[, "SPI"]
plot(SPI, type = "l", col = "steelblue", main = "SP500")
abline(h = 0, col = "grey")

   
qqnormPlot(SPI) 
```
