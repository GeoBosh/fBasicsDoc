# Print control

Unlists and prints a control object.

## Usage

``` r
# S3 method for class 'control'
print(x, ...)
```

## Arguments

- x:

  the object to be printed.

- ...:

  arguments to be passed.

## Value

prints control

## Examples

``` r
control <- list(n = 211, seed = 54, name = "generator")
print(control) 
#> $n
#> [1] 211
#> 
#> $seed
#> [1] 54
#> 
#> $name
#> [1] "generator"
#> 
class(control) <- "control"
print(control)  
#>           n        seed        name 
#>       "211"        "54" "generator" 
```
