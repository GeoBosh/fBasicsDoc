# Set and retrieve column/row names

Sets and retrieves column and row names. The functions are for
compatibility with SPlus.

## Usage

``` r
colIds(x, ...)
rowIds(x, ...)
```

## Arguments

- x:

  a numeric matrix.

- ...:

  passed on to `colnames` or `rownames`.

## Details

Usually in R the functions `colnames` and `rownames` are used to
retrieve and set the names of matrices. The functions `rowIds` and
`colIds`, are S-Plus like synonyms.

## Examples

``` r
## Create Pascal Matrix:
P <- pascal(3)
P
#>      [,1] [,2] [,3]
#> [1,]    1    1    1
#> [2,]    1    2    3
#> [3,]    1    3    6
 
rownames(P) <- letters[1:3]
P   
#>   [,1] [,2] [,3]
#> a    1    1    1
#> b    1    2    3
#> c    1    3    6
   
colIds(P) <- as.character(1:3)
P                            
#>   1 2 3
#> a 1 1 1
#> b 1 2 3
#> c 1 3 6
```
