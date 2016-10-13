---
title: "Hadley: R Lord of ISU"
author: "Jared Flater"
topic: "07"
layout: post
root: ../../../
---
# Read Hadley Wickham's Split-Apply-Combine paper here: http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.182.5667&rep=rep1&type=pdf

# What is the split-apply-combine strategy and how is it used in the process of data anlysis? Where have we already seen/used the split-apply-combine strategy in this class? What are some advantages of using the split-apply-combine strategy?

![](images/homer_split.gif)

SAC or split-apply-combine is a strategy for data analysis useful whenever breaking up of data into smaller chunks is necessary to ease analysis. This is usually followed by application of said analysis to all chunks and assembly of said analyzed chunks into something useful.

The SAC strategy is applied to data sets where one action may be better of performed on a small subset of data. For my use, this could be useful in terms of the size of our data...often in the 10s of gigs. Imagine a function applied that takes days to run through all the samples. What if you get an error at the end of those days? Wouldn't it make more sense to apply your function to a small, digestible in hours, set of data? Human time is more valuable than computer time, it's apparent the the SAC strategy could be used to make better use of time. 

Another benefit of Hadley's plyr package and the SAC strategy is the simplification of code. When transforming a variable in a data set over many variable, a for loop is often used. However, plyr allows for a much simpler chunk to achieve the same result. 

For loop example: 

{% highlight r %}
models <- as.list(rep(NA, 24 * 24))
dim(models) <- c(24, 24)
deseas <- array(NA, c(24, 24, 72))
dimnames(deseas) <- dimnames(ozone)
for (i in seq_len(24)) {
  for(j in seq_len(24)) {
    mod <- deseasf(ozone[i, j, ])
    models[[i, j]] <- mod
    deseas[i, j, ] <- resid(mod)
  }
}
{% endhighlight %}

plyr example:

{% highlight r %}
models <- aaply(ozone, 1:2, deseasf)
deseas <- aaply(models, 1:2, resid)
{% endhighlight %}





The advantages of this strategy or at least a subset of it were made apparent to me as I tackled our homework for next week. We are given two data sets, one for DC and one for Marvel comics and asked to investigate said data, to facilitate my analysis (comparison) of these two publishers, I wanted to combine the two data sets into one data frame while adding a column to identify DC vs. Marvel. I used the rbind function to achieve this:


{% highlight r %}
marvel<-read.delim("marvel-wikia-data.csv", sep=",") #Read in Marvel data
dc<-read.delim("dc-wikia-data.csv", sep=",") #Read in DC data
colnames(marvel)[13]<-"YEAR" #Change last column to YEAR in Marvel to match YEAR in DC
dc$publisher<-"DC" #Add publisher col
marvel$publisher<-"Marvel" #Add publisher col
df<-rbind(dc, marvel) #Bind both tables into one data frame
{% endhighlight %}
![](images/bart_lisa_combine.gif)
