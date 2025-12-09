# The rank of a matrix

Computes the rank of a matrix.

## Usage

``` r
rk(x, method = c("qr", "chol"))
```

## Arguments

- x:

  a numeric matrix.

- method:

  a character string. For `method = "qr"` the rank is computed as
  `qr(x)\$rank`, or alternatively for `method = "chol"` the rank is
  computed as `attr(chol(x, pivot = TRUE), "rank")`.

## Details

The function `rk` computes the rank of a matrix which is the dimension
of the range of the matrix corresponding to the number of linearly
independent rows or columns of the matrix, or to the number of nonzero
singular values.

The rank of a matrix is also named linear map.

## References

Golub, van Loan, (1996); *Matrix Computations*, 3rd edition. Johns
Hopkins University Press.

## Examples

``` r
## Create Pascal Matrix:
P = pascal(5)
P
#>      [,1] [,2] [,3] [,4] [,5]
#> [1,]    1    1    1    1    1
#> [2,]    1    2    3    4    5
#> [3,]    1    3    6   10   15
#> [4,]    1    4   10   20   35
#> [5,]    1    5   15   35   70
   
## Compute the Rank:
rk(P)
#> [1] 5
rk(P, "chol")                                
#> [1] 5
```
