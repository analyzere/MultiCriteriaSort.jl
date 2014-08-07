# MultiCriteriaSort

This is package extends the capabilities of the sorting functions to sort entire matrices on a set of columns/rows that are defined in set terms of descending priority.

## New Sorting Methods

The `sort!`, `sort` and `sortperm` functions may be provided with an additional argument, `keys::Vector{Int}`, when provided with a `AbstractMatrix` to sort. The keys are an array of column or row indices that define which indices to sort on in descending order of priorty.

To sort a matrices rows using columns 1, 2 and 3 to sort:
``` a = [1 3 2; 1 2 3; 1 1 1; 3 4 4; 3 4 1; 3 4 2]
    sort(a, [1:3])```
    
Similarly to get the row permutation to sort the matrix use `sortperm(a, [1:3])`.

Each function is given an optional `dim::Int` argument which defines which dimension to sort (i.e. 1 = sort rows by values in given columns and 2 = sort columns by values in given rows). To sort the columns in matrix `a` by rows 1 and 2 use `sort(a, [1,2], dim = 2)`. 