# Matrices in R


## Introduction

In R, a matrix is a two-dimensional array of numbers. Matrices are used to represent systems of linear equations, perform linear transformations, and manipulate data. This document provides an overview of matrices in R and how to apply functions to them as a whole, row-wise, and column-wise.

## Creating Matrices


Matrices can be created in R using the `matrix()` function. The general syntax is:

```r
matrix(data, nrow, ncol, byrow = FALSE)
```

*   `data`: a vector of numbers to fill the matrix
*   `nrow`: the number of rows in the matrix
*   `ncol`: the number of columns in the matrix
*   `byrow`: a logical value indicating whether the matrix should be filled by row (TRUE) or by column (FALSE)

Example:

```r
# Create a 2x3 matrix filled with the numbers 1 to 6
m <- matrix(1:6, nrow = 2, ncol = 3, byrow = TRUE)
print(m)
```

Output:

```r
     [,1] [,2] [,3]
[1,]    1    2    3
[2,]    4    5    6
```

## Applying Functions to Matrices


### Whole Matrix

Functions can be applied to an entire matrix using the `apply()` function. The general syntax is:

```r
apply(X, MARGIN, FUN)
```

*   `X`: the matrix to which the function will be applied
*   `MARGIN`: a vector indicating the dimension(s) over which the function will be applied (1 for rows, 2 for columns, c(1, 2) for both)
*   `FUN`: the function to be applied

Example:

```r
# Calculate the sum of all elements in the matrix
m_sum <- sum(m)
print(m_sum)
```

Output:

```r
[1] 21
```

### Row-Wise

Functions can be applied to each row of a matrix using the `apply()` function with `MARGIN = 1`. The general syntax is:

```r
apply(X, 1, FUN)
```

*   `X`: the matrix to which the function will be applied
*   `FUN`: the function to be applied

Example:

```r
# Calculate the mean of each row
m_row_means <- apply(m, 1, mean)
print(m_row_means)
```

Output:

```r
[1] 2 5
```

### Column-Wise

Functions can be applied to each column of a matrix using the `apply()` function with `MARGIN = 2`. The general syntax is:

```r
apply(X, 2, FUN)
```

*   `X`: the matrix to which the function will be applied
*   `FUN`: the function to be applied

Example:

```r
# Calculate the standard deviation of each column
m_col_sds <- apply(m, 2, sd)
print(m_col_sds)
```

Output:

```r
[1] 1.5 1.5 1.5
```


## Applying Functions to Matrices using lapply, sapply, and tapply

In addition to the `apply()` function, R provides several other functions for applying functions to matrices and other data structures. These include `lapply()`, `sapply()`, and `tapply()`.

### lapply()

The `lapply()` function applies a function to each element of a list or vector and returns a list of the results. It can be used to apply a function to each row or column of a matrix.

Example:

```r
# Create a 2x3 matrix filled with the numbers 1 to 6
m <- matrix(1:6, nrow = 2, ncol = 3, byrow = TRUE)

# Calculate the sum of each row using lapply
m_row_sums_lapply <- lapply(1:nrow(m), function(i) sum(m[i, ]))
print(m_row_sums_lapply)

# Calculate the mean of each column using lapply
m_col_means_lapply <- lapply(1:ncol(m), function(i) mean(m[, i]))
print(m_col_means_lapply)
```

Output:

```r
[[1]]
[1] 6

[[2]]
[1] 15

[[1]]
[1] 2.5

[[2]]
[1] 3.5

[[3]]
[1] 4.5
```

### sapply()

The `sapply()` function is similar to `lapply()`, but it simplifies the result to a vector or matrix if possible.

Example:

```r
# Calculate the sum of each row using sapply
m_row_sums_sapply <- sapply(1:nrow(m), function(i) sum(m[i, ]))
print(m_row_sums_sapply)

# Calculate the mean of each column using sapply
m_col_means_sapply <- sapply(1:ncol(m), function(i) mean(m[, i]))
print(m_col_means_sapply)
```

Output:

```r
[1]  6 15
[1] 2.5 3.5 4.5
```

### tapply()

The `tapply()` function applies a function to each subset of a vector or matrix defined by a factor or list of factors.

Example:

```r
# Create a factor to subset the matrix
factor <- c("A", "B", "A", "B", "A", "B")

# Calculate the sum of each subset using tapply
m_subset_sums_tapply <- tapply(c(m), factor, sum)
print(m_subset_sums_tapply)

# Create a list of factors to subset the matrix
factor_list <- list(factor, c("X", "Y", "X", "Y", "X", "Y"))

# Calculate the mean of each subset using tapply
m_subset_means_tapply <- tapply(c(m), factor_list, mean)
print(m_subset_means_tapply)
```

Output:

```r
 A  B 
 9 12 

  A.X  A.Y  B.X  B.Y 
 2.5  4.5  3.5  5.5 
```


## Conclusion


In this document, we have covered the basics of matrices in R and how to apply functions to them as a whole, row-wise, and column-wise. Matrices are a powerful data structure in R, and understanding how to work with them is essential for data analysis and manipulation. 