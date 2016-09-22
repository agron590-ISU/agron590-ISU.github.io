---
title: "What is \"normal\" anyways?"
author: "Laila Puntel"
topic: "04"
layout: post
root: ../../../
---

The focus of this article is about normalizing the design of a database to avoid inconsistencies and make it easier to use, edit, and store. The author explain the main rules to accomplish that:
1) Al records must contain the same number of fields.
2) and 3) Is about key and non-key. An on-key field must relate and provide a fact about the key. If a non-key fact is a fact about a sub-set of the key, then needs to be separated into 2 records
4) and 5) talks about the dependencies between the stablished relationships (like many-to-many and many-to-one relationships). The author suggest to minimize the number of fields that are involved in a composite key and keep these facts independent.
Definitely this rules would help you to normalize your databases but as the author mentioned there some things like redundancies that could be unavoidable, particularly when several multivalued facts are dependent rather than independent; or when redundancies occur across multiple record types (INTER-RECORD REDUNDANCY). 
The examples provided in this articles where very helpful to better understand the applicable side of all these theory.
