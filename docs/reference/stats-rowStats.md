# Row statistics

Functions to compute row statistical properties of financial and
economic time series data.  

The functions are:

|                |                                             |
|----------------|---------------------------------------------|
| `rowStats`     | calculates row statistics,                  |
| `rowSds`       | calculates row standard deviations,         |
| `rowVars`      | calculates row variances,                   |
| `rowSkewness`  | calculates row skewness,                    |
| `rowKurtosis`  | calculates row kurtosis,                    |
| `rowMaxs`      | calculates maximum values in each row,      |
| `rowMins`      | calculates minimum values in each row,      |
| `rowProds`     | computes product of all values in each row, |
| `rowQuantiles` | computes quantiles of each row.             |

## Usage

    rowStats(x, FUN, ...)

    <!-- % rowSums(x, \dots) -->
    <!-- % rowMeans(x, \dots) -->

    rowSds(x, ...)
    rowVars(x, ...)
    rowSkewness(x, ...)
    rowKurtosis(x, ...)
    rowMaxs(x, ...)
    rowMins(x, ...)
    rowProds(x, ...)
    rowQuantiles(x, prob = 0.05, ...)

    rowStdevs(x, ...)
    rowAvgs(x, ...)

## Arguments

- FUN:

  a function name, the statistical function to be applied.

- prob:

  a numeric value, the probability with value in \[0,1\].

- x:

  a rectangular object which can be transformed into a matrix by the
  function `as.matrix`.

- ...:

  arguments to be passed.

## Value

each function returns a numeric vector of the statistics

## See also

[`apply`](https://rdrr.io/r/base/apply.html)

## Examples

``` r
## Simulated Return Data in Matrix Form:
x <- matrix(rnorm(10*10), nrow = 10)
     
rowStats(x, FUN = mean)
#>  [1] -0.07130207  0.41613040  0.01773426  0.33939605  0.18244729  0.19210571
#>  [7] -0.22218828  0.23648095 -0.14000824 -0.06758812
rowMaxs(x)  
#>  [1] 0.6135046 1.4881833 1.6704000 2.9194556 2.4254361 1.7637915 1.0885857
#>  [8] 2.1724900 0.9874172 1.6041385
```
