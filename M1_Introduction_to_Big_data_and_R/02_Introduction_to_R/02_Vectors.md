# Vectors in R

## Introduction


Vectors are the most basic data structure in R. They are a collection of elements of the same data type. In this README, we will cover the different types of vectors, their creation, length, traversal, modification, deletion, and sorting.

## Types of Vectors


There are several types of vectors in R:

*   **Numeric Vectors**: These are vectors that contain numeric values.
*   **Character Vectors**: These are vectors that contain character strings.
*   **Logical Vectors**: These are vectors that contain logical values (TRUE or FALSE).
*   **Factor Vectors**: These are vectors that contain categorical data.

## Creating Vectors


Vectors can be created using the `c()` function, which combines the elements into a vector.

```r
# Create a numeric vector
num_vector <- c(1, 2, 3, 4, 5)

# Create a character vector
char_vector <- c("apple", "banana", "cherry")

# Create a logical vector
log_vector <- c(TRUE, FALSE, TRUE)

# Create a factor vector
fac_vector <- factor(c("male", "female", "male"))
```

## Vector Length

The length of a vector can be determined using the `length()` function.

```r
# Get the length of a vector
length(num_vector)
```

## Traversing Vectors


Vectors can be traversed using a for loop or the `sapply()` function.

```r
# Traverse a vector using a for loop
for (i in 1:length(num_vector)) {
    print(num_vector[i])
}

# Traverse a vector using sapply
sapply(num_vector, print)
```

## Modifying Vectors

Vectors can be modified by assigning new values to specific elements.

```r
# Modify a vector
num_vector[1] <- 10
```

## Deleting Vector Elements

Vector elements can be deleted using the `NULL` assignment.

```r
# Delete a vector element
num_vector[1] <- NULL
```

## Sorting Vectors
------------------

Vectors can be sorted using the `sort()` function.

```r
# Sort a vector
sort(num_vector)
```

## Additional Vector Operations


Some additional vector operations include:

*   **Vector Addition**: Vectors can be added together using the `+` operator.
*   **Vector Multiplication**: Vectors can be multiplied together using the `*` operator.
*   **Vector Division**: Vectors can be divided using the `/` operator.
*   **Vector Exponentiation**: Vectors can be exponentiated using the `^` operator.

```r
# Vector addition
num_vector + c(1, 2, 3, 4, 5)

# Vector multiplication
num_vector * c(1, 2, 3, 4, 5)

# Vector division
num_vector / c(1, 2, 3, 4, 5)

# Vector exponentiation
num_vector ^ c(1, 2, 3, 4, 5)
```

## Vector Recycling


When performing operations on vectors of different lengths, R will recycle the shorter vector to match the length of the longer vector.

```r
# Vector recycling
c(1, 2, 3) + c(1, 2)
```

## Vector Indexing

Vectors can be indexed using square brackets `[]`.

```r
# Vector indexing
num_vector[1]
```

## Vector Naming


Vectors can be named using the `names()` function.

```r
# Vector naming
names(num_vector) <- c("a", "b", "c", "d", "e")
```
