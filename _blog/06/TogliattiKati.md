---
title: "The Making of R"
author: "Kati Togliatti"
topic: "06"
layout: post
root: ../../../
---

## Blog 6:

R is a combination of the languages S and Scheme. S was used for the looks of R and Scheme was used for the underlying implementation and semantics. The designers originally wanted development of R to be done on Unix workstations, but then decided to target 32-bit machines. To make the portability of this language easier they coded R in standard C. They stated that writing in C makes the code compact and efficient. Something interesting was that they could not directly use FORTRAN code so they had to use f2c to make the code available for them. FORTRAN is still widely used for weather models and I found it interesting to see that it still has other applications today. A problem with R is that everything must be stored internally. They give an example in the article that if R were to crash and you had not saved the environment all of your work would be deleted and non-recoverable. Overall, it was beneficial to read about how R was made and the steps that the developers took to make it a working language.  
