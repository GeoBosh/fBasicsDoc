# Hilbert matrix

Creates a Hilbert matrix.

## Usage

``` r
hilbert(n)
```

## Arguments

- n:

  an integer value, the dimension of the square matrix.

## Details

An \\n,n\\ matrix with \\(i,j)\\th element equal to \\1/(i+j-1)\\ is
said to be a Hilbert matrix of order \\n\\. Hilbert matrices are
symmetric and positive definite.

They are canonical examples of ill-conditioned matrices, making them
notoriously difficult to use in numerical computation. For example, the
2-norm condition number of a 5x5 Hilbert matrix above is about 4.8e5.

## Value

a matrix

## References

Hilbert D., *Collected papers*, vol. II, article 21.

Beckermann B, (2000); *The condition number of real Vandermonde, Krylov
and positive definite Hankel matrices*, Numerische Mathematik 85,
553–577, 2000.

Choi, M.D., (1983); *Tricks or Treats with the Hilbert Matrix*, American
Mathematical Monthly 90, 301–312, 1983.

Todd, J., (1954); *The Condition Number of the Finite Segment of the
Hilbert Matrix*, National Bureau of Standards, Applied Mathematics
Series 39, 109–116.

Wilf, H.S., (1970); *Finite Sections of Some Classical Inequalities*,
Heidelberg, Springer.

## Examples

``` r
## Create a Hilbert Matrix:
H = hilbert(5)
H                              
#>           [,1]      [,2]      [,3]      [,4]      [,5]
#> [1,] 1.0000000 0.5000000 0.3333333 0.2500000 0.2000000
#> [2,] 0.5000000 0.3333333 0.2500000 0.2000000 0.1666667
#> [3,] 0.3333333 0.2500000 0.2000000 0.1666667 0.1428571
#> [4,] 0.2500000 0.2000000 0.1666667 0.1428571 0.1250000
#> [5,] 0.2000000 0.1666667 0.1428571 0.1250000 0.1111111
```
