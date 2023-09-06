## Data Visualization

### Create a scatter plot
```r
plot(df$X, df$Y, main = "Scatter Plot", xlab = "X-axis", ylab = "Y-axis")
```

### Histogram
```r
hist(df$X, main = "Histogram", xlab = "X-axis", ylab = "Frequency")
```

### Box plot
```r
boxplot(df$X, main = "Box Plot", ylab = "X-axis")
```

### Bar Chart
```r
barplot(df$Count, names.arg = df$Category, main = "Bar Chart", xlab = "Category", ylab = "Count")
```

### Pie Chart
```r
pie(df$Count, labels = df$Category, main = "Pie Chart")
```

### Line Chart
```r
plot(df$X, df$Y, type = "l", main = "Line Chart", xlab = "X-axis", ylab = "Y-axis")
```