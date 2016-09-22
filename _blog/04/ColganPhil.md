---
title: "Article Review"
author: "Phil Colgan"
topic: "04"
layout: post
root: ../../../
---

This article by William Kent, "A Simple Guide to Five Normal Forms in Relational Database Theory" describes methods of normalizing the structure of relational databases to avoid various issues. I learned from the second and third normal form that splitting up a larger record can help avoid redundancy and generation of inconistent data, but this also introduces some level performance cost because a query has to search multiple records and make the connection between them as opposed to searching one larger record. The fourth and fifth normal forms pertain to multivalued facts and attempt to simplify composite keys to keep each fact distuingishable from one another.  Most of the issues these rules seem to cause issues when updating/maintaining a database, so i will have to keep them in mind if i ever make one.

