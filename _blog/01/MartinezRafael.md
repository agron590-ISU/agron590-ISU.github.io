---
title: "Blog post #1: My worst data experience"
author: "Rafel Martinez-Feria"
topic: "01"
layout: post
root: ../../../
---

## A rookie mistake

As graduate students we often have to quickly learn how to navigate classes, academia, and research (all at the same time), and with little or no instruction. Interestingly, we are expected to come up with a research project shortly after entering the program to be on target to graduate on time (agronomy students need at least 2 years of field data to write anything meaningful in the thesis). But the classes meant to teach how to properly design and conduct field research are 2 or 3 semesters away. So, many times we are left to play it by ear, and figure out A WAY of accomplishing something out of our time in gradschool. This exercise may be beneficial in the long-term (we are developing problem-solving and reasoning skills) but surely it is stressful when you are a newbie.

I can think of many times during my Master’s when I felt like I did not know what I was doing (as shown in the figure below). This was especially true when organizing my field data (I’ve recently gone back to some of those old folders and left with a bit of PTSD). But there is a specific example that I recall that both, makes me shriek at how I decided to approach the problem, but also shows me how far I’ve come.

<center><img src="images/idk_dog.jpg"/></center>

This was, I think, on the 2nd semester of my MS program. I was interested in obtaining a database for weather data for stations in Iowa. I found a bounty of data at the [Iowa Environmental Mesonet](https://mesonet.agron.iastate.edu/) but did not take the time to find out how to properly access the data base. Instead, I decided to download individual [reports](https://mesonet.agron.iastate.edu/climodat/) as txt files for each of the 110 weather stations I was interested. The files I got looked something like this: 

```
  # IEM Climodat http://mesonet.agron.iastate.edu/climodat/
  # Report Generated: 31 Aug 2016
  # Climate Record: 1893-01-01 -> 2016-08-31
  # Site Information: [IA0200] AMES-8-WSW
  # Contact Information: Daryl Herzmann akrherz@iastate.edu 515.294.5978
  # LENGTH OF SEASON FOR STATION NUMBER  IA0200   BASE TEMP=28
  # LAST SPRING OCCURENCE FIRST FALL OCCURENCE
  
   YEAR MONTH DAY DOY         MONTH DAY DOY   LENGTH OF SEASON
   1893   4    24 114           9    28 271          157
   1894   4     9  99          10     9 282          183
   ...
   ...
   2014   4    18 108          10    31 304          196
   2015   3    28  87          11    21 325          238
   MEAN   4    12 102          10    21 102          192

```
Of course, I got my undergrad aid involved in this mess, and it took us several days to download all the reports and stich them back together into a single excel file. Then, I did all the data transformations, summaries and pivoting within this file, but with 300,000+ rows Excel kept crashing when I was trying to do the simplest of tasks. You can guess how many “weather-summary-final-version10.xlxs” files I ended up with. So it took me about 2 weeks to get anything meaningful from this dataset, only to find out later that we have made plenty of mistakes when copying and pasting the data. To make things worse I realized later that the complete dataset could be also downloaded on a [single file format](https://mesonet.agron.iastate.edu/request/coop/fe.phtml).

This was one of my first experiences with data processing, way before I had any real coding skills. Today, this task would take me a few hours of work in R. More importantly, I would have been able to track my work and avoid copy-paste gaffes. I guess this experience did teach me about the perils of data-recklessness.
