# Lagged or leading vector/matrix

Creates a lagged or leading vector/matrix of selected order(s).

## Usage

``` r
tslag(x, k = 1, trim = FALSE)
```

## Arguments

- k:

  an integer value, the number of positions the new series is to lag or
  to lead the input series.

- x:

  a numeric vector or matrix, missing values are allowed.

- trim:

  a logical flag, if TRUE, the missing values at the beginning ans/or
  end of the returned series will be trimmed. The default value is
  FALSE.

## See also

[`pdl`](https://geobosh.github.io/fBasicsDoc/reference/matrix-pdl.md)

## Examples

``` r
## tslag -
```
