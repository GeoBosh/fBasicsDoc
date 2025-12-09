# Generic functions extensions

Basic extensions which add and/or modify additional functionality which
is not available in R's basic packages.

## Usage

``` r
# Default S3 method
stdev(x, na.rm = FALSE)

# Default S3 method
termPlot(model, ...)
```

## Arguments

- model:

  a fitted model object.

- x:

  an object for which to compute the standard deviation.

- na.rm:

  a logical value - should the NA values be removed.

- ...:

  arguments to be passed.

## Details

`stdev` and `termPlot` are generic functions with default methods
[`stats::sd`](https://rdrr.io/r/stats/sd.html) and
[`stats::termplot`](https://rdrr.io/r/stats/termplot.html),
respectively.

## See also

[`sd`](https://rdrr.io/r/stats/sd.html),
[`termplot`](https://rdrr.io/r/stats/termplot.html)
