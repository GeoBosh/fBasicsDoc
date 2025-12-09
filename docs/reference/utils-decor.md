# Functions for decorating plots

Functions for decorating plots.

## Usage

``` r
decor()

hgrid(ny = NULL, ...) 
vgrid(nx = NULL, ...) 

boxL(col = "white") 
box_(col = c("white", "black")) 

copyright()
```

## Arguments

- col:

  the color of the background, `"black"` and foreground `"white"` lines
  of the box.

- nx, ny:

  number of cells of the grid in `x` or `y` direction. When `NULL`, as
  per default, the grid aligns with the tick marks on the corresponding
  default axis (i.e., tick marks as computed by axTicks).

- ...:

  additional arguments passed to the
  [`grid()`](https://rdrr.io/r/graphics/grid.html) function.

## Details

`decor` is equivalent to `hgrid()` followed by `boxL()`.

`hgrid` creates horizontal grid lines.

`vgrid` creates vertical grid lines.

`boxL` creates an L-shaped box

`box_` creates a bottom line box.

`copyright` adds Rmetrics copyright to a plot.

## Examples

``` r
plot(x = rnorm(100), type = "l", col = "red", 
     xlab = "", ylab = "Variates", las = 1)
title("Normal Deviates", adj = 0)
hgrid()
boxL()
copyright()
```
