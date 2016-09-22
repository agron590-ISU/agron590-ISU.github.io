---
title: "What is \"normal\" anyways?"
author: "Jordan Kersey"
topic: "04"
layout: post
root: ../../../
---


# Normalization, 
as I understand it from the article, is a way of organizing and keeping one's data in order for easier editing, storage, and usage in the future. As introduced, it appears to be a set of rules compiled to make one's data design more successful.

1. First normal form simply implies that all records (occurances of) must contain the same number of fields.

2. Second normal form relates key and non-key points to one another, and how they must be organized.  If a non-key fact is a fact about a sub-set of the key, then it violates this rule, and must be separated into two individual records to satisfy both first and second normal form.

3. Third normal form is very similar to second normal form, and is dealt with in a comparable nature.  This rule is violated by one non-key field being a fact about another non-key field.  This problem can be adjusted by separating the conflicting non-key fields into two records.

4. Functional dependencies help to keep things organized by suggesting that each Y-value must correspond to a single X-value, and that relationship must be consistent. 

5. Fourth normal form (and fifth normal form) deal with multi-fact keys. Fourth normal form states that one record type shouold not contiain two or more independent, multi-valued facts about one subject.  They should be separated into two records.
Violating fourth normal form leads to three problem-causing table formats.  
  * Disjoint format- leaves blanks which are ambiguous
  * A random mix (three variations)
    + Minimum records with repetitions
    + Minimum records with null values
    + Unrestricted (messy)
  * Cross-product form where you get repeated pairings in order to satisfy every possible pairing.

6. Independent multi-valued facts can be disregarded by the previous rules, because pairings do not convey any information.

7. Finally, fifth normal form is a record type in which its information cannot be reconstructed from several smaller record types.It also agrees with all of the preceeding normal forms.

ALthought, this paper was a good introduction, I still feel I need a bit of experimenting with design in order to completely comprehend what all of these normalities mean in the real world. I do, however, see how following these rules will allow for more organized and tidy data design.  I can see it being very useful for organizing data into blocks, which would ultimately allow for greater manipulation.

![](http://media.giphy.com/media/cLtvKDcQYkSRO/giphy.gif)


