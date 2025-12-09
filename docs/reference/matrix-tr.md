# Trace of a matrix

Computes the trace of a matrix.

## Usage

``` r
tr(x)
```

## Arguments

- x:

  a numeric matrix.

## Details

`tr` computes the trace of a square matrix, i.e., the sum of its
diagonal elements.

If the matrix is not square, `tr` returns `NA`.

## References

Golub, van Loan, (1996); *Matrix Computations*, 3rd edition. Johns
Hopkins University Press.

## Examples

``` r
## Create Pascal Matrix:
P = pascal(3)
P
#>      [,1] [,2] [,3]
#> [1,]    1    1    1
#> [2,]    1    2    3
#> [3,]    1    3    6
  
tr(P)                                  
#> [1] 9
```
