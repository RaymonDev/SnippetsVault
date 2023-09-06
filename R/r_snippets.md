# R

### Variable assignement and data types
```r
# Assign a value to a variable
x <- 5

# Numeric variable
y <- 3.14

# Character variable
name <- "John"

# Logical (boolean) variable
is_true <- TRUE
```

### Vectors
```r
# Create a numeric vector
numbers <- c(1, 2, 3, 4, 5)

# Create a character vector
fruits <- c("apple", "banana", "cherry")
```

### Data Frames
```r
# Create a data frame
data <- data.frame(
  Name = c("Alice", "Bob", "Charlie"),
  Age = c(25, 30, 22)
)
```

### Basic operations
```r
# Addition
result <- 2 + 3

# Subtraction
result <- 5 - 2

# Multiplication
result <- 4 * 6

# Division
result <- 10 / 2
```

### Conditional statements
```r
# If statement
if (x > 0) {
  print("x is positive")
} else {
  print("x is non-positive")
}
```

### Loops
```r
# For loop
for (i in 1:5) {
  print(i)
}

# While loop
count <- 1
while (count <= 5) {
  print(count)
  count <- count + 1
}
```

### Functions
```r
# Define a function
square <- function(x) {
  return(x^2)
}

# Call a function
result <- square(4)
```

### Data import/export
```r
# Read data from a CSV file
data <- read.csv("data.csv")

# Write data to a CSV file
write.csv(data, "output.csv")
```

### Plotting
```r
# Create a scatter plot
x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 1, 3, 5)
plot(x, y, type = "p", main = "Scatter Plot", xlab = "X-axis", ylab = "Y-axis")
```

### Packages (installing and loading)
```r
# Install a package from CRAN
install.packages("package_name")

# Load a package
library(package_name)
```

### Date and time
```r
current_datetime <- Sys.time()

formatted_date <- format(Sys.Date(), format = "%Y-%m-%d")
```

### String concatenation
```r
concatenated_str <- paste("Hello", "World", sep = " ")
```

### Substring
```r
sub_str <- substr("Hello World", start = 1, stop = 5)
```

### File operations
```r
file_list <- list.files(path = "/path/to/directory")
```

### Read text file
```r
text <- readLines("file.txt")
```

### Error handling
```r
tryCatch(expr, error = function(e) {
  # Code to handle the error
})
```

### 


