---
title: "Literate programming"
author: "Victoria Walker"
topic: "11"
layout: post
root: ../../../
---

The idea of literate programming is that you write as if you are explaining to a human what you tell the computer, rather than writing strictly formatted instructions for the computer. Donald Knuth started working on literate programming after he was asked to publish TeX in a book; he felt that the code was not presentable. His vision of literate programming combines the code and documentation into a single project. Each section of the document (e.g., input, plan, output, steps of the program, and an index) starts with commentary (plain-English) and then presents the code. This allows for the document to be ordered in a way humans follow processes, as opposed to the format that is required for the compiler. This WEB file can either be weaved, where the document is formatted as a TeX-ready file, or tangled, where the document is formatted as a compiler-ready file.

At the end of Donald Knuth's paper on literate program, he states that if many people take interest in WEB it is possible that an effective unified system (that can both tangle and weave) will likely be created. I would say that R Markdown is an example of today's unified system, as we can create a type-set document and run code from the same (.Rmd) file. However, I wouldn't describe R Markdown as literate programming (as Knuth envisioned) as code chunks are still handled as if they are a tree (linear)  rather than a web of connected components.
