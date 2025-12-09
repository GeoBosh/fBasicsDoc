# Kronecker product

Computes the Kronecker product of two matrices.

## Usage

``` r
kron(x, y)
```

## Arguments

- x, y:

  numeric matrices.

## Details

The *Kronecker product* can be computed using the operator `%x%` or
alternatively using the function `kron` for SPlus compatibility.

## Note

`kron` is a synonym to `%x%`.

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
   
## Return the Kronecker Product                     
kron(P, diag(3))
#>       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9]
#>  [1,]    1    0    0    1    0    0    1    0    0
#>  [2,]    0    1    0    0    1    0    0    1    0
#>  [3,]    0    0    1    0    0    1    0    0    1
#>  [4,]    1    0    0    2    0    0    3    0    0
#>  [5,]    0    1    0    0    2    0    0    3    0
#>  [6,]    0    0    1    0    0    2    0    0    3
#>  [7,]    1    0    0    3    0    0    6    0    0
#>  [8,]    0    1    0    0    3    0    0    6    0
#>  [9,]    0    0    1    0    0    3    0    0    6
P %x% diag(3)                        
#>       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9]
#>  [1,]    1    0    0    1    0    0    1    0    0
#>  [2,]    0    1    0    0    1    0    0    1    0
#>  [3,]    0    0    1    0    0    1    0    0    1
#>  [4,]    1    0    0    2    0    0    3    0    0
#>  [5,]    0    1    0    0    2    0    0    3    0
#>  [6,]    0    0    1    0    0    2    0    0    3
#>  [7,]    1    0    0    3    0    0    6    0    0
#>  [8,]    0    1    0    0    3    0    0    6    0
#>  [9,]    0    0    1    0    0    3    0    0    6
```
