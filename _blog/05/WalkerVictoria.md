---
title: "Tidy data --vawalker#5"
author: "Victoria Walker"
topic: "05"
layout: post
root: ../../../
---

## Tidy data

Tidy data is a standard where data is structured so that rows are observations and columns variables. I didn't realize that people's data wasn't structured this way? Our raw data (binary or .csv) are put into .csv files as in Table 12(b); these tables are then "stacked" into matlab structures, netcdf, or hdf5 files. This allows for the dataset to be manipulated using matrix operations (logical for sort/filter/etc. and mathematical for analysis) and shared as a single file. The downside to this is the potential for metadata loss, but for filetypes such as netcdf or hdf5 metadata can be stored as a header. I think that the strongest relation between tidy data and the topics discussed in class is that data, structured to reduce/eliminate redundancy, should be stored in the form that makes analysis easiest to reproduce.

