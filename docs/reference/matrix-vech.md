# Stacking vectors and matrices

Stacks either a lower triangle matrix or a matrix.

## Usage

``` r
vec(x)
vech(x)
```

## Arguments

- x:

  a numeric matrix.

## Details

The function `vec` implements the operator that stacks a matrix as a
column vector, to be more precise in a matrix with one column. \\vec(X)
= (X\_{11}, X\_{21}, ..., X\_{N1}, X\_{12}, X\_{22}, ..., X\_{NN})\\.

The function `vech` implements the operator that stacks the lower
triangle of a NxN matrix as an N(N+1)/2x1 vector: \\vech(X) =(X\_{11},
X\_{21}, X\_{22}, X\_{31}, ..., X\_{NN})\\, to be more precise in a
matrix with one row.

## Examples

``` r
## Create Pascal Matrix:
P = pascal(3)
   
## Stack the matrix
vec(P) 
#>       [,1]
#>  [1,]    1
#>  [2,]    1
#>  [3,]    1
#>  [4,]    1
#>  [5,]    2
#>  [6,]    3
#>  [7,]    1
#>  [8,]    3
#>  [9,]    6
   
## Stack the lower triangle
vech(P)                                        
#>      [,1] [,2] [,3] [,4] [,5] [,6]
#> [1,]    1    1    1    2    3    6
```
