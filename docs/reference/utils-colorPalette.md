# Color palettes

Functions to create color palettes.  

The functions are:

|                  |                                   |
|------------------|-----------------------------------|
| `rainbowPalette` | Contiguous rainbow color palette, |
| `heatPalette`    | Contiguous heat color palette,    |
| `terrainPalette` | Contiguous terrain color palette, |
| `topoPalette`    | Contiguous topo color palette,    |
| `cmPalette`      | Contiguous cm color palette,      |
| `greyPalette`    | R's gamma-corrected gray palette, |
| `timPalette`     | Tim's Matlab like color palette,  |
| `rampPalette`    | Color ramp palettes,              |
| `seqPalette`     | Sequential color brewer palettes, |
| `divPalette`     | Diverging color brewer palettes,  |
| `qualiPalette`   | Qualified color brewer palettes,  |
| `focusPalette`   | Red, green blue focus palettes,   |
| `monoPalette`    | Red, green blue mono palettes.    |

## Usage

``` r
rainbowPalette(n = 64, ...) 
heatPalette(n = 64, ...) 
terrainPalette(n = 64, ...) 
topoPalette(n = 64, ...) 
cmPalette(n = 64, ...) 

greyPalette(n = 64, ...)
timPalette(n = 64)

rampPalette(n, name = c("blue2red", "green2red", "blue2green",     
    "purple2green", "blue2yellow", "cyan2magenta"))
    
seqPalette(n, name = c(
    "Blues", "BuGn", "BuPu", "GnBu", "Greens", "Greys", "Oranges", 
    "OrRd", "PuBu", "PuBuGn", "PuRd", "Purples", "RdPu", "Reds", 
    "YlGn", "YlGnBu", "YlOrBr", "YlOrRd"))
divPalette(n, name = c(
    "BrBG", "PiYG", "PRGn", "PuOr", "RdBu", "RdGy", "RdYlBu", "RdYlGn", 
    "Spectral"))   
qualiPalette(n, name = c(
    "Accent", "Dark2", "Paired", "Pastel1", "Pastel2", "Set1", "Set2", 
    "Set3")) 
    
focusPalette(n, name = c("redfocus", "greenfocus", "bluefocus"))
monoPalette(n, name = c("redmono", "greenmono", "bluemono"))
```

## Arguments

- n:

  an integer, giving the number of greys or colors to be constructed.

- name:

  a character string, the name of the color set.

- ...:

  arguments to be passed, see the details section

## Details

All Rmetrics' color sets are named as `fooPalette`, where the prefix
`foo` denotes the name of the underlying color set.

### R's Contiguous Color Palettes:

Palettes for `n` contiguous colors are implemented in the `grDevices`
package. To conform with Rmetrics' naming convention for color palettes
we have build wrappers around the underlying functions. These are the
`rainbowPalette`, `heatPalette`, `terrainPalette`, `topoPalette`, and
the `cmPalette`.

Conceptually, all of these functions actually use (parts of) a line cut
out of the 3-dimensional color space, parametrized by the function
`hsv(h,s,v,gamma)`, where `gamma=1` for the `fooPalette` function, and
hence, equispaced hues in RGB space tend to cluster at the red, green
and blue primaries.

