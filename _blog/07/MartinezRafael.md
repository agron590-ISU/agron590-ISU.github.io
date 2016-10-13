---
title: "SAC it to me!"
author: "Rafael Martinez-Feria"
topic: "07"
layout: post
root: ../../../
---

## Now what? 

So you’ve read your data into `R`. You have gone through the trouble of getting familiar with the data structure, and figured out whether each variable matches the correct type (e.g. integer, factor, character, date-time, etc.). You have re-arranged it into a tidy format. You have identified and discarded some obvious outliers using conditional expressions and tried using `subset()` to get rid of some non-interesting values. And now you look at your dataset and realized that you still have multiple observations (perhaps replicates) for every group in your data. So you tell yourself:

> I want to calculate summary statistics for all of these different groups! 

After all, analysis is all about converting data into meaningful information. But how do you go about this? 

## Enter the split-apply-combine strategy (SAC) strategy

An intuitive strategy to go about this is to *split* your data in to unique groups, *apply* certain method (e.g. the computation of the mean or standard error) to the group values, and *combine* individual pieces into a new *summarized* dataset. 

> Wait, doesn't this sound familiar?

Yes, in fact this principle of the SAC strategy is behind the the `SQL` group `by` operator previously discussed in class. For those Excel users, pivot tables work using the SAC strategy.

### Tell me how to do this in R

In the base `R` world, you’d most likely use `for` loops or the `apply` family of functions to split-apply, and `rbind()` to attach the new values to a previously created result data frame. For non programmer folk like us, there is just something unsexy about dealing with loops, list, 3d arrays, etc. Here an example for a for loop using the `InsectSprays` dataset:


{% highlight r %}
data("InsectSprays")
str(InsectSprays)
{% endhighlight %}



{% highlight text %}
## 'data.frame':	72 obs. of  2 variables:
##  $ count: num  10 7 20 14 14 12 10 23 17 20 ...
##  $ spray: Factor w/ 6 levels "A","B","C","D",..: 1 1 1 1 1 1 1 1 1 1 ...
{% endhighlight %}



{% highlight r %}
# Create an df with NAs
(res <- data.frame(spray=unique(InsectSprays$spray), Mean = NA , SD = NA))
{% endhighlight %}



{% highlight text %}
##   spray Mean SD
## 1     A   NA NA
## 2     B   NA NA
## 3     C   NA NA
## 4     D   NA NA
## 5     E   NA NA
## 6     F   NA NA
{% endhighlight %}



{% highlight r %}
for (spray in unique(InsectSprays$spray)){
  res$Mean[res$spray == spray] <- mean(InsectSprays$count[InsectSprays$spray == spray])
  res$SD[res$spray == spray] <- sd(InsectSprays$count[InsectSprays$spray == spray])
}

res
{% endhighlight %}



{% highlight text %}
##   spray      Mean       SD
## 1     A 14.500000 4.719399
## 2     B 15.333333 4.271115
## 3     C  2.083333 1.975225
## 4     D  4.916667 2.503028
## 5     E  3.500000 1.732051
## 6     F 16.666667 6.213378
{% endhighlight %}

Luckily the `plyr` and `dplyr` packages by  [Hadley Wickham](http://hadley.nz/) make SAC strategy second nature, helping you focus on  the important details of the computation and keep you from quarreling with the unimportant book-keeping code.


{% highlight r %}
require(plyr, quietly = T)

ddply(.data = InsectSprays,
      .variables = "spray",
      .fun = summarise,
      Mean=mean(count),
      SD=sd(count))
{% endhighlight %}



{% highlight text %}
##   spray      Mean       SD
## 1     A 14.500000 4.719399
## 2     B 15.333333 4.271115
## 3     C  2.083333 1.975225
## 4     D  4.916667 2.503028
## 5     E  3.500000 1.732051
## 6     F 16.666667 6.213378
{% endhighlight %}

We use the `ddply` becasue we have a **d**ata frame as input and we want a **d**ata frame as output.

`dplyr` is the new iteration of the `plyr`, optimized for working with data frame objects. It makes the innovation of adding the "chain" operator `%>%` to make code more like a grammar structure.


{% highlight r %}
require(dplyr, quietly = T)
{% endhighlight %}



{% highlight text %}
## 
## Attaching package: 'dplyr'
{% endhighlight %}



{% highlight text %}
## The following objects are masked from 'package:plyr':
## 
##     arrange, count, desc, failwith, id, mutate, rename, summarise,
##     summarize
{% endhighlight %}



{% highlight text %}
## The following objects are masked from 'package:stats':
## 
##     filter, lag
{% endhighlight %}



{% highlight text %}
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
{% endhighlight %}



{% highlight r %}
InsectSprays %>%
  group_by(spray) %>%
  summarise(Mean=mean(count),SD=sd(count))
{% endhighlight %}



{% highlight text %}
## # A tibble: 6 × 3
##    spray      Mean       SD
##   <fctr>     <dbl>    <dbl>
## 1      A 14.500000 4.719399
## 2      B 15.333333 4.271115
## 3      C  2.083333 1.975225
## 4      D  4.916667 2.503028
## 5      E  3.500000 1.732051
## 6      F 16.666667 6.213378
{% endhighlight %}

To learn more about the details of the `plyr` package and the SAC strategy, read [Hadley Wickham's 2011 paper](http://www.jstatsoft.org/v40/i01/)
