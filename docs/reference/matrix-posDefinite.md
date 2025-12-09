# Positive definite matrices

Checks if a matrix is positive definite and/or forces a matrix to be
positive definite.

## Usage

``` r
isPositiveDefinite(x)
makePositiveDefinite(x)
```

## Arguments

- x:

  a square numeric matrix.

## Details

The function `isPositiveDefinite` checks if a square matrix is positive
definite.

The function `makePositiveDefinite` forces a matrix to be positive
definite.

## Author

Korbinian Strimmer.

## Examples

``` r
# the 3x3 Pascal Matrix is positive define 
isPositiveDefinite(pascal(3))                
#> [1] TRUE
```
