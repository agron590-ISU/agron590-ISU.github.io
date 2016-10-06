---
title: "Blog #6"
author: "Victoria Walker"
topic: "06"
layout: post
root: ../../../
---

## The origins of R

Apparently there were once two statistical  data analysis languages: S and Scheme. The developers of R started with Scheme and added S-like features. Perhaps one of the most important features imported from S is the use of "lazy arguments," which allow for function arguments to be available as symbolic variables within the function. This is in comparsion to Scheme, which uses an "eager evaluation" policy where function arguments are evaluated before the function itself. The largest problem in R, inherited from design choices, is that the current environment must be saved internally rather than in a file that can be re-accessed if R crashes. 

