# Table of symbols

Displays a table of plot characters and symbols.

## Usage

``` r
symbolTable(font = par('font'), cex = 0.7)
```

## Arguments

- cex:

  a numeric value, determines the character size, the default size is
  0.7.

- font:

  an integer value, the number of the `font`, by default font number 1.

## Value

displays a table with the plot characters and symbols numbered from 0 to
255 and returns invisibly the name of the font.

## Note

Symbols with codes on the range 128-255 are not legitimate in some
locales, most notably UTF-8. Moreover, what happens with non-ASCII
characters in plots is system dependent and depends on the graphics
device, as well. Use of such characters is not recommended for portable
code.

From version 4031.95 of package `fBasics`, the characters are always
defined as Latin1. In particular, in UTF8 locales the system converts
them internally to UTF8. Still some symbols are not usable and non-ASCII
symbols are not recommended, as pointed out above. For details, see the
help page of [`points()`](https://rdrr.io/r/graphics/points.html), in
particular the discussion of its argument `pch`.

## See also

[`characterTable`](https://geobosh.github.io/fBasicsDoc/reference/utils-characterTable.md),
[`colorTable`](https://geobosh.github.io/fBasicsDoc/reference/utils-colorTable.md)

[`pdf`](https://rdrr.io/r/grDevices/pdf.html) for discussion of
encodings for the pdf device

## Examples

``` r
# symbolTable()
```
