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
library(methods)
df=data.frame(country=c("US", "GB", "BR"), 
              val1=c(10,13,14), 
              val2=c(23,12,32))
Line <- gvisLineChart(df)
print(Line, tag = "chart")
{% endhighlight %}

<!-- LineChart generated in R 3.2.0 by googleVis 0.5.8 package -->
<!-- Wed May 20 20:09:08 2015 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataLineChartID203753c6887b () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 "US",
10,
23 
],
[
 "GB",
13,
12 
],
[
 "BR",
14,
32 
] 
];
data.addColumn('string','country');
data.addColumn('number','val1');
data.addColumn('number','val2');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartLineChartID203753c6887b() {
var data = gvisDataLineChartID203753c6887b();
var options = {};
options["allowHtml"] = true;

    var chart = new google.visualization.LineChart(
    document.getElementById('LineChartID203753c6887b')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "corechart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartLineChartID203753c6887b);
})();
function displayChartLineChartID203753c6887b() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartLineChartID203753c6887b"></script>
 
<!-- divChart -->
  
<div id="LineChartID203753c6887b" 
  style="width: 500; height: automatic;">
</div>


{% highlight r %}
library(metricsgraphics)
{% endhighlight %}



{% highlight text %}
## Loading required package: htmlwidgets
## Loading required package: htmltools
{% endhighlight %}



{% highlight r %}
tmp <- data.frame(year=seq(1790, 1970, 10), uspop=as.numeric(uspop))

k <- tmp %>%
  mjs_plot(x=year, y=uspop) %>%
  mjs_line() %>%
  mjs_add_marker(1850, "Something Wonderful") %>%
  mjs_add_baseline(150, "Something Awful")  

k
{% endhighlight %}

<!--html_preserve--><div id="mjs-5c79f35030f396429ba2f6d1e896d1" class="metricsgraphics" style="width:504px;height:504px;"></div>
<div id="mjs-5c79f35030f396429ba2f6d1e896d1-legend" class="metricsgraphics-legend"></div>
<script type="application/json" data-for="mjs-5c79f35030f396429ba2f6d1e896d1">{"x":{"data":{"year":[1790,1800,1810,1820,1830,1840,1850,1860,1870,1880,1890,1900,1910,1920,1930,1940,1950,1960,1970],"uspop":[3.93,5.31,7.24,9.64,12.9,17.1,23.2,31.4,39.8,50.2,62.9,76,92,105.7,122.8,131.7,151.3,179.3,203.2]},"x_axis":true,"y_axis":true,"baseline_accessor":null,"predictor_accessor":null,"show_confidence_band":null,"chart_type":"line","xax_format":"plain","x_label":null,"y_label":null,"markers":[{"year":1850,"label":"Something Wonderful"}],"baselines":[{"value":150,"label":"Something Awful"}],"linked":false,"title":null,"description":null,"left":80,"right":10,"bottom":60,"buffer":8,"y_scale_type":"linear","yax_count":5,"xax_count":6,"x_rug":false,"y_rug":false,"area":false,"missing_is_zero":false,"size_accessor":null,"color_accessor":null,"color_type":"number","color_range":["blue","red"],"size_range":[1,5],"bar_height":20,"min_x":null,"max_x":null,"min_y":null,"max_y":null,"bar_margin":1,"binned":false,"bins":null,"least_squares":false,"interpolate":"cardinal","decimals":2,"show_rollover_text":true,"x_accessor":"year","y_accessor":"uspop","multi_line":null,"geom":"line","legend":null,"legend_target":null,"y_extended_ticks":false,"x_extended_ticks":false,"target":"#mjs-5c79f35030f396429ba2f6d1e896d1","full_width":true,"full_height":true,"animate_on_load":false},"evals":[]}</script><!--/html_preserve-->



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
## [1] methods   stats     graphics  grDevices utils     datasets 
## [7] base     
## 
## other attached packages:
## [1] metricsgraphics_0.7.5 htmltools_0.2.6       htmlwidgets_0.4      
## [4] googleVis_0.5.8      
## 
## loaded via a namespace (and not attached):
##  [1] Rcpp_0.11.5      digest_0.6.8     jsonlite_0.9.16 
##  [4] formatR_1.2      magrittr_1.5     evaluate_0.7    
##  [7] rstudioapi_0.3.1 RJSONIO_1.3-0    tools_3.2.0     
## [10] servr_0.2        stringr_0.6.2    httpuv_1.3.2    
## [13] yaml_2.1.13      knitr_1.10
{% endhighlight %}

