## Statistics

### Chi-square test
```r
chisq_test <- chisq.test(table(df$Category1, df$Category2))
```

### T-test
```r
t_test <- t.test(df$Group1, df$Group2)
```

