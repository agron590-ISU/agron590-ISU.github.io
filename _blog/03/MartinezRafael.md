---
title: "Relational DBs are dead, long live relational DBs!"
author: "Firstname Lastname"
topic: "03"
layout: post
root: ../../../
---

### 1. How can relational databases help you with your research?

The main advantage of using relational databases in my research program would be that it would allow for a more structured and cleaner management of the my data compared to what I do now (csv files and R scripts). Since my reseach data reasearch data grows relatively slowly (add observations every 10-15 days), it may also allow for esiser (and perhaps more automated) data entry. 

### 2. Is there any aspect of them that makes them a poor fit for you?
I cannot really think of anything major that would turn me off using RDB's other than perhaps most (if not _all_) of the methods impremented in SQL can be also implemented in `R` using packages such as `dplyr` and/or `reshape2`, which may tempt me to stick to what I already know. Another issue may be compatibility and portability; what if I built my DB in SQLite? Can someone else view my data in mySQL or PostgreSQL? Seems much easier to send my data to my collaborators in .csv format.

### 3. What other types of databases are there?

There are many types of databases. In the simplest of terms, a folder containing a bunch with .xls or .csv files with your field data could be considered your 'database', even when these files may be poorly organized. But when talking about other _formal_ database formats, that I can think of a couple: 

* Spatial databases: These are similiar to relational databases (maybe more like a special type of RDBs). They are basically a database that is optimized to store and query data that represents objects defined in a geometric space. So here the "things" are objects in space (points, lines, polygons) with certain attributes.

* Document-oriented databases: These are collections of semi-structured data that allows for toring, retrieving, and managing data based on document attributes. Documents can be written in languages like XML, YAML or JSON. These is often how the so-called "big-data" are stored.
