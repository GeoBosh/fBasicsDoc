# Time series box plots

Produce a box plot or a box percentile plot.

## Usage

``` r
boxPlot(x, col = "steelblue", title = TRUE, ...)
boxPercentilePlot(x, col = "steelblue", title = TRUE, ...)
```

## Arguments

- x:

  an object of class `"timeSeries"` or any other object which can be
  transformed by the function `as.timeSeries` into an object of class
  `"timeSeries"`.

- col:

  the color for the series. In the univariate case use just a color name
  like the default, `col = "steelblue"`, in the multivariate case we
  recommend to select the colors from a color palette, e.g.
  `col = heat.colors(ncol(x))`.

- title:

  a logical flag, by default `TRUE`. Should a default title added to the
  plot?

- ...:

  optional arguments to be passed to
  [`boxplot`](https://rdrr.io/r/graphics/boxplot.html).

## Details

`boxPlot` produces a side-by-side standard box plot,

`boxPercentilePlot` produces a side-by-side box-percentile plot.

## Value

`NULL`

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
LPP <- LPP2005REC[, 1:6]
plot(LPP, type = "l", col = "steelblue", main = "SP500")
abline(h = 0, col = "grey")

   
boxPlot(LPP) 
```