Some applications, such as contouring, require a palette of colors which
do not wrap around to give a final color close to the starting one. To
pass additional arguments to the underlying functions see
[`help(rainbow)`](https://rdrr.io/r/grDevices/palettes.html). With
rainbow, the parameters `start` and `end` can be used to specify
particular subranges of hues. Synonym function calls are `rainbow`,
`heat.colors`, `terrain.colors`, `topo.colors`, and `cm.colors`.

### R's Gamma-Corrected Gray Palette:

`grayPalette` chooses a series of `n` gamma-corrected gray levels. The
range of the gray levels can be optionally monitored through the `...`
arguments, for details see
[`help(gray.colors)`](https://rdrr.io/r/grDevices/gray.colors.html),
which is a synonym function call in the `grDevices` package.

### Tim's Matlab like Color Palette:

`timPalette` creates a color set ranging from blue to red, and passes
through the colors cyan, yellow, and orange. It comes from the Matlab
software, originally used in fluid dynamics simulations. The function
here is a copy from R's contributed package `fields` doing a spline
interpolation on `n=64` color points.

### Color Ramp Palettes:

`rampPalette` creates several color ramps. The function is implemented
from Tim Keitt's contributed R package `colorRamps`. Supported through
the argument `name` are the following color ramps: `"blue2red"`,
`"green2red"`, `"blue2green"`, `"purple2green"`, `"blue2yellow"`,
`"cyan2magenta"`.

### Color Brewer Palettes:

The functions `seqPalette`, `divPalette`, and `qualiPalette` create
color sets according to R's contributed `RColorBrewer` package. The
first letter in the function name denotes the type of the color set: "s"
for sequential palettes, "d" for diverging palettes, and "q" for
qualitative palettes.

*Sequential palettes* are suited to ordered data that progress from low
to high. Lightness steps dominate the look of these schemes, with light
colors for low data values to dark colors for high data values. The
sequential palettes names are: Blues, BuGn, BuPu, GnBu, Greens, Greys,
Oranges, OrRd, PuBu, PuBuGn, PuRd, Purples, RdPu, Reds, YlGn, YlGnBu,
YlOrBr, YlOrRd.

*Diverging palettes* put equal emphasis on mid-range critical values and
extremes at both ends of the data range. The critical class or break in
the middle of the legend is emphasized with light colors and low and
high extremes are emphasized with dark colors that have contrasting
hues. The diverging palettes names are: BrBG, PiYG, PRGn, PuOr, RdBu,
RdGy, RdYlBu, RdYlGn, Spectral.

*Qualitative palettes* do not imply magnitude differences between legend
classes, and hues are used to create the primary visual differences
between classes. Qualitative schemes are best suited to representing
nominal or categorical data. The qualitative palettes names are: Accent,
Dark2, Paired, Pastel1, Pastel2, Set1, Set2, Set3.

In contrast to the original color brewer palettes, the palettes here are
created by spline interpolation from the color variation with the most
different values, i.e for the sequential palettes these are 9 values,
for the diverging palettes these are 11 values, and for the qualitative
palettes these are between 8 and 12 values dependeing on the color set.

### Graph Color Palettes

The function `perfanPalette` creates color sets inspired by R's
contributed package `Performance Analytics`. These color palettes have
been designed to create readable, comparable line and bar graphs with
specific objectives.

- Focused Color Palettes:

  Color sets designed to provide focus to the data graphed as the first
  element. This palette is best used when there is clearly an important
  data set for the viewer to focus on, with the remaining data being
  secondary, tertiary, etc. Later elements graphed in diminishing values
  of gray.

- Monochrome Color Palettes:

  These include color sets for monochrome color displays.

## Value

a character string of color strings

## Note

The palettes are wrapper functions provided in several contributed R
packages. These include:

Cynthia Brewer and Mark Harrower for the brewer palettes,  
Peter Carl and Brian G. Peterson for the "PerformanceAnalytics"
package,  
Tim Keitt for the "colorRamps" package,  
Ross Ihaka for the "colorspace" package,  
Tomas Aragon for the "epitools" package,  
Doug Nychka for the "fields" package,  
Erich Neuwirth for the "RColorBrewer" package.  

Additional undocumented hidden functions:

|               |                                               |
|---------------|-----------------------------------------------|
| `.asRGB`      | Converts any R color to RGB (red/green/blue), |
| `.chcode`     | Changes from one to another number system,    |
| `.hex.to.dec` | Converts heximal numbers do decimal numbers,  |
| `.dec.to.hex` | Converts decimal numbers do heximal numbers.  |

## Examples

``` r
greyPalette()
#>  [1] "#4D4D4D" "#525252" "#575757" "#5C5C5C" "#606060" "#646464" "#686868"
#>  [8] "#6C6C6C" "#707070" "#737373" "#777777" "#7A7A7A" "#7D7D7D" "#808080"
#> [15] "#838383" "#868686" "#898989" "#8C8C8C" "#8E8E8E" "#919191" "#949494"
#> [22] "#969696" "#999999" "#9B9B9B" "#9D9D9D" "#A0A0A0" "#A2A2A2" "#A4A4A4"
#> [29] "#A7A7A7" "#A9A9A9" "#ABABAB" "#ADADAD" "#AFAFAF" "#B1B1B1" "#B3B3B3"
#> [36] "#B5B5B5" "#B7B7B7" "#B9B9B9" "#BBBBBB" "#BDBDBD" "#BFBFBF" "#C1C1C1"
#> [43] "#C3C3C3" "#C5C5C5" "#C6C6C6" "#C8C8C8" "#CACACA" "#CCCCCC" "#CDCDCD"
#> [50] "#CFCFCF" "#D1D1D1" "#D2D2D2" "#D4D4D4" "#D6D6D6" "#D7D7D7" "#D9D9D9"
#> [57] "#DBDBDB" "#DCDCDC" "#DEDEDE" "#DFDFDF" "#E1E1E1" "#E2E2E2" "#E4E4E4"
#> [64] "#E6E6E6"
```
