# Grid vector coordinates

Creates rectangular grid coordinates from two vectors.

## Usage

``` r
gridVector(x, y = NULL)
```

## Arguments

- x,y:

  numeric vectors

## Details

The grid is obtained by pairing each element of `y` with all elements of
`x`. The `X` and `Y` coordinates of the points are stored in separate
vectors. This is convenient, for example, for plotting. It can be useful
also for brute force optimisation or simulation.

If `y` is `NULL`, the default, then `y = x`.

## Value

a list with two components, `X` and `Y`, giving the coordinates which
span the bivariate grid.

## See also

[`expand.grid`](https://rdrr.io/r/base/expand.grid.html)

## Examples

``` r
## a small grid vector with row and col transformations
gridVector(0:2)
#> $X
#> [1] 0 1 2 0 1 2 0 1 2
#> 
#> $Y
#> [1] 0 0 0 1 1 1 2 2 2
#> 
data.frame(gridVector(0:2))
#>   X Y
#> 1 0 0
#> 2 1 0
#> 3 2 0
#> 4 0 1
#> 5 1 1
#> 6 2 1
#> 7 0 2
#> 8 1 2
#> 9 2 2
do.call("rbind", gridVector(0:2))
#>   [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9]
#> X    0    1    2    0    1    2    0    1    2
#> Y    0    0    0    1    1    1    2    2    2

gridVector(0:2, 0:3)
#> $X
#>  [1] 0 1 2 0 1 2 0 1 2 0 1 2
#> 
#> $Y
#>  [1] 0 0 0 1 1 1 2 2 2 3 3 3
#> 

## grid over a unit square
gridVector((0:10)/10) # equivalently: gridVector((0:10)/10, (0:10)/10)
#> $X
#>   [1] 0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0 0.0 0.1 0.2 0.3 0.4 0.5 0.6
#>  [19] 0.7 0.8 0.9 1.0 0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0 0.0 0.1 0.2
#>  [37] 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0 0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9
#>  [55] 1.0 0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0 0.0 0.1 0.2 0.3 0.4 0.5
#>  [73] 0.6 0.7 0.8 0.9 1.0 0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0 0.0 0.1
#>  [91] 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0 0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8
#> [109] 0.9 1.0 0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0
#> 
#> $Y
#>   [1] 0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.1 0.1 0.1 0.1 0.1 0.1 0.1
#>  [19] 0.1 0.1 0.1 0.1 0.2 0.2 0.2 0.2 0.2 0.2 0.2 0.2 0.2 0.2 0.2 0.3 0.3 0.3
#>  [37] 0.3 0.3 0.3 0.3 0.3 0.3 0.3 0.3 0.4 0.4 0.4 0.4 0.4 0.4 0.4 0.4 0.4 0.4
#>  [55] 0.4 0.5 0.5 0.5 0.5 0.5 0.5 0.5 0.5 0.5 0.5 0.5 0.6 0.6 0.6 0.6 0.6 0.6
#>  [73] 0.6 0.6 0.6 0.6 0.6 0.7 0.7 0.7 0.7 0.7 0.7 0.7 0.7 0.7 0.7 0.7 0.8 0.8
#>  [91] 0.8 0.8 0.8 0.8 0.8 0.8 0.8 0.8 0.8 0.9 0.9 0.9 0.9 0.9 0.9 0.9 0.9 0.9
#> [109] 0.9 0.9 1.0 1.0 1.0 1.0 1.0 1.0 1.0 1.0 1.0 1.0 1.0
#> 
```
