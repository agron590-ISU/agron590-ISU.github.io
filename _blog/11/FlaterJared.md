---
title: "The Literate Donald"
author: "Jared Flater"
topic: "11"
layout: post
root: ../../../
---
![](images/knuth_jf.jpg)

## Thoughts:

["Literate Programming"](https://channel9.msdn.com/Events/useR-international-R-User-conference/useR2016/Literate-Programming)

I think the concept of literate programming really makes sense, however, I'm not sure it is the solution for all programming. The idea behind literate programming is to write code for more than just the computer to read, to approach it more as literature for human understanding. I think this is a great approach and we have really been using it in our homeworks with Rmarkdown, the homeworks are often comprised of code and english word sections to describe what the code is doing. 

## "#" Commenting your code:

As we comment our code, we are really implementig literate programming. Though I would like to pose a counter argument, that we should be able to write code for most applications that should be understandable by the reader. Good code shouldn't need a lot of comments saying what it's doing. Second, if your code isn't readable as code, then it stands to reason that your language skills might be equally hard do understand. 

## History:

In the context of Knuth's era when he concieved literate programing, the programming languages were not as high level as they are now. Much of the coding we are doing in R or Python is much more human readable then lower level languages. 

### In R:

{% highlight r %}
cat('Hello, world!
')
{% endhighlight %}



{% highlight text %}
## Hello, world!
{% endhighlight %}

### In Python:

{% highlight python %}
print "Hello, world!"
{% endhighlight %}




{% highlight text %}
## Hello, world!
{% endhighlight %}

As we can see, we might consider Python slightly more "lieterate" than R, specifically the cat function...it's not intuitive how that got there or what it means. Now compared to Python, it's pretty obvious what's going on, but both are far from being not readable by humans. 

## Conclusion:

I believe that lieterate programming has useful applications, specifically for creating dynamic documents or walkthroughs as well as for translating code containing manuscripts into operable documents. However, some arguments can be made that it isn't a silver bullet, not that I believe Donald would be arguing that.

![](images/matrix_jf.gif)


