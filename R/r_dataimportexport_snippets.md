## Data Import/Export

### Read CSV file
```r
my_data <- read.csv("my_data.csv")
```

### Write CSV file
```r
write.csv(my_data, "my_data.csv")
```

### Read Excel file
```r
library(readxl)
my_data <- read_excel("my_data.xlsx")
```

### Write Excel file
```r
library(xlsx)
write.xlsx(my_data, "my_data.xlsx")
```

### Read JSON file
```r
library(jsonlite)
my_data <- fromJSON("my_data.json")
```

### Write JSON file
```r
library(jsonlite)
toJSON(my_data, "my_data.json")
```