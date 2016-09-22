---
title: "What is \"normal\" anyways?"
author: "Rafael Martinez-Feria"
topic: "04"
layout: post
root: ../../../
---
## The five normal forms

Normal? What does _normal_ mean? 

The basic idea of behind **database normalization** is provide a "standard" form for data base organization that reduces data redundancy, improves data integrity, and prevents update anomalies and data inconsistencies. The principles behind normal forms as well as relational database theory were laid out by Codd ([1970]( https://www.seas.upenn.edu/~zives/03f/cis550/codd.pdf)), but in his classic article Kent ([1983](http://www.iai.uni-bonn.de/III/lehre/vorlesungen/TDWA/WS07/1.pdf)) presented these concepts in much simpler terms, making it accessible to a larger audience.

According to the paper, there are five main *normal* forms. 

### 1st normal form
1st NF says that all occurrences of a record type must contain the same number of fields, which essentially means that data tables should be a "rectangle". No more or no less than _one_ data items per field. 

### 2nd normal form

A table is in 2nd NF if it is in 1st NF and every non-key field column of the table is dependent on the whole of the key fields (this is only relevant for composite keys). So we end up having different tables: one each column relationship to the subset of the pertinent keys or to exactly the whole key.

### 3rd normal form
The 3rd NF is similar to 2nd NF, with the difference that every non-key column on a first table are  dependent (the key) to another table.

### 4th normal form
A table in 4th NF should not contain two or more independent multi-valued facts about an entity (tipically an issue with many-to-many relationships). For instance, two tables that list the languages, computer and spoken languages that I know:


|Name   |Spoken_Languages |
|:------|:----------------|
|Rafael |Spanish          |
|Rafael |English          |



|Name   |Computer_Languages |
|:------|:------------------|
|Rafael |R                  |
|Rafael |SAS                |
|Rafael |Javacript          |
|Rafael |HTML               |
|Rafael |...SQL?            |

### 5th normal form 

It generalizes the all the other normal forms and allows for reconstruction of information from smaller pieces of information. This helps to maintain the database with minimal redundancy. In most cases, however, any table that conforms to 4th NF will also be in 5th NF. 


## What is in it for me?

I think I already knew this intuitively: keeping data in smaller pieces (tables) and avoiding redundancies makes for an easier-to-manage dataset. I always try to keep an observations table that contains keys for the plot and time when it was collected, and a separate table for plot-treatment information (like management or location). However, having _formal_ knowledge of forms in which data bases can be organized is useful to be able to communicate with others (and to certain extent with myself) more effectively about how design and maintain databases.

## References

- Kent, W. 1983. "A Simple Guide to Five Normal Forms in Relational Database Theory". Communications of the ACM 26(2), 120-125.

- Codd E. F. 1970. "A Relational Model of Data for Large Shared Data Banks". Communications of the ACM 13(6), 377-387.


