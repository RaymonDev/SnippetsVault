## Data cleaning

### Remove NA values
```r
cleaned_df <- na.omit(df)
```

### Replace NA values
```r
df$Column[is.na(df$Column)] <- replacement_value
```

### Remove duplicates
```r
cleaned_df <- unique(df)
```

### Rename columns
```r
colnames(df)[colnames(df) == "Old_Name"] <- "New_Name"
```

### Rename rows
```r
rownames(df)[rownames(df) == "Old_Name"] <- "New_Name"
```

### Remove columns
```r
cleaned_df <- df[, -c(1, 2, 3)]
```

### Remove rows
```r
cleaned_df <- df[-c(1, 2, 3), ]
```