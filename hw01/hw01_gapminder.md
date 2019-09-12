Gapminder Exploration
================
Sihaoyu Gao
Sep 11, 2019

Introduction
------------

This document explores the gapminder dataset. First of all, load the gapminder data set from `gapminder` library. Before doing any analysis, we need to understand the dataset. The data set is the excerpt of the Gapminder data on life expectancy, GDP per capita, and population by country. The main data frame gapminder has 1704 rows and 6 variables:

``` r
names(gapminder)
```

    ## [1] "country"   "continent" "year"      "lifeExp"   "pop"       "gdpPercap"

Country is a factor with 142 levels, continent is a factor with 5 levels, year ranges from 1952 to 2007 in increments of 5 years, lifeExp is life expectancy at birth (in years), pop is population, and gdpPercap is GDP per capita in US dollars. All the above information are provided in R.

``` r
?gapminder
```

Analysis
--------

Figure 1 shows the trajectories of GDP per capita over time for each country. There is one country has extremely high GDP per capita before 1980. By extracting the lines with remarkable high GDP from the dataset, it shows that the outstanding country is Kuwait in Asia.

![](hw01_gapminder_files/figure-markdown_github/figs-1.png)

Except show all 142 countries' change in GDP per capita over time, we can also plot the GDP per capita change in terms of different continents. Figure 2 shows the trajectories of GDP per capita over time for each continent. At each time point, GDP per capita for each continent is calculated by the mean of all the countries in the continent at that time point. From Figure 2, we can see that Europe and Oceania have the fastest increase rate of GDP per capita, while Africa has the lowest increase rate of GDP per capita over years.

![](hw01_gapminder_files/figure-markdown_github/fig_2-1.png)

Finally, instead of showing the GDP per capita change over time, it is interesting to explore the relationship between GDP per capita and life expectancy. From Figure 3, it is obvious that life expectancy increases as GDP per capita increase.

![](hw01_gapminder_files/figure-markdown_github/scatter-1.png)

The correlation also indicates the same result. 0.8 is quite close to 1, and it illustrates that life expectancy and GDP per capita (in log) have a positive correlation.

``` r
cor(log(gdpPercap),lifeExp)
```

    ## [1] 0.8076179
