# Sample L-moments

Computes L-moments from an empirical sample data set.

## Usage

``` r
sampleLmoments(x, rmax = 4)
```

## Arguments

- x:

  numeric vector, the sample values.

- rmax:

  an integer value, the number of L-moments to be returned.

## Value

a named numeric vector of length `rmax` with names
`c("L1", "L2", ..., "L<rmax>")`

## Author

Diethelm Wuertz

## Examples

``` r
x <- rt(100, 4)
   
sampleLmoments(x)
#>           L1           L2           L3           L4 
#>  0.085554392  0.727388215 -0.005733317  0.145122744 
```
