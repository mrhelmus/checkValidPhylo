# checkValidPhylo
A function to check the validity of "phylo" objects in R

This function takes as single argument an object (phy), checks its elements, and prints a diagnostic. All problems are printed with a label: FATAL (will likely cause an error or a crash) or MODERATE (may cause some problems).

Exemple:

```r
> source("checkValidPhylo.R")
> library(ape)
> tr <- rtree(3)
> checkValidPhylo(tr)
Starting checking the validity of tr...
Found number of tips: n = 3 
Found number of nodes: m = 2 
Done.
> tr$edge[1] <- 0
> checkValidPhylo(tr)
Starting checking the validity of tr...
Found number of tips: n = 3 
Found number of nodes: m = 2 
  MODERATE: the matrix 'edge' is not stored as integers
  FATAL: some elements in 'edge' are negative or zero
  FATAL: all nodes should appear at least twice in 'edge'
Done.
```
