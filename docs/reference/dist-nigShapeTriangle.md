# NIG Shape Triangle

Plots the normal inverse Gaussian Shape Triangle.

## Usage

``` r
nigShapeTriangle(object, add = FALSE, labels = TRUE, ...)
```

## Arguments

- object:

  an object of class `"fDISTFIT"` as returned by the function `nigFit`.

- add:

  a logical value. Should another point added to the NIG shape triangle?
  By default FALSE, a new plot will be created.

- labels:

  a logical flag by default `TRUE`. Should the logarithm of the density
  be returned?

- ...:

  arguments to be passed to the function `integrate`.

## Value

displays the parameters of fitted distributions in the NIG shape
triangle.

## Author

David Scott for code implemented from R's contributed package
`HyperbolicDist`.

## References

Atkinson, A.C. (1982); *The simulation of generalized inverse Gaussian
and hyperbolic random variables*, SIAM J. Sci. Stat. Comput. 3, 502–515.

Barndorff-Nielsen O. (1977); *Exponentially decreasing distributions for
the logarithm of particle size*, Proc. Roy. Soc. Lond., A353, 401–419.

Barndorff-Nielsen O., Blaesild, P. (1983); *Hyperbolic distributions. In
Encyclopedia of Statistical Sciences*, Eds., Johnson N.L., Kotz S. and
Read C.B., Vol. 3, pp. 700–707. New York: Wiley.

Raible S. (2000); *Levy Processes in Finance: Theory, Numerics and
Empirical Facts*, PhD Thesis, University of Freiburg, Germany, 161
pages.

## Examples

``` r
## nigShapeTriangle -
   #
```
