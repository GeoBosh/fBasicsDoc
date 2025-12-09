# The inverse of a matrix

Computes the inverse of a matrix.

## Usage

``` r
inv(x)
```

## Arguments

- x:

  a numeric matrix.

## Value

a matrix

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
         
## Compute the Inverse Matrix:
inv(P)
#>      [,1] [,2] [,3] [,4] [,5]
#> [1,]    5  -10   10   -5    1
#> [2,]  -10   30  -35   19   -4
#> [3,]   10  -35   46  -27    6
#> [4,]   -5   19  -27   17   -4
#> [5,]    1   -4    6   -4    1
   
## Check:
inv(P) %*% P    
#>      [,1] [,2] [,3] [,4] [,5]
#> [1,]    1    0    0    0    0
#> [2,]    0    1    0    0    0
#> [3,]    0    0    1    0    0
#> [4,]    0    0    0    1    0
#> [5,]    0    0    0    0    1
   
## Alternatives:
chol2inv(chol(P))
#>      [,1] [,2] [,3] [,4] [,5]
#> [1,]    5  -10   10   -5    1
#> [2,]  -10   30  -35   19   -4
#> [3,]   10  -35   46  -27    6
#> [4,]   -5   19  -27   17   -4
#> [5,]    1   -4    6   -4    1
solve(P)                     
#>      [,1] [,2] [,3] [,4] [,5]
#> [1,]    5  -10   10   -5    1
#> [2,]  -10   30  -35   19   -4
#> [3,]   10  -35   46  -27    6
#> [4,]   -5   19  -27   17   -4
#> [5,]    1   -4    6   -4    1
```
