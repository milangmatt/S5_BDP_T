Applying Functions to Data Frames in R
=====================================

### Overview
In this section, we will explore how to apply functions to data frames in R. This is a common operation in data analysis and manipulation.

### Summary Statistics

Summary statistics are used to describe the main features of a dataset. In R, you can use functions like `mean()`, `median()`, `sd()`, and `var()` to calculate summary statistics.

```r
# Create a sample data frame
df <- data.frame(x = c(1, 2, 3, 4, 5), y = c(2, 4, 6, 8, 10))

# Calculate summary statistics
mean_x <- mean(df$x)
median_y <- median(df$y)
sd_x <- sd(df$x)
var_y <- var(df$y)

# Print the results
print(paste("Mean of x:", mean_x))
print(paste("Median of y:", median_y))
print(paste("Standard Deviation of x:", sd_x))
print(paste("Variance of y:", var_y))
```

Output:
```
[1] "Mean of x: 3"
[1] "Median of y: 6"
[1] "Standard Deviation of x: 1.4142135623731"
[1] "Variance of y: 20"
```

### Sorting

Sorting is used to arrange data in a specific order. In R, you can use the `order()` function to sort data.

```r
# Create a sample data frame
df <- data.frame(x = c(5, 2, 8, 1, 9))

# Sort the data frame in ascending order
df_sorted <- df[order(df$x), ]

# Print the sorted data frame
print(df_sorted)
```

Output:
```
  x
4 1
2 2
1 5
3 8
5 9
```

### Merging and Joining

Merging and joining are used to combine data from multiple data frames. In R, you can use the `merge()` function to merge data frames.

```r
# Create two sample data frames
df1 <- data.frame(id = c(1, 2, 3), name = c("John", "Mary", "David"))
df2 <- data.frame(id = c(1, 2, 3), age = c(25, 31, 42))

# Merge the two data frames
df_merged <- merge(df1, df2, by = "id")

# Print the merged data frame
print(df_merged)
```

Output:
```
  id name age
1  1 John  25
2  2 Mary  31
3  3 David  42
```

### Aggregation

Aggregation is used to combine data from multiple rows into a single row. In R, you can use the `aggregate()` function to aggregate data.

```r
# Create a sample data frame
df <- data.frame(group = c("A", "A", "B", "B"), value = c(10, 20, 30, 40))

# Aggregate the data frame by group
df_aggregated <- aggregate(df$value, by = list(df$group), sum)

# Print the aggregated data frame
print(df_aggregated)
```

Output:
```
  Group.1 x
1       A 30
2       B 70
```

### Reshaping

Reshaping is used to change the structure of a data frame. In R, you can use the `reshape()` function to reshape data.

```r
# Create a sample data frame
df <- data.frame(id = c(1, 1, 2, 2), time = c("pre", "post", "pre", "post"), value = c(10, 20, 30, 40))

# Reshape the data frame
df_reshaped <- reshape(df, direction = "wide", idvar = "id", timevar = "time")

# Print the reshaped data frame
print(df_reshaped)
```

Output:
```
  id value.pre value.post
1  1       10        20
2  2       30        40
```

### Filtering

Filtering is used to select specific rows from a data frame. In R, you can use the `subset()` function to filter data.

```r
# Create a sample data frame
df <- data.frame(id = c(1, 2, 3, 4, 5), value = c(10, 20, 30, 40, 50))

# Filter the data frame
df_filtered <- subset(df, value > 30)

# Print the filtered data frame
print(df_filtered)
```

Output:
```
  id value
4  4    40
5  5    50
```

### Grouping and Summarizing

Grouping and summarizing are used to group data by one or more variables and calculate summary statistics. In R, you can use the `group_by()` and `summarise()` functions from the dplyr package to group and summarize data.

```r
# Load the dplyr package
library(dplyr)

# Create a sample data frame
df <- data.frame(group = c("A", "A", "B", "B"), value = c(10, 20, 30, 40))

# Group and summarize the data frame
df_summarized <- df %>% group_by(group) %>% summarise(mean_value = mean(value))

# Print the summarized data frame
print(df_summarized)
```

Output:
```
  group mean_value
1     A       15.0
2     B       35.0
```

### Data Cleaning and Transformations

Data cleaning and transformations are used to prepare data for analysis. In R, you can use various functions like `na.omit()`, `na.replace()`, and `transform()` to clean and transform data.

```r
# Create a sample data frame
df <- data.frame(id = c(1, 2, 3, 4, 5), value = c(10, NA, 30, 40, 50))

# Remove rows with missing values
df_cleaned <- na.omit(df)

# Print the cleaned data frame
print(df_cleaned)
```

Output:
```
  id value
1  1    10
3  3    30
4  4    40
5  5    50
```