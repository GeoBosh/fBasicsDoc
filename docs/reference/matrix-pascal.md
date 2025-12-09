# Pascal matrix

Creates a Pascal matrix.

## Usage

``` r
pascal(n)
```

## Arguments

- n:

  an integer value, the dimension of the square matrix.

## Details

The function `pascal` generates a Pascal matrix of order `n` which is a
symmetric positive definite matrix with integer entries made up from
Pascal's triangle. The determinant of a Pascal matrix is 1. The inverse
of a Pascal matrix has integer entries. If `lambda` is an eigenvalue of
a Pascal matrix, then `1/lambda` is also an eigenvalue of the matrix.
Pascal matrices are ill-conditioned.

## References

Call G.S., Velleman D.J., (1993); *Pascal's matrices*, American
Mathematical Monthly 100, 372–376.

Edelman A., Strang G., (2004); *Pascal Matrices*, American Mathematical
Monthly 111, 361–385.

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
   
## Determinant
det(pascal(5)) 
#> [1] 1
det(pascal(10))   
#> [1] 1
det(pascal(15))   
#> [1] 1.001116
det(pascal(20))                                       
#> [1] 59.77116
```
