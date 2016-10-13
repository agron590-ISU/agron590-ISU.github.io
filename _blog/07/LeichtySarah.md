---
title: "SAC it to me! Blog"
author: "Sarah Leichty"
topic: "07"
layout: post
root: ../../../
---

## HW 7:

The split-apply-combine strategy is where a large problem is broken up into more manageable pieces. Once these pieces are operated on individually, the whole problem is put back in one coherent piece.

It is used in the process of data analysis by allowing the user to group data together in easier ways or model data with different models.As far as using the plyr R package, less for loops are necessary. Without this extra code, the important objectives of the code are front and center. With less book-keeping code, the essential code is not hidden.  

We have already seen or used the split-apply-combine strategy in this class when dividing tables in a relational database and then creating joins between tables to relate tables to one another. By changing bits of smaller tables and then relating those to other small tables, different characteristics can be changed without the whole data set needing to change. This has helped me to keep factors separate and look at a few variables at a time when searching for connections.  

Some advantages of using the split-apply-combine strategy are that instead of having to worry about figuring out how to change data from a 2d array to another array form, the plyr package takes care of these tricky details. The main advantage of using plyr when organizing data is that it replaces for loops in a variety of problems, thus more clearly describing the goals of the code. 

Interesting points from the paper: 
split with split()
apply with lapply()
combine with rbind()
refer to entire row with d*ply
refer to entire column with *dply

. Arrays are sliced by dimension in to lower-d pieces: a*ply()
. Data frames are subsetted by combinations of variables: d*ply()
. Each element in a list is a piece: l*ply()

plyr takes this code example:
pieces <- split(ozonedf, list(ozonedf$lat, ozonedf$long))
models <- lapply(pieces, deseasf_df)
results <- mapply(function(model, df) {
cbind(df[rep(1, 72), c("lat", "long")], resid(model))
}, models, pieces)
deseasdf <- do.call("rbind", results)

and changes it in to this: 

models <- dlply(ozonedf, .(lat, long), deseasf_df)
deseas <- ldply(models, resid)




