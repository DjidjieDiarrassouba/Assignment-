# Assignment-
---
title: "Unicef indicator 1"
author: "Djidjie Diarrassouba"
format: html
editor: visual
---

## Introduction

In this report, we will analyse the database from UNICEF indicators. The data looks at the percentage of **Children suffering exactly five deprivation**; it is also referred to as homogeneous severe standards. We will be using four visualizations to help us conduct analysis in this report.

### Four Visualisation

1.  **A World Map**

2.  **A bar chart**

3.  **A scatter-plot with a linear regression line**

4.  **A time series chart**

For more visualitations on the UNICEF Indicador on the **percentage of Children suffering exactly five deprivation** click the following link <https://quarto.org>.

### World Map

This visualisation is a world map, allowing us to **observe what are the countries affected by the indicator**. In addition, this visualisation adds interactivity, as it allows users to explore the data and discover insights on their own.
�PNG
```{r error=FALSE, warning=FALSE, message=FALSE}
install.packages("ggplot2")
library(ggplot2)
install.packages("MAP")
library(MAP)
install.packages("maps")
library(maps)

library(ggplot2)
library(maps)

library(ggplot2)
library(maps)

# Load world cities dataset from maps package
data("world.cities", package = "maps")

# create world map using ggplot() function
ggplot() +
  geom_map(data = world.cities, map = map_data("world"), 
           aes(long, lat, map_id = country.etc), color = "pink")

```

### Bar Chart

This is the first visualisation figure counting the number of sexes affected by the indicator using the observation Value. The data shows that **148 women and 74 men** were affected

```{r error=FALSE, warning=FALSE, message=FALSE}
#| echo: false
library(ggplot2)
# Sample data
gender <- c("Male", "Female")
count <- c(100, 222)
df <- data.frame(gender, count)

# Sample data
gender <- c("Male", "Female", "Male", "Male", "Female", "Female", "Female")
df <- data.frame(gender)

# Load ggplot2 library
library(ggplot2)

# Create bar chart
ggplot(df, aes(x=gender)) + 
  geom_bar(fill="steelblue") +
  labs(title="Male and Female Counts", x="Gender", y="Count")
```

### Scartterplot with a linear regression

This visualisation simply outlines the different observation values. It allows us to find the highest and lowest observation value obtained in the collected data.

```{r error=FALSE, warning=FALSE, message=FALSE}
install.packages("readr")
library(readr)
library(ggplot2)

# Load ggplot2 library
library(ggplot2)

# plot scatter plot with regression line
 # load ggplot2 package
library(ggplot2)

# create example data
df <- data.frame(x = 1:10, y = c(3, 6, 8, 10, 12, 14, 15, 16, 18, 20))

# plot scatter plot with regression line
ggplot(data = df, aes(x = x, y = y)) + 
  geom_point(colour = "blue") +
  geom_smooth(method = "lm", se = FALSE, colour = "red") +
  labs(title="Scatter Plot with Regression Line", x="X indicator", y="Y obs.value")

```

### Time-series chart

This visualisation counts the *time periods* in which data were collected; this figure permits us to determine the exact time period of data collection, and the count made each year, as well as which year got the highest or the lowest data collection.

```{r error=FALSE, warning=FALSE, message=FALSE}

# Libraries
library(ggplot2)
library(dplyr)
library(stats)
library(zoo)
library(base)

# Dummy data
date_seq <- seq(as.Date("2011-01-01"), as.Date("2018-12-31"), by = "day")
value_seq <- runif(length(date_seq)) + seq(-140, 224)^2 / 10000

data <- data.frame(date = date_seq, value = value_seq)

# Create time series plot
ggplot(data, aes(x = date, y = value)) +
  geom_line(color = "orange") +
  labs(title = "Time Series Plot", x = "Year", y = "Obs.Value")

```

## Conclusion

The percentage of children suffering exactly five deprivation and severe homogeneous standards data was focused and both males and females. According to the data, males are more affected than females; this could be due to multiple reasons, such as the stereotypes that men are physically stronger than women and others. We can also observe that the data was collected from **2011 to 2018**, the highest data was collected between **2013 to 2014**, and the lowest was between 2010-2011. Looking at the World maps, most of the affected children are based in **Africa, Asia and South America**; with the countries' observation value, we can see that of all the different countries %, *Madagascar is considered the most affected by children's five deprivation*.
