---
title: "Tidy data"
author: "Rafael Martinez-Feria"
topic: "05"
layout: post
root: ../../../
---

So you have learned about SQL and relational databases in previous weeks, and you are feeling excited about figuring out how you can integrate these new tools (well… new to you) in to your research work. Surely soon there will be plenty of opportunities for building your own databases optimized for seamless data entering, storage and analysis workflows. That's all good and all, but the universe outside the relational database galaxy will continue to be messy. To venture into (in)possible missions like sharing data with other scientists (or your former self), web data scraping, or even, **big data** analysis, you need to know how to deal with messy data.

Enter Hadley Wickham.

Somewhat of a `R`ock star, he is well known for his contributions to the world of data wrangling and visualization, and for `R` packages like `ggplot2`, `dplyr` and `reshape2`. In [this 2014 paper](http://vita.had.co.nz/papers/tidy-data.pdf), Wickham tells us why we should care about the way we structure datasets, and the benefits of keeping data tidy. 

### Wait, tidy data?

Data tidying is an important aspect of data cleaning: structuring datasets to facilitate analysis. It is a standard way of mapping the meaning of a dataset to its structure. Wickham describes in rough term that whether a dataset is messy or tidy depends on how rows, columns and tables are matched up with observations, variables and types. In a tidy dataset: 

1. Each variable forms a column.
2. Each observation forms a row.
3. Each type of observational unit forms a table.

Some people refer to as to making wide and shot datasets into tall and skinny. 
This is really just like 3NF of database normalization, but instead the focus is on a single dataset rather than the many connected tables. A dataset is messy with any other arrangement of the data. 

### What is the benefits to keeping data *tidy*?

Because tidy data provides a standard way of structuring a dataset, it facilitates the analyst’s (or a computer’s) job of extracting values from needed variables. With messy data, sometimes values are stored in the names of the (header) of the columns, and extracting this information for analysis may prove difficult. Or maybe a column may contain multiple values in one cell (e.g. the combination of site and treatment), which may interfere when modeling the data. Tidying is done to make sure that the data is ‘analysis ready’.

### So what is the catch? 

There are a couple reasons why you wouldn’t want to tidy up your data. For instance, in large datasets (>500k observations) procedures of melting or casting may get to be a bit slow, or errors may be hard to catch. However, the principles of data tidy is definitively a good practice for those that want to keep their data within reach for analysis, manipulation and data visualization.
