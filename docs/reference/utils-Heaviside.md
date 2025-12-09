# Heaviside and related functions

Functions which compute the Heaviside and related functions. These
include the Heaviside function, the sign function, the delta function,
the boxcar function, and the ramp function.

## Usage

``` r
Heaviside(x, a = 0)
Sign(x, a = 0)
Delta(x, a = 0)
Boxcar(x, a = 0.5)
Ramp(x, a = 0)
```

## Arguments

- x:

  a numeric vector.

- a:

  a numeric value, the location of the break.

## Details

`Heaviside` computes the Heaviside unit step function. `Heaviside` is 1
for `x > a`, `1/2` for `x = a`, and `0` for `x < a`.

`Sign` computes the sign function. `Sign` is `1` for `x > a`, `0` for
`x = a`, and `-1` for `x < a`.

`Delta` computes the delta function. `Delta` is defined as:
`Delta(x) = d/dx H(x-a)`.

`Boxcar` computes the boxcar function. `Boxcar` is defined as:
`Boxcar(x) = H(x+a) - H(x-a)`.

`Ramp` computes ramp function. The ramp function is defined as:
`Ramp(x) = (x-a) * H(x-a)`.

## Value

numeric vector

## Note

The Heaviside function is used in the implementation of the skew Normal,
Student-t, and Generalized Error distributions, distributions functions
which play an important role in modelling GARCH processes.

## See also

`GarchDistribution`, `GarchDistributionFits`

## References

Weisstein W. (2004);
*http://mathworld.wolfram.com/HeavisideStepFunction.html*, Mathworld.

## Examples

``` r
x <- sort(round(c(-1, -0.5, 0, 0.5, 1, 5*rnorm(5)), 2))

h <- Heaviside(x)
s <- Sign(x)
d <- Delta(x)
Pi <- Boxcar(x)
r <- Ramp(x)

cbind(x = x, Step = h, Signum = s, Delta = d, Pi = Pi, R = r)        
#>           x Step Signum Delta   Pi    R
#>  [1,] -2.02  0.0     -1     0  0.0 0.00
#>  [2,] -1.00  0.0     -1     0  0.0 0.00
#>  [3,] -0.82  0.0     -1     0  0.0 0.00
#>  [4,] -0.50  0.0     -1     0 -0.5 0.00
#>  [5,]  0.00  0.5      0   Inf -1.0 0.00
#>  [6,]  0.50  1.0      1     0 -0.5 0.50
#>  [7,]  1.00  1.0      1     0  0.0 1.00
#>  [8,]  3.48  1.0      1     0  0.0 3.48
#>  [9,]  4.01  1.0      1     0  0.0 4.01
#> [10,]  4.30  1.0      1     0  0.0 4.30
```
