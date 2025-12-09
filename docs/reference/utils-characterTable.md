# Table of characters

Displays a table of numerical equivalents to Latin characters.

## Usage

``` r
characterTable(font = 1, cex = 0.7)
```

## Arguments

- cex:

  a numeric value, determines the character size, the default size is
  0.7.

- font:

  an integer value, the number of the `font`, by default font number 1.

## Value

displays a table with the characters of the requested font. The
character on line `"xy"` and column `"z"` of the table has code
`"\xyz"`, e.g `cat("\126")` prints: V for font number 1. These codes can
be used as any other characters.

## Note

What happens with non-ASCII characters in plots is system dependent and
depends on the graphics device, as well. Use of such characters is not
recommended for portable code.

## See also

[`colorTable`](https://geobosh.github.io/fBasicsDoc/reference/utils-colorTable.md),
[`symbolTable`](https://geobosh.github.io/fBasicsDoc/reference/utils-symbolTable.md)

[`points`](https://rdrr.io/r/graphics/points.html) for use of characters
in plotting

## Examples

``` r
## Character Table for Font 1:
# characterTable(font = 1)
```
