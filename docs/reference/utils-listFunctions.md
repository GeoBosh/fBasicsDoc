# List exported functions in a package

Utilities to list and count exported functions in a package, list the
contents of the description file of a package, and

Prints the content of an index file for a package (a list of the objects
exported by a package).

## Usage

``` r
listFunctions(package, character.only = FALSE)
countFunctions(package, character.only = FALSE)

listIndex(package, character.only = FALSE)
```

## Arguments

- package:

  a literal character string or a character string denoting the name of
  a package.

- character.only:

  a logical indicating whether 'package' can be assumed to be a
  character string.

## Value

for `listFunctions`, a character vector containing the names of the
exported functions in a package,

for `countFunctions`, a named numeric value giving the number of the
exported functions in a package.

`listIndex` doesn't return a useful value. It is used for the side
effect of printing the description or index.

## Note

Be aware that `listFunctions` and `countFunctions` attach the package to
the search path.

## See also

[`packageDescription`](https://rdrr.io/r/utils/packageDescription.html)

## Examples

``` r
listFunctions("fBasics")
#>   [1] ".acfPlot"             ".contourPlot"         ".distCheck"          
#>   [4] ".firePlot"            ".mrlPlot"             ".pacfPlot"           
#>   [7] ".perspPlot"           ".plot"                ".predict"            
#>  [10] ".qStableFit"          ".residualsPlot"       ".responsesPlot"      
#>  [13] ".sliderMenu"          ".unirootNA"           "Boxcar"              
#>  [16] "Delta"                "Heaviside"            "Ramp"                
#>  [19] "Sign"                 "Triang"               "acfPlot"             
#>  [22] "adTest"               "akimaInterp"          "akimaInterpp"        
#>  [25] "as.timeSeries"        "basicStats"           "boxL"                
#>  [28] "boxPercentilePlot"    "boxPlot"              "box_"                
#>  [31] "characterTable"       "cmPalette"            "colIds"              
#>  [34] "colIds<-"             "colVec"               "colorLocator"        
#>  [37] "colorMatrix"          "colorTable"           "copyright"           
#>  [40] "correlationTest"      "countFunctions"       "cumulatedPlot"       
#>  [43] "cvmTest"              "dagoTest"             "decor"               
#>  [46] "densityPlot"          "dgh"                  "dght"                
#>  [49] "dgld"                 "dhyp"                 "distCheck"           
#>  [52] "divPalette"           "dmaxdd"               "dnig"                
#>  [55] "drawdownPlot"         "dsgh"                 "dsght"               
#>  [58] "dsnig"                "dssd"                 "focusPalette"        
#>  [61] "get.lcgseed"          "getArgs"              "getDescription"      
#>  [64] "getModel"             "getSlot"              "getTitle"            
#>  [67] "ghFit"                "ghIQR"                "ghKURT"              
#>  [70] "ghKurt"               "ghMED"                "ghMean"              
#>  [73] "ghMode"               "ghMoments"            "ghSKEW"              
#>  [76] "ghSkew"               "ghSlider"             "ghVar"               
#>  [79] "ghtFit"               "ghtIQR"               "ghtKURT"             
#>  [82] "ghtKurt"              "ghtMED"               "ghtMean"             
#>  [85] "ghtMode"              "ghtMoments"           "ghtSKEW"             
#>  [88] "ghtSkew"              "ghtVar"               "gldFit"              
#>  [91] "gldIQR"               "gldKURT"              "gldMED"              
#>  [94] "gldMode"              "gldSKEW"              "greyPalette"         
#>  [97] "gridVector"           "heatPalette"          "hgrid"               
#> [100] "hilbert"              "histPlot"             "hypFit"              
#> [103] "hypIQR"               "hypKURT"              "hypKurt"             
#> [106] "hypMED"               "hypMean"              "hypMode"             
#> [109] "hypMoments"           "hypSKEW"              "hypSkew"             
#> [112] "hypSlider"            "hypVar"               "interactivePlot"     
#> [115] "inv"                  "isPositiveDefinite"   "jarqueberaTest"      
#> [118] "jbTest"               "kendallTest"          "krigeInterp"         
#> [121] "kron"                 "ks2Test"              "ksnormTest"          
#> [124] "kurtosis"             "lacfPlot"             "lillieTest"          
#> [127] "linearInterp"         "linearInterpp"        "listFunctions"       
#> [130] "listIndex"            "locationTest"         "logDensityPlot"      
#> [133] "makePositiveDefinite" "maxddStats"           "monoPalette"         
#> [136] "nFit"                 "nigFit"               "nigIQR"              
#> [139] "nigKURT"              "nigKurt"              "nigMED"              
#> [142] "nigMean"              "nigMode"              "nigMoments"          
#> [145] "nigSKEW"              "nigShapeTriangle"     "nigSkew"             
#> [148] "nigSlider"            "nigVar"               "norm2"               
#> [151] "normIQR"              "normKURT"             "normMED"             
#> [154] "normSKEW"             "normalTest"           "pacfPlot"            
#> [157] "pascal"               "pchiTest"             "pdl"                 
#> [160] "pearsonTest"          "pgh"                  "pght"                
#> [163] "pgld"                 "phyp"                 "pmaxdd"              
#> [166] "pnig"                 "psgh"                 "psght"               
#> [169] "psnig"                "pssd"                 "qgh"                 
#> [172] "qght"                 "qgld"                 "qhyp"                
#> [175] "qnig"                 "qqghtPlot"            "qqgldPlot"           
#> [178] "qqnigPlot"            "qqnormPlot"           "qsgh"                
#> [181] "qsght"                "qsnig"                "qssd"                
#> [184] "qualiPalette"         "rainbowPalette"       "rampPalette"         
#> [187] "returnPlot"           "returnSeriesGUI"      "returns"             
#> [190] "rgh"                  "rght"                 "rgld"                
#> [193] "rhyp"                 "rk"                   "rmaxdd"              
#> [196] "rnig"                 "rnorm.lcg"            "rowAvgs"             
#> [199] "rowIds"               "rowIds<-"             "rowKurtosis"         
#> [202] "rowMaxs"              "rowMins"              "rowProds"            
#> [205] "rowQuantiles"         "rowSds"               "rowSkewness"         
#> [208] "rowStats"             "rowStdevs"            "rowVars"             
#> [211] "rowVec"               "rsgh"                 "rsght"               
#> [214] "rsnig"                "rssd"                 "rt.lcg"              
#> [217] "runif.lcg"            "sampleIQR"            "sampleKURT"          
#> [220] "sampleLmoments"       "sampleMED"            "sampleSKEW"          
#> [223] "scaleTest"            "scalinglawPlot"       "seqPalette"          
#> [226] "seriesPlot"           "set.lcgseed"          "sfTest"              
#> [229] "sghFit"               "shapiroTest"          "show"                
#> [232] "skewness"             "snigFit"              "spearmanTest"        
#> [235] "ssdFit"               "stableFit"            "stableSlider"        
#> [238] "stdev"                "symbolTable"          "tFit"                
#> [241] "teffectPlot"          "termPlot"             "terrainPalette"      
#> [244] "timPalette"           "timeSeries"           "topoPalette"         
#> [247] "tr"                   "triang"               "tsHessian"           
#> [250] "tslag"                "varianceTest"         "vec"                 
#> [253] "vech"                 "vgrid"                "volatility"          
   
countFunctions("fBasics")
#> fBasics 
#>     255 
```
