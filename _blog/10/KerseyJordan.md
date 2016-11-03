---
title: "Dynamic documents"
author: "Jordan Kersey"
topic: "10"
layout: post
root: ../../../
---

## Dynammic Documents
A dynamic document, are helpful in easy manipulation for varying audiences or presentation-types. By holding information and producing graphs in the form of reproducible research, as one desires different outputs, it can easily be created.
According to the authors, "reproducible research" is that which includes an accompanying software, that allow readers to directly reproduce the results that were presented.  Considering that much of science involved collaboration, this is a wonderful attribute for data (and its analysis forms) to maintain. Without software programming, there is not a simple way to include both the author and reader in the analysis of the data.

## The Compendium
This refers to the "live" form of a document, which includes data, code, text, and figures, which can all be manipulated and used to one's advantange as either a reader or original author. Within this compendium, there are code chunks, which provide details and create outputs of various analysis.  Text chunks describe the results of the code, and can also interpret the figure of data.  Text chunks are intended to be read.

The software that is included in the compendium does not simply represent "R" or the like, but instead, it describes the functions contained within the program, which make it easier to solve problems within data (compute within code chunks).

Transformers are also an integral part of a dynamic document.  These provide the means for generating some kind of output, such as a webpage or static paper.  

All of the components are distributed together, which makes the entire composition "dynamic" and allows for interactions between multiple parties.

One important factor of reproducible research, and a positive piece of a dynamic document, is that a compendium allows the reader to exactly replicate the analysis.  This is an important aspect of good science, and therefore is beneficial from many angles.  This also allows for zooming-in on different pieces at greater detail, while also allowing for skimming of just important concepts.
It is also a way to distribute computational details, in a way that allows others to view the methods involved in the conclusions drawn. Algorithmic descriptions are often more useful if they are in the form of runnable code.

Principles of Dynamic Documents
1. Literate programming: a document with a mixture of code segments and text segments. This includes tangling and weaving. Tangling suppresses textual content and arranges code in sequence that allows machine processing. Weaving produces a document that is suitable for human-viewing, displaying code and its annotations.
2. Reproducible Research: each piece of a dynamic document is enclosed in one place, allowing for ease of repeatition and easy-access by readers.
3. Software components: Includes "authoring software", used to intergrate code and text descriptions; "auxillary software", used for compiling functions and datasets to be combined with the entire document; "transformation software", which include tools for processing data to yield various outputs; "quality control software", used to validate/test a compendium; and "distribution software", used to provide access to many and a form of management of the compendium.
4. Language: This involves the components which implement the compendiums through a variety of programs, and allows for the processing in different forms by the user/reader.

##The future...
One thing that the future likely holds for dynamic documents is multi-language compendiums, which include different system use for various pieces of the total compendium. To go along with this, conditional chunks may become useful so that the user/reader can ignore certain languages they are not currently using, and access only certain conditions at once.
Also, interactivity is something that will likely become more prevelent, as the possibilities of data management/analysis grow.  Interactive documents are more useful to the user/reader if they are attempting to forward the existing data.

Another key factor which defines the positives of reproducible research, is the level of organization that it implies. By putting data and its components into this format, the user automatically has obtained a certain level of organization. This is huge, when non-dynamic data is very easily too disorderly to be functional.

Ideally, one should keep and use data in a dynamic format ALWAYS.  By getting in the habit of this, one can continue to grow in their data stewardship and also be ready to learn the new techniques which will, most definitely, come into existence.
