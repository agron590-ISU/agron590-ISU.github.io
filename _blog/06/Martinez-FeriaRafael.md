---
title: "In the beginning..."
author: "Rafael Martinez-Feria"
topic: "06"
layout: post
root: ../../../
---
Today, the R programming language is being adopted by an ever greater number of academics and enterprise users for wide array of applications. From big data analytics to database management (through integration with SQL), and interactive web data apps, the R community is a growing force, challenging more traditional statistical and analytics platforms. But, what makes R so special? Where does R come from anyway? 

A good place to start searching for answers is Ihaka and Gentleman’s 2001 paper "[R: A Language for Data Analysis and Graphics](http://biostat.mc.vanderbilt.edu/wiki/pub/Main/JeffreyHorner/JCGSR.pdf)". This paper gives some interesting insights on how the R language was developed.

## R starts with S

R is a programing language that was developed specifically for statistical analytics and graphics. As such, much of its functionality is geared to manipulating and storing data.

Ihaka and Gentleman’s describe that the key to R was to integrate useful features from the scheme language with a S-like syntax. So we can think that R is basically a different implementation of the S language and environment. For its part, S is a 40-year old language  developed at Bell Laboratories. The video below contains a lecture by Richard Becker describing a bit of history of how the S language came about.

<iframe src="https://channel9.msdn.com/Events/useR-international-R-User-conference/useR2016/Forty-years-of-S/player" width="560" height="315" allowFullScreen frameBorder="0"></iframe>

Of course, there are some important differences from S and scheme. But the syntax is similar enough that much of the S code runs in R. The happy marriage provided advantages in key areas such as portability, computational efficiency, memory management, and scoping.

### The important differences

- Environments and scoping: In S, variables in functions are either local or global, while in R functions access the variables which were in the environment when the function was defined. In the following example taken from [Ross Ihaka](https://cran.r-project.org/doc/html/interface98-paper/paper_1.html) there are multiple environment frames in which the variable `n` is assigned. The function `count` returns a value which is itself an inner function that increments the value of the variable `n`, and then returns the value of that variable. Here we have created a variable which only the inner function can see and manipulate. Note that here assignment operator `<<-` is used to allow for the variable to be available within a larger environment frame. 




{% highlight r %}
n <- 10
count <- function(n = 0)
  function() {
    n <<- n + 1
    return(n)
    }

counter <- count()
counter()
{% endhighlight %}



{% highlight text %}
## [1] 1
{% endhighlight %}



{% highlight r %}
counter()
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
counter()
{% endhighlight %}



{% highlight text %}
## [1] 3
{% endhighlight %}


- Memory managment: R allocates a fixed amount of memory at startup and manages it on the fly. This means that there R won’t try to use more memory than what it has available, but this also may aslo result in lower computing speeds.

### Summary

With its `S`-like syntax and its `scheme` legacy, R offers a relatively straight forward, yet flexible language for of users to develop a wide array of applications. 
