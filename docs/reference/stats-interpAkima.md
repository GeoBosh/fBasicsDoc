# Bivariate Spline Interpolation

Interpolates bivariate data sets using Akima spline interpolation.

## Usage

``` r
akimaInterp(x, y = NULL, z = NULL, gridPoints = 21,
    xo = seq(min(x), max(x), length = gridPoints),
    yo = seq(min(y), max(y), length = gridPoints), extrap = FALSE)

akimaInterpp(x, y = NULL, z = NULL, xo, yo, extrap = FALSE)
```

## Arguments

- x, y, z:

  for `akimaInterp` the arguments `x` and `y` are two numeric vectors of
  grid pounts, and `z` is a numeric matrix or any other rectangular
  object which can be transformed by the function `as.matrix` into a
  matrix object. For `akimaInterpp` we consider either three numeric
  vectors of equal length or if `y` and `z` are NULL, a list with
  entries `x`, `y`, `z`, or named data frame with `x` in the first, `y`
  in the second, and `z` in the third column.

- gridPoints:

  an integer value specifying the number of grid points in `x` and `y`
  direction.

- xo, yo:

  for `akimaInterp` two numeric vectors of data points spanning the
  grid, and for `akimaInterpp` two numeric vectors of data points
  building pairs for pointwise interpolation.

- extrap:

  a logical, if `TRUE` then the data points are extrapolated.

## Details

Two options are available: gridded and pointwise interpolation.

`akimaInterp` is a wrapper to `interp` provided by the contributed R
package `akima`. The Fortran code of the Akima spline interpolation
routine was written by H. Akima.

Linear surface fitting and krige surface fitting are provided by the
functions
[`linearInterp`](https://geobosh.github.io/fBasicsDoc/reference/stats-interpLinear.md)
and
[`krigeInterp`](https://geobosh.github.io/fBasicsDoc/reference/stats-interpKrige.md).

## Note

Package `akima` is no longer needed. Equivalent functions from package
`interp` are now called instead.

## Value

- akimaInterp:

  returns a list with at least three entries, `x`, `y` and `z`. Note,
  that the returned values, can be directly used by the `persp` and
  `contour` 3D plotting methods.

- akimaInterpp:

  returns a data.frame with columns `"x"`, `"y"`, and `"z"`.

## See also

[`linearInterp`](https://geobosh.github.io/fBasicsDoc/reference/stats-interpLinear.md),
[`krigeInterp`](https://geobosh.github.io/fBasicsDoc/reference/stats-interpKrige.md).

## References

Akima H., 1978, *A Method of Bivariate Interpolation and Smooth Surface
Fitting for Irregularly Distributed Data Points*, ACM Transactions on
Mathematical Software 4, 149-164.

Akima H., 1996, *Algorithm 761: Scattered-Data Surface Fitting that has
the Accuracy of a Cubic Polynomial*, ACM Transactions on Mathematical
Software 22, 362-371.

## Examples

``` r
# \donttest{
## Does not run for r-solaris-x86
## akimaInterp -- Akima Interpolation:
if (requireNamespace("interp")) {
  set.seed(1953)
  x <- runif(999) - 0.5
  y <- runif(999) - 0.5
  z <- cos(2*pi*(x^2+y^2))
  ans <- akimaInterp(x, y, z, gridPoints = 41, extrap = FALSE)
  persp(ans, theta = -40, phi = 30, col = "steelblue",
       xlab = "x", ylab = "y", zlab = "z")
  contour(ans)
}
#> Loading required namespace: interp



## Use spatial as alternative on r-solaris-x86
## spatialInterp - Generate Kriged Grid Data:
if (requireNamespace("spatial")) {
  RNGkind(kind = "Marsaglia-Multicarry", normal.kind = "Inversion")
  set.seed(4711, kind = "Marsaglia-Multicarry")
  x <- runif(999)-0.5
  y <- runif(999)-0.5
  z <- cos(2*pi*(x^2+y^2))
  ans <- krigeInterp(x, y, z, extrap = FALSE)
  persp(ans)
  title(main = "Kriging")
  contour(ans)
  title(main = "Kriging")
}
#> Warning: RNGkind: Marsaglia-Multicarry has poor statistical properties
#> Warning: RNGkind: Marsaglia-Multicarry has poor statistical properties


# }
```
