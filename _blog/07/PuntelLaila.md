---
title: "SAC it to me!"
author: "Laila Puntel"
topic: "07"
layout: post
root: ../../../
---


**What is the split-apply-combine strategy and how is it used in the process of data anlysis?**

According to Hadley Wickman "SAC" is the the process of:

"split": breaking up data into pieces 

"Apply": working on each piece individually

"Combine": putting the pieces back together

The "plyr" R package meant to perform SAC all at once and in a more computationally efficient way providing a replacement for loops that tend to have the disadvantage of book-keeping code. The "plyr" package is careful in not to make an extra copy of the data in the split step, the author concluded. 

The use of SAC process facilitates the data preparation and analysis by allowing the user to apply different modeling estrategies for each component of the data or for the combined version of the data.


**Where have we already seen/used the split-apply-combine strategy in this class?**

We appliy Split-apply-combine strategy by using: SQL databases, using this thecniques we split the data into pieces that are connected with a common key that allows us to use tools to combine those different pieces back together in different ways to facilitate the analysis. We also apply SAC in class by using R software to subset, clean , and organize data. 


**What are some advantages of using the split-apply-combine strategy?**

Better explore and understand your data

Facilitates data visualization operations

Helps you and anothers to find and fix problems in your data

Solve common data analysis problems

Useful when teaching others how to do data analysis

![](images/giphy_lap.gif)


