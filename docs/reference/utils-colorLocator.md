# Named colors in R

Displays R's 657 named colors for selection and returns optionally R's
color names.

## Usage

``` r
colorLocator(locator = FALSE, cex.axis = 0.7)
colorMatrix()
```

## Arguments

- locator:

  logical, if true, [`locator`](https://rdrr.io/r/graphics/locator.html)
  is used for interactive selection of color names, default is `FALSE`.

- cex.axis:

  size of axis labels.

## Value

Color Locator:

`colorsLocator()` generates a plot with R colors and, when `locator` is
true, returns matrix with graph coordinates and names of colors
selected. `colorsMatrix()` quietly returns the matrix of names.

## Details

Color Locator:

The `colorLocator` function plots R's 657 named colors. If
`locator=TRUE` then you can interactively point and click to select the
colors for which you want names. To end selection, right click on the
mouse and select 'Stop', then R returns the selected color names.

The functions used here are wrappers to the functions provided by Tomas
Aragon in the contributed R package `epitools`.

## See also

[`colorPalette`](https://geobosh.github.io/fBasicsDoc/reference/utils-colorPalette.md),
[`colorTable`](https://geobosh.github.io/fBasicsDoc/reference/utils-colorTable.md).

## Examples

``` r
 colorLocator()
```
