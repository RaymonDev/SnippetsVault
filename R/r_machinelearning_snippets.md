## Machine learning

### Random forest classifier
```r
library(randomForest)
rf_model <- randomForest(Class ~ ., data = df)
```

### K-Means clustering
```r
kmeans_model <- kmeans(df, centers = 3)
``