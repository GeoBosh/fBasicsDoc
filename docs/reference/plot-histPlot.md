# Histogram and density plots

Produce tailored histogram plots and kernel density/log-density estimate
plots.

## Usage

``` r
histPlot(x, labels = TRUE, col = "steelblue", fit = TRUE, 
    title = TRUE, grid = TRUE, rug = TRUE, skip = FALSE, ...) 
densityPlot(x, labels = TRUE, col = "steelblue", fit = TRUE, hist = TRUE, 
    title = TRUE, grid = TRUE, rug = TRUE, skip = FALSE, ...)    
logDensityPlot(x, labels = TRUE, col = "steelblue", robust = TRUE,  
    title = TRUE, grid = TRUE, rug = TRUE, skip = FALSE, ...)
```

## Arguments

- x:

  an object of class `"timeSeries"`.

- labels:

  a logical flag, should the plot be returned with default labels and
  decorated in an automated way? By default `TRUE`.

- col:

  the color for the series. In the univariate case use just a color name
  like the default, `col = "steelblue"`, in the multivariate case we
  recommend to select the colors from a color palette, e.g.
  `col = heat.colors(ncol(x))`.

- fit:

  a logical flag, should a fit be added to the plot?

- hist:

  a logical flag, by default `TRUE`. Should a histogram be laid under
  the plot?

- title:

  a logical flag, by default `TRUE`. Should a default title be added to
  the plot?

- grid:

  a logical flag, should a grid be added to the plot? By default `TRUE`.

- rug:

  a logical flag, by default TRUE. Should a rug representation of the
  data be added to the plot?

- skip:

  a logical flag, should zeros be skipped in the return Series?

- robust:

  a logical flag, by default `TRUE`. Should a robust fit be added to the
  plot?

- ...:

  optional arguments to be passed on.

## Details

`histPlot` produces a tailored histogram plot.

`densityPlot` produces a tailored kernel density estimate plot.

`logDensityPlot` produces a tailored log kernel density estimate plot.

## Value

`NULL`, invisibly. The functions are used for the side effect of
producing a plot.

## See also

[`seriesPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`returnPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`cumulatedPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md),
[`drawdownPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-seriesPlot.md)

[`qqnormPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md),
[`qqnigPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md),
[`qqghtPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md),
[`qqgldPlot`](https://geobosh.github.io/fBasicsDoc/reference/plot-qqPlot.md)

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

   
histPlot(SPI) 

   
densityPlot(SPI) 
```
