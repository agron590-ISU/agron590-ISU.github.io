---
title: "Literate programming"
author: "Rafael Mrtinez-Feria"
topic: "11"
layout: post
root: ../../../
---

Literate programming (LP) is the idea that computer code is not only read by the computer, but also read by people. This comes in handy  when writing complicated code to solve complext tasks. In LP, the syntax is the same as traditional programming languages, but with the documentation wrapped around it. In it's [1984 paper](http://www.literateprogramming.com/knuthweb.pdf), the creator of LP Donald Knuth explains his vision:

> Instead of imagining that our main task is to instruct a computer what to do, let us concentrate rather on explaining to human beings what we want a computer to do.

Knuth first implemented literate programming in the 1980's with his web of abstract concepts (WEB) system which ran in `Pascal`. The he adapted the implementation to `C` (thus CWEB), which runs on  operating systems and can produce TeX and PDF documentation. A simplified implementation of WEB was develop by  [Norman Ramsey](http://www.cs.tufts.edu/~nr/) and and packaged into `R` as `noweb` by [Terry Thernau](https://cran.r-project.org/web/packages/noweb/noweb.pdf).

This concept may appear remote for the average R user (non-computer science person), but the fact is that it is the foundation for modern hypertext markup/markdown programming languages and dynamic documents, specially the `knitr` package.


<iframe src="https://channel9.msdn.com/Events/useR-international-R-User-conference/useR2016/Literate-Programming/player" width="470" height="270" allowFullScreen frameBorder="0"></iframe>


## References 

Knuth, Donald E. (1984). "Literate Programming". The Computer Journal. British Computer Society. 27 (2): 97–111. [doi:10.1093/comjnl/27.2.97](http://www.literateprogramming.com/knuthweb.pdf)

