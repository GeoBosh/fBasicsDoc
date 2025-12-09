# Column and row vectors

Creates a column or row vector from a numeric vector.

## Usage

``` r
colVec(x)
rowVec(x)
```

## Arguments

- x:

  a numeric vector.

## Details

`colVec` and `rowVec` transform a vector into a column and row vector,
respectively. A column vector is a matrix object with one column, and a
row vector is a matrix object with one row.

## Examples

``` r
x = rnorm(5)
   
colVec(x)
#>           [,1]
#> [1,] 0.4934692
#> [2,] 1.9424086
#> [3,] 0.6254734
#> [4,] 2.0612688
#> [5,] 0.9423640
rowVec(x)                        
#>           [,1]     [,2]      [,3]     [,4]     [,5]
#> [1,] 0.4934692 1.942409 0.6254734 2.061269 0.942364
```
