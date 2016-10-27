---
title: "Grammar of Graphics"
author: "Victoria Walker"
topic: "09"
layout: post
root: ../../../
---

## 40 pages of Grammar of Graphics

There are 7 orthogonal components of Grammer of Graphics (GoG): variables, algebra, scales, statistics, geometry, coordinates, and aesthetics. Every combination of aspects between these components are valid, however they must be computed in the same order as in the data flow (as listed above) to avoid scientifically sketchy results. The purpose of GoG is create a standard for manipulating data tables and creating statistical graphics. This should result in more concise (and therefore easier to follow) code and graphics. In addition, the separation of analysis method and geometric representation allows for a more robust set of potential graphics.

One way we've already used GoG in class is obvious: we've used the ggplot2 and qplot functions (based on GoG) to perform simple computations and graph the results. Both GoG and the majority of our class seem to have the same fundamental concept: that data, analysis, and representation should be concise, standardized, and reproducible.
