Creating Data Frames in R
==========================

Overview
--------

Data frames are a fundamental data structure in R, used to store and manipulate tabular data. They are similar to tables in a relational database or Excel spreadsheets. In this guide, we will cover the basics of creating data frames in R.

Creating a Data Frame
--------------------

A data frame can be created using the `data.frame()` function. The basic syntax is as follows:

```r
data.frame(column1 = c(value1, value2, ...), column2 = c(value1, value2, ...))
```

Example
-------

```r
# Create a data frame with two columns: 'Name' and 'Age'
df <- data.frame(
  Name = c("John", "Mary", "David"),
  Age = c(25, 31, 42)
)

# Print the data frame
print(df)
```

Output
------

```
   Name Age
1  John  25
2  Mary  31
3 David  42
```

Adding Rows and Columns
----------------------

You can add rows to a data frame using the `rbind()` function, and columns using the `cbind()` function.

```r
# Add a new row to the data frame
df <- rbind(df, data.frame(Name = "Emily", Age = 28))

# Add a new column to the data frame
df$Country <- c("USA", "UK", "Australia", "Canada")

# Print the updated data frame
print(df)
```

Output
------

```
   Name Age  Country
1  John  25      USA
2  Mary  31       UK
3 David  42 Australia
4 Emily  28    Canada
```

Conclusion
----------

In this guide, we have covered the basics of creating data frames in R. We have shown how to create a data frame, add rows and columns, and manipulate the data. With practice, you will become proficient in working with data frames and be able to perform more complex data analysis tasks.