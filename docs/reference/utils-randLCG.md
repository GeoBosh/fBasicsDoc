# Generator for Portable random innovations

Functions to generate portable random innovations. The functions run
under R and S-Plus and generate the same sequence of random numbers.
Supported are uniform, normal and Student-t distributed random
numbers.  

The functions are:

|               |                                           |
|---------------|-------------------------------------------|
| `set.lcgseed` | Set initial random seed,                  |
| `get.lcgseed` | Get the current valus of the random seed, |
| `runif.lcg`   | Uniform linear congruational generator,   |
| `rnorm.lcg`   | Normal linear congruational generator,    |
| `rt.lcg`      | Student-t linear congruential generator.  |

## Usage

``` r
set.lcgseed(seed = 4711)
get.lcgseed()

runif.lcg(n, min = 0, max = 1)
rnorm.lcg(n, mean = 0, sd = 1)
rt.lcg(n, df)
```

## Arguments

- seed:

  an integer value, the random number seed.

- n:

  an integer, the number of random innovations to be generated.

- df:

  degrees of freedom, a positive number, may be non-integer.

- mean, sd:

  mean and standard deviation of the normally distributed innovations.

- min, max:

  lower and upper limits of the uniformly distributed innovations.

## Details

A simple portable random number generator for use in R and SPlus. We
recommend to use this generator only for comparisons of calculations in
R and Splus.

The generator is a linear congruential generator with parameters
`LCG(a=13445, c=0, m=2^31-1, X=0)`. It is a simple random number
generator which passes the bitwise randomness test.

## Value

A vector of generated random innovations. The value of the current seed
is stored in the variable `lcg.seed`.

## References

Altman, N.S. (1988); *Bitwise Behavior of Random Number Generators*,
SIAM J. Sci. Stat. Comput., 9(5), September, 941–949.

## Examples

``` r
set.lcgseed(seed = 65890)
 
## runif.lcg, rnorm.lcg, rt.lcg
cbind(runif.lcg(10), rnorm.lcg(10), rt.lcg(10, df = 4))
#>            [,1]       [,2]        [,3]
#>  [1,] 0.4125252  0.1343111  2.04846215
#>  [2,] 0.4008696  0.6894022 -0.51108298
#>  [3,] 0.6922567 -1.0722959  1.74930732
#>  [4,] 0.3915458 -0.2155675 -1.97028909
#>  [5,] 0.3328643 -1.0960369  0.19380579
#>  [6,] 0.3609585  0.4220095 -1.80223886
#>  [7,] 0.0872767  0.3471476  0.08012026
#>  [8,] 0.4352189  0.8073492  1.69154270
#>  [9,] 0.5179752 -1.0614631 -1.40535393
#> [10,] 0.1761661 -0.5147036  0.99432970

get.lcgseed()  
#> lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed.lcg.seed 
#>                                                                                                                                                                                                                                                                             1743389204 
   
## Note, to overwrite rnorm, use
   # rnorm = rnorm.lcg
   # Going back to rnorm
   # rm(rnorm)
```
