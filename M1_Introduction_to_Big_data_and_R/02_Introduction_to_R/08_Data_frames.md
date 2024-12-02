Data Frames in R
================

Overview
--------

Data frames are a fundamental data structure in R, used to store and manipulate tabular data. They are similar to tables in relational databases or data frames in Python's pandas library.

Creating Data Frames
-------------------

Data frames can be created using the `data.frame()` function, which takes a list of vectors as arguments. Each vector represents a column in the data frame.

```r
# Create a data frame
df <- data.frame(
  Name = c("John", "Mary", "David"),
  Age = c(25, 31, 42),
  Country = c("USA", "Canada", "UK")
)
```

Data Frame Structure
--------------------

A data frame consists of rows and columns. Each row represents a single observation, and each column represents a variable.

```r
# Print the data frame
print(df)
```

Output:

```
   Name Age Country
1  John  25     USA
2  Mary  31  Canada
3 David  42      UK
```

Data Frame Operations
---------------------

Data frames support various operations, including filtering, sorting, and merging.

```r
# Filter rows where Age is greater than 30
df_filtered <- df[df$Age > 30, ]

# Sort the data frame by Age in descending order
df_sorted <- df[order(df$Age, decreasing = TRUE), ]

# Merge two data frames
df_merged <- merge(df, df2, by = "Name")
```

Data Frame Functions
--------------------

R provides various functions for working with data frames, including:

* `head()`: Displays the first few rows of a data frame.
* `tail()`: Displays the last few rows of a data frame.
* `str()`: Displays the structure of a data frame.
* `summary()`: Displays a summary of a data frame.

```r
# Display the first few rows of a data frame
head(df)

# Display the last few rows of a data frame
tail(df)

# Display the structure of a data frame
str(df)

# Display a summary of a data frame
summary(df)
```

Conclusion
----------

Data frames are a powerful data structure in R, providing a flexible and efficient way to store and manipulate tabular data. By understanding how to create, manipulate, and analyze data frames, you can unlock the full potential of R for data analysis and visualization.