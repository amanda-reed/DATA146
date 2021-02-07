## Gapminder Exercise

### Get a list of all the years in this data, without any duplicates. How many unique values are there, and what are they?

There are 12 distinct years in this data set:
1952, 1957, 1962, 1967, 1972, 1977, 1982, 1987, 1992, 1997, 2002, 2007

To get a list of all the years without duplicates, I subset the year variable from the data and used the unique() function to avoid duplicates. 

### What is the largest value for population (pop) in this data? When and where did this occur?

The largest value for population in this data is 1,318,683,096 which occurred in China in 2007.

To find this data, I found the index of the max value of population in the data set. Then I used .loc function to find all the information for this occurrence. 

```
max_pop = data_asia.loc[data_asia['pop'].idxmax()]
```

### Extract all the records for Europe. In 1952, which country had the smallest population, and what was the population in 2007?

In 1952, Iceland had the smallest population (147,962) in Europe. In 2007, Iceland's population was 301,931.

To extract all the records for Europe, I found all the indices where the continent was Europe, and used those values to subset the data. Then I subset all the data from 1952 
in the same way. From there, I was able to find the index of the minimum population and use .loc to find the complete observation at the index.
```
min_pop = eu_1952.loc[eu_1952['pop'].idxmin()]
```
Having found that the country was Iceland, I found the observation from the European data set in which Iceland was the country and the year was 2007. 
```
data_eu[(data_eu['country']=='Iceland')&(data_eu['year']==2007)]
```
