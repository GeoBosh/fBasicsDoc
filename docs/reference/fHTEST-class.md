# Class `"fHTEST"`

An S4 class representing the outcome of a statistical test.

## Objects from the Class

Objects from this class are created by some statistical test functions.

## Slots

- `call`::

  the function call.

- `data`::

  the data as specified by the input argument(s).

- `test`::

  a list whose elements contain the results from the statistical test.
  The information provided is similar to a list object of class
  `"htest"`.

- `title`::

  a character string with the name of the test. This can be overwritten
  specifying a user defined input argument.

- `description`::

  a character string with an optional user defined description. By
  default just the current date when the test was applied will be
  returned.

Slot `@test` is an object of class `"list"` containing at least the
following elements:

- statistic:

  the value(s) of the test statistic.

- p.value:

  the p-value(s) of the test.

- parameters:

  a numeric value or vector of parameters.

- estimate:

  a numeric value or vector of sample estimates.

- conf.int:

  a numeric two row vector or matrix of 95% confidence levels.

- method:

  a character string indicating what type of test was performed.

- data.name:

  a character string giving the name(s) of the data.

## Methods

- show:

  `signature(object = "fHTEST")`: ...

## See also

for functions returning objects from class `"fHTEST"`, see
[`scaleTest`](https://geobosh.github.io/fBasicsDoc/reference/test-scaleTest.md),
[`correlationTest`](https://geobosh.github.io/fBasicsDoc/reference/test-correlationTest.md),
[`ks2Test`](https://geobosh.github.io/fBasicsDoc/reference/test-ks2Test.md),
[`locationTest`](https://geobosh.github.io/fBasicsDoc/reference/test-locationTest.md),
[`NormalityTests`](https://geobosh.github.io/fBasicsDoc/reference/test-normalityTests.md),
[`varianceTest`](https://geobosh.github.io/fBasicsDoc/reference/test-varianceTest.md)
[`scaleTest`](https://geobosh.github.io/fBasicsDoc/reference/test-scaleTest.md)

## Examples

``` r
showClass("fHTEST")
#> Class "fHTEST" [package "fBasics"]
#> 
#> Slots:
#>                                                                   
#> Name:         call        data        test       title description
#> Class:        call        list        list   character   character
```
