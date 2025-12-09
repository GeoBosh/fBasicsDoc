# Polynomial distributed lags

Creates a regressor matrix for polynomial distributed lags.

## Usage

``` r
pdl(x, d = 2, q = 3, trim = FALSE)
```

## Arguments

- x:

  a numeric vector.

- d:

  an integer specifying the order of the polynomial.

- q:

  an integer specifying the number of lags to use in creating polynomial
  distributed lags. This must be greater than `d`.

- trim:

  a logical flag; if `TRUE`, the missing values at the beginning of the
  returned matrix will be trimmed.

## See also

[`tslag`](https://geobosh.github.io/fBasicsDoc/reference/matrix-tslag.md)

## Examples

``` r
## pdl -
   #                                      
```
