## Geospatial Analysis (with 'sf' package)

### Read shapefile
```r
library(sf)
my_sf <- st_read("shapefile.shp")
```

### Plot spatial data
```r
library(ggplot2)
ggplot() + geom_sf(data = my_sf)
```

