---
title: "Square peg, meet round hole"
author: "Jared Flater"
topic: "05"
layout: post
root: ../../../
---

# Read Hadley Wickham's Tidy Data paper here: http://vita.had.co.nz/papers/tidy-data.pdf

# What is tidy data and how does it relate to the data modeling topics that we have already discussed in this class? What are the benefits to keeping data "tidy"? Are there any drawbacks?
![](images/peg.jpeg)

  Simply put, tidy data is just that, tidy. Data that is put in it's proper place, much like you would do to a messy room, is tidy. Variable out of place? Put it somewhere! Empty cell? Fill it! Tidy data is data that is well organized and free of errors, that is easily digestible by computational software to help us better answer the real questions we are after, not spend hours sifting through messy data just to get it into shape for analysis.
  
  The main point of Hadley Wickham's article was that a structured data set is a good data set. The term "tidy" is similar in meaning to the normal forms we have already learned, except that it mainly pertains to a single data set, not the relational data sets that Codd's forms refer to. 
  
  From the article: ''Tidy data has each variable forming a column, each observations forming a row and each type of observational unit forming a table''
  
  As mentioned, tidy data is very closely linked to normalization, something that we have learned is very important when working with relational databases.
  
  However, while tidy data may make the most sense for analysis... it doesn't always lend itself to easily digestible information by humans. There may be cases when it just makes more sense to have variables in multiple columns, for visualization purposes. 
  
  The obvious benefits to tidy data are that it is a standard, one that is easily shared. Additional, analysis of said data will be much more straight forward when in a tidy form. I found this article very helpful and easier to understand than Codd's normal forms, something I have been struggling with understanding as we move further into database management.  

  
