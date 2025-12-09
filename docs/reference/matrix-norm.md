# Matrix norm

Computes the norm of a matrix.

## Usage

``` r
norm2(x, p = 2)
```

## Arguments

- x:

  a numeric matrix.

- p:

  an integer value, `1`, `2` or `Inf`, see section ‘Details’.

## Details

The function `norm2` computes the norm of a matrix. Three choices are
possible:

- `p=1`:

  The maximum absolute column sum norm which is defined as the maximum
  of the sum of the absolute valued elements of columns of the matrix.

- `p=2`:

  The spectral norm is "the norm" of a matrix `X`. This value is
  computed as the square root of the maximum eigenvalue of `CX`, where
  `C` is the conjugate transpose.

- `p=Inf`:

  The maximum absolute row sum norm is defined as the maximum of the sum
  of the absolute valued elements of rows of the matrix.

## Note

Since [`base::norm()`](https://rdrr.io/r/base/norm.html) has become
available in the R base environment, the function
[`fBasics::norm()`](https://rdrr.io/r/base/norm.html) has become
obsolete. To avoid conflicts with
[`norm()`](https://rdrr.io/r/base/norm.html) we have renamed the
fBasics' one to `norm2`.

## Value

the requested norm of the matrix, a non-negative number

## References

Golub, van Loan, (1996); *Matrix Computations*, 3rd edition. Johns
Hopkins University Press.

## Examples

``` r
## Create Pascal Matrix:
P <- pascal(5)
P                  
#>      [,1] [,2] [,3] [,4] [,5]
#> [1,]    1    1    1    1    1
#> [2,]    1    2    3    4    5
#> [3,]    1    3    6   10   15
#> [4,]    1    4   10   20   35
#> [5,]    1    5   15   35   70
     
## Return the Norm of the Matrix:                      
norm2(P)                                                       
#> [1] 92.29043
```
