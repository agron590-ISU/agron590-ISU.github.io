---
title: "Grammar of Graphics"
author: "Rafael Martinez-Feria"
topic: "09"
layout: post
root: ../../../
---

![](images/js_grammar.gif)


### Not exactly what I mean, but thanks anyway John!

**Grammar of grahics*** (GoG) is the theory behing Hardly Wickam's [ggplot2](http://ggplot2.org/) package. [In his 2010 paper](http://link.springer.com/chapter/10.1007/978-3-642-21551-3_13), Leland Wilkinson describes GoG as a system to produce a statistical graphics. The system contains seven GoG classes embedded in a data flow, which represent the sequence of mappings needed to a graphic from a set or multiple sets of data. The figure below (taken form Wilkinson's paper) shows the data flow of the classes. 

![](images/dataflow.png)

### Here is an example of how GoG is implemented in ggplot2


{% highlight r %}
require(ggplot2)
data("mtcars")
{% endhighlight %}

1. Variables maps data to an object called a varset (a set of variables). In ggplot2, for example, you can specify the varset that we want to use by using the data arguement


{% highlight r %}
(p <- ggplot(data=mtcars))
{% endhighlight %}

![center](figure/AkuokoOhene-unnamed-chunk-2-1.png)

2 and 3. Algebra and Scales are transformations on varsets. For instance, below we trasnform the scale of the x axis using `scale_x_sqrt()`


{% highlight r %}
(p <- p + scale_x_sqrt())
{% endhighlight %}

![center](figure/AkuokoOhene-unnamed-chunk-3-1.png)

4. Statistics takes a varset and creates a statistical graph. Below the `stat_bin2d()` function performs a summary of counting points within a 2d-bin statistic. 


{% highlight r %}
(p <- p + stat_bin2d(aes(x=mpg, y=hp)))
{% endhighlight %}

![center](figure/AkuokoOhene-unnamed-chunk-4-1.png)

5. Geometry maps a statistical graph to a geometric graph. Geometry is the "physiscal" graphic we want to see. For example below we add a point geometry to represent individual observations.  


{% highlight r %}
(p <- p + geom_point(aes(x=mpg, y=hp,colour=factor(cyl))))
{% endhighlight %}

![center](figure/AkuokoOhene-unnamed-chunk-5-1.png)

6. Coordinates embeds a graph in a coordinate space. By default, ggplot2 uses cartesian coordinate system. But we can change it to polar coodinates, for example. 


{% highlight r %}
(p <- p + coord_polar())
{% endhighlight %}

![center](figure/AkuokoOhene-unnamed-chunk-6-1.png)

5. Aesthetics maps a graph to a visible or perceivable display called a graphic. Note that in a few instances, we have used the `aes()` function to tell ggplot what VARSET we want it to use to map the graph. In this example, we add a regresion line to a set of groups. 


{% highlight r %}
(p <- p + geom_smooth(aes(x=mpg, y=hp,colour=factor(cyl)), method = "lm"))
{% endhighlight %}

![center](figure/AkuokoOhene-unnamed-chunk-7-1.png)

### What are some challenges with GoG/ggplot2?

- Becasue of its workflow (you have to run through GoG workflow every time) ggplot2 tends to be slower than other base graphic system.

- It may sometimes be difficult to determine whether what you want to see in the graphic is an aesthetic, or a fixed values  (takes a couple of tries to wrap your head around it).

- Although tidy data works beautifully with ggplot2 (and the GoG paradigm), that means that you may need to invest sometime/code tiding your data. It is be harder to pass on to ggplot2 an `aes()` if data is not tidy. You may end up having multiple geom layers. 
