# General S4 Class Extractor Functions

A collection and description of functions to extract slots from S4 class
objects.  

The extractor functions are:

|                  |                                                 |
|------------------|-------------------------------------------------|
| `getModel`       | Extracts the model slot from a S4 object,       |
| `getTitle`       | Extracts the title slot from a S4 object,       |
| `getDescription` | Extracts the description slot from a S4 object, |
| `getSlot`        | Extracts a specified slot from a S4 object,     |
| `getArgs`        | Shows the arguments of a S4 function.           |

Since R version 2.14.0, a generic `getCall()` is part of R; for earlier
versions, we had provided a simple version for S4 objects.

## Usage

    <!-- % getCall(x, \dots) -->
    getModel(object)
    getTitle(object)
    getDescription(object)

    getSlot(object, slotName)

    getArgs(f, signature)

## Arguments

- f:

  a generic function or the character-string name of one.

- object:

  an object of class S4.

- signature:

  the signature of classes to match to the arguments of `f`

- slotName:

  a character string, the name of the slot to be extracted from the S4
  object.

## Value

for `getModel`, `getTitle`, `getDescription`, and `getSlot` - the
content of the corresponding slot.

for `getArgs` the names of the arguments.

## Examples

``` r
## Example S4 Representation:
## Hyothesis Testing with Control Settings
setClass("hypTest",
         representation(
             call = "call",
             data = "numeric",
             test = "list",
             description = "character")
         )

## Shapiro Wilk Normaility Test
swTest = function(x, description = "") {
    ans = shapiro.test(x)
    class(ans) = "list"
    new("hypTest",
        call = match.call(),
        data = x,
        test = ans,
        description = description)
}
test = swTest(x = rnorm(500), description = "500 RVs")

## Extractor Functions:
isS4(test)
#> [1] TRUE
getCall(test)
#> swTest(x = rnorm(500), description = "500 RVs")
getDescription(test)
#> [1] "500 RVs"

## get arguments
args(returns)
#> function (x, ...) 
#> NULL
getArgs(returns)
#> returns,:
#> function (x, method = c("continuous", "discrete", "compound", 
#>     "simple"), percentage = FALSE, ...) 
#> NULL
getArgs("returns")
#> returns,:
#> function (x, method = c("continuous", "discrete", "compound", 
#>     "simple"), percentage = FALSE, ...) 
#> NULL
getArgs(returns, "timeSeries")
#> returns,timeSeries:
#> function (x, method = c("continuous", "discrete", "compound", 
#>     "simple"), percentage = FALSE, na.rm = TRUE, trim = TRUE, 
#>     ...) 
#> NULL
getArgs("returns", "timeSeries")
#> returns,timeSeries:
#> function (x, method = c("continuous", "discrete", "compound", 
#>     "simple"), percentage = FALSE, na.rm = TRUE, trim = TRUE, 
#>     ...) 
#> NULL
```
