# Class `"fDISTFIT"`

S4 class representing fitted distributions.

## Objects from the Class

Objects can be created by calls of the form `new("fDISTFIT", ...)` but
are typically created by functions fitting distributions.

## Slots

- `call`::

  Object of class `"call"` \~~

- `model`::

  Object of class `"character"` \~~

- `data`::

  Object of class `"data.frame"` \~~

- `fit`::

  Object of class `"list"` \~~

- `title`::

  Object of class `"character"` \~~

- `description`::

  Object of class `"character"` \~~

Slot `fit` is a list. Its components depend on the fitting functions.
Here is the meaning of some common ones:

- estimate:

  the point at which the maximum value of the log liklihood function is
  obtained.

- minimum:

  the value of the estimated maximum, i.e. the value of the log
  liklihood function.

- code:

  an integer indicating why the optimization process terminated.  
  1: relative gradient is close to zero, current iterate is probably
  solution;  
  2: successive iterates within tolerance, current iterate is probably
  solution;  
  3: last global step failed to locate a point lower than `estimate`.
  Either `estimate` is an approximate local minimum of the function or
  `steptol` is too small;  
  4: iteration limit exceeded;  
  5: maximum step size `stepmax` exceeded five consecutive times. Either
  the function is unbounded below, becomes asymptotic to a finite value
  from above in some direction or `stepmax` is too small.

- gradient:

  the gradient at the estimated maximum.

## Methods

- show:

  `signature(object = "fDISTFIT")`: ...

## Examples

``` r
showClass("fDISTFIT")
#> Class "fDISTFIT" [package "fBasics"]
#> 
#> Slots:
#>                                                                               
#> Name:         call       model        data         fit       title description
#> Class:        call   character  data.frame        list   character   character
```
