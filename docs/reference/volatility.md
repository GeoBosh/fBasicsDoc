# Compute volatility

Generic function for volatility computations.

## Usage

``` r
volatility(object, ...)

# Default S3 method
volatility(object, ...)
```

## Arguments

- object:

  an object from which to extract or compute the volatility.

- ...:

  arguments for methods. Ignored by the default method.

## Details

`volatility` is a generic function, whose default method centers and
squares the values in `object`. Other packages can (and do) define
methods for it.
