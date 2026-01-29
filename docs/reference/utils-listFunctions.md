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
#>   [1] ".acfPlot"             ".contourPlot"         ".firePlot"           
#>   [4] ".mrlPlot"             ".pacfPlot"            ".perspPlot"          
#>   [7] ".plot"                ".predict"             ".qStableFit"         
#>  [10] ".residualsPlot"       ".responsesPlot"       ".sliderMenu"         
#>  [13] ".unirootNA"           "Boxcar"               "Delta"               
#>  [16] "Heaviside"            "Ramp"                 "Sign"                
#>  [19] "Triang"               "acfPlot"              "adTest"              
#>  [22] "akimaInterp"          "akimaInterpp"         "as.timeSeries"       
#>  [25] "basicStats"           "boxL"                 "boxPercentilePlot"   
#>  [28] "boxPlot"              "box_"                 "characterTable"      
#>  [31] "cmPalette"            "colIds"               "colIds<-"            
#>  [34] "colVec"               "colorLocator"         "colorMatrix"         
#>  [37] "colorTable"           "copyright"            "correlationTest"     
#>  [40] "countFunctions"       "cumulatedPlot"        "cvmTest"             
#>  [43] "dagoTest"             "decor"                "densityPlot"         
#>  [46] "dgh"                  "dght"                 "dgld"                
#>  [49] "dhyp"                 "distCheck"            "divPalette"          
#>  [52] "dmaxdd"               "dnig"                 "drawdownPlot"        
#>  [55] "dsgh"                 "dsght"                "dsnig"               
#>  [58] "dssd"                 "focusPalette"         "get.lcgseed"         
#>  [61] "getArgs"              "getDescription"       "getModel"            
#>  [64] "getSlot"              "getTitle"             "ghFit"               
#>  [67] "ghIQR"                "ghKURT"               "ghKurt"              
#>  [70] "ghMED"                "ghMean"               "ghMode"              
#>  [73] "ghMoments"            "ghSKEW"               "ghSkew"              
#>  [76] "ghSlider"             "ghVar"                "ghtFit"              
#>  [79] "ghtIQR"               "ghtKURT"              "ghtKurt"             
#>  [82] "ghtMED"               "ghtMean"              "ghtMode"             
#>  [85] "ghtMoments"           "ghtSKEW"              "ghtSkew"             
#>  [88] "ghtVar"               "gldFit"               "gldIQR"              
#>  [91] "gldKURT"              "gldMED"               "gldMode"             
#>  [94] "gldSKEW"              "greyPalette"          "gridVector"          
#>  [97] "heatPalette"          "hgrid"                "hilbert"             
#> [100] "histPlot"             "hypFit"               "hypIQR"              
#> [103] "hypKURT"              "hypKurt"              "hypMED"              
#> [106] "hypMean"              "hypMode"              "hypMoments"          
#> [109] "hypSKEW"              "hypSkew"              "hypSlider"           
#> [112] "hypVar"               "interactivePlot"      "inv"                 
#> [115] "isPositiveDefinite"   "jarqueberaTest"       "jbTest"              
#> [118] "kendallTest"          "krigeInterp"          "kron"                
#> [121] "ks2Test"              "ksnormTest"           "kurtosis"            
#> [124] "lacfPlot"             "lillieTest"           "linearInterp"        
#> [127] "linearInterpp"        "listFunctions"        "listIndex"           
#> [130] "locationTest"         "logDensityPlot"       "makePositiveDefinite"
#> [133] "maxddStats"           "monoPalette"          "nFit"                
#> [136] "nigFit"               "nigIQR"               "nigKURT"             
#> [139] "nigKurt"              "nigMED"               "nigMean"             
#> [142] "nigMode"              "nigMoments"           "nigSKEW"             
#> [145] "nigShapeTriangle"     "nigSkew"              "nigSlider"           
#> [148] "nigVar"               "norm2"                "normIQR"             
#> [151] "normKURT"             "normMED"              "normSKEW"            
#> [154] "normalTest"           "pacfPlot"             "pascal"              
#> [157] "pchiTest"             "pdl"                  "pearsonTest"         
#> [160] "pgh"                  "pght"                 "pgld"                
#> [163] "phyp"                 "pmaxdd"               "pnig"                
#> [166] "psgh"                 "psght"                "psnig"               
#> [169] "pssd"                 "qgh"                  "qght"                
#> [172] "qgld"                 "qhyp"                 "qnig"                
#> [175] "qqghtPlot"            "qqgldPlot"            "qqnigPlot"           
#> [178] "qqnormPlot"           "qsgh"                 "qsght"               
#> [181] "qsnig"                "qssd"                 "qualiPalette"        
#> [184] "rainbowPalette"       "rampPalette"          "returnPlot"          
#> [187] "returnSeriesGUI"      "returns"              "rgh"                 
#> [190] "rght"                 "rgld"                 "rhyp"                
#> [193] "rk"                   "rmaxdd"               "rnig"                
#> [196] "rnorm.lcg"            "rowAvgs"              "rowIds"              
#> [199] "rowIds<-"             "rowKurtosis"          "rowMaxs"             
#> [202] "rowMins"              "rowProds"             "rowQuantiles"        
#> [205] "rowSds"               "rowSkewness"          "rowStats"            
#> [208] "rowStdevs"            "rowVars"              "rowVec"              
#> [211] "rsgh"                 "rsght"                "rsnig"               
#> [214] "rssd"                 "rt.lcg"               "runif.lcg"           
#> [217] "sampleIQR"            "sampleKURT"           "sampleLmoments"      
#> [220] "sampleMED"            "sampleSKEW"           "scaleTest"           
#> [223] "scalinglawPlot"       "seqPalette"           "seriesPlot"          
#> [226] "set.lcgseed"          "sfTest"               "sghFit"              
#> [229] "shapiroTest"          "show"                 "skewness"            
#> [232] "snigFit"              "spearmanTest"         "ssdFit"              
#> [235] "stableFit"            "stableSlider"         "stdev"               
#> [238] "symbolTable"          "tFit"                 "teffectPlot"         
#> [241] "termPlot"             "terrainPalette"       "timPalette"          
#> [244] "timeSeries"           "topoPalette"          "tr"                  
#> [247] "triang"               "tsHessian"            "tslag"               
#> [250] "varianceTest"         "vec"                  "vech"                
#> [253] "vgrid"                "volatility"          
   
countFunctions("fBasics")
#> fBasics 
#>     254 
```
