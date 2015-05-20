---
layout: post
title:  "Serve Jekyll Websites with servr and knitr"
categories: [jekyll, rstats]
tags: [knitr, servr, httpuv, websocket]
---


{% highlight r %}
library(googleVis)
{% endhighlight %}



{% highlight text %}
## 
## Welcome to googleVis version 0.5.8
## 
## Please read the Google API Terms of Use
## before you start using the package:
## https://developers.google.com/terms/
## 
## Note, the plot method of googleVis will by default use
## the standard browser to display its output.
## 
## See the googleVis package vignettes for more details,
## or visit http://github.com/mages/googleVis.
## 
## To suppress this message use:
## suppressPackageStartupMessages(library(googleVis))
{% endhighlight %}



{% highlight r %}
df=data.frame(country=c("US", "GB", "BR"), 
              val1=c(10,13,14), 
              val2=c(23,12,32))
Line <- gvisLineChart(df)
{% endhighlight %}



{% highlight text %}
## Error in FUN(X[[i]], ...): could not find function "is"
{% endhighlight %}



{% highlight r %}
print(Line, tag = "chart")
{% endhighlight %}



{% highlight text %}
## Error in print(Line, tag = "chart"): object 'Line' not found
{% endhighlight %}



{% highlight r %}
sessionInfo()
{% endhighlight %}



{% highlight text %}
## R version 3.2.0 (2015-04-16)
## Platform: x86_64-pc-linux-gnu (64-bit)
## Running under: Ubuntu 14.04.2 LTS
## 
## locale:
##  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C              
##  [3] LC_TIME=pt_BR.UTF-8        LC_COLLATE=en_US.UTF-8    
##  [5] LC_MONETARY=pt_BR.UTF-8    LC_MESSAGES=en_US.UTF-8   
##  [7] LC_PAPER=pt_BR.UTF-8       LC_NAME=C                 
##  [9] LC_ADDRESS=C               LC_TELEPHONE=C            
## [11] LC_MEASUREMENT=pt_BR.UTF-8 LC_IDENTIFICATION=C       
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  base     
## 
## other attached packages:
## [1] googleVis_0.5.8
## 
## loaded via a namespace (and not attached):
##  [1] formatR_1.2   tools_3.2.0   Rcpp_0.11.5   RJSONIO_1.3-0
##  [5] knitr_1.10    methods_3.2.0 stringr_0.6.2 httpuv_1.3.2 
##  [9] servr_0.2     evaluate_0.7
{% endhighlight %}

