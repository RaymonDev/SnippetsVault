## Data Manipulation

### Create a vector
```r
my_vector <- c(1, 2, 3, 4, 5)
```

### Create a data frame
```r
df <- data.frame(Name = c("Alice", "Bob", "Charlie"), Age = c(25, 30, 22))
```

### Subset data
```r
subset_df <- df[df$Age > 25, ]
```

### Merge data frames
```r
merged_df <- merge(df1, df2, by = "ID")
```

### Sort data
```r
sorted_df <- df[order(df$Column), ]
```

### Data sampling
```r
sample_data <- sample(my_vector, size = 5, replace = TRUE)
```

### Data reshaping
```r
transposed_matrix <- t(my_matrix)
```

