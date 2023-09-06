## Functions

### Create a function
```r
my_function <- function(x, y) {
  result <- x + y
  return(result)
}
```

### Apply a function to a column
```r
df$NewColumn <- sapply(df$OldColumn, my_function)
```

