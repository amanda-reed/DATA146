## Project 1

#### Describe what is a package? Also, describe what is a library? What are the two steps you need to execute in order to install a package and then make 
that library of functions accessible to your workspace and current python work session?

A package is a set of related classes and functions. A package will also contain a constructor function. A library is a collection of packages that must be imported at the 
beginning of each coding session to be utilized. To install a package, you must import the library to which it is contained and then import the specific package you need. 
For example, you can install the pandas library as so:
```
import pandas as pd
```
By importing pandas as "pd", you can reference pd in your code as you call functions within the library. Rather than typing the entire library name when calling a function,
you can simply use "pd", saving you time. You can also install a specific function from a package if you know you will only use one function. For example:
``` 
from datetime import datetime
```

#### Describe what is a data frame? Identify a library of functions that is particularly useful for working with data frames. In order to read a file in its remote location within the file system of your operating system, which command would you use? Provide an example of how to read a file and import it into your work session in order to create a new data frame. Also, describe why specifying an argument within a read_() function can be significant. Does data that is saved as a file in a different type of format require a particular argument in order for a data frame to be successfully imported? Also, provide an example that describes a data frame you created. How do you determine how many rows and columns are in a data frame? Is there an alternate terminology for describing rows and columns?

A data frame is an array or table of information in which the columns represent variables and the rows represent observations. The Pandas library is particularly useful for working with data frames. In order to read a file in its remote location, you can use read_csv() within 
the pandas library. 
```
df = pd.read_csv(foldername\name_of_file)
```
Data that is saved in a different format may use a different read function. For example, read_html() is used to read an html file. Specifying the type of file to be read 
indicates the reader function which converts the data into something that can be read and processed in a python file. However, files similar to csv, tsv for example, can
be specified in the argument of the function by adding the seperation as "\t". 
```
data = pd.read_csv(path_to_data, sep = '\t')
```
To count the rows and columns in a data frame, you can use .shape command, which will give the number of rows, then columns. Rows and columns may also be known as observations and variables.

#### Import the gapminder.tsv data set and create a new data frame. Interrogate and describe the year variable within the data frame you created. Does this variable exhibit regular intervals? If you were to add new outcomes to the raw data in order to update and make it more current, which years would you add to each subset of observations? Stretch goal: can you identify how many new outcomes in total you would be adding to your data frame?

The year variable has 12 unique instances: 1952, 1957, 1962, 1967, 1972, 1977, 1982, 1987, 1992, 1997, 2002, 2007. This variable exhibits a regular interval of 5 years. To make the data more current, you would add 2012, and 2017. Since there are 142 unique countries in the data frame, by making the data more current you would add 284 new outcomes. 

#### Using the data frame you created by importing the gapminder.tsv data set, determine which country at what point in time had the lowest life expectancy. Conduct a cursory level investigation as to why this was the case and provide a brief explanation in support of your explanation.

The country with the lowest life expectancy in the data frame was Rwanda in 1992, which had a life expectancy of 23.599. To find this data, I found the index of the minimum life expectancy in the data and then used that index to find all information about that particular observation. This is due to an increasingly violent civil war in Rwanda which escalated into a genocide in the 1990s. 

#### Using the data frame you created by importing the gapminder.tsv data set, multiply the variable pop by the variable gdpPercap and assign the results to a newly created variable. Then subset and order from highest to lowest the results for Germany, France, Italy and Spain in 2007. Create a table that illustrates your results (you are welcome to either create a table in markdown or plot/save in PyCharm and upload the image). Stretch goal: which of the four European countries exhibited the most significant increase in total gross domestic product during the previous 5-year period (to 2007)?

![](p1_df.png)

Germany had the most significant increase in total gross domestic product during the previous 5-year period. 

#### You have been introduced to four logical operators thus far: &, ==, | and ^. Describe each one including its purpose and function. Provide an example of how each might be used in the context of programming.

The AND operator, &, is used when both statements must be true for the overall conditional statement to be true. For example, if you are looking for observations within a data set which come from 2007 and Italy, you would use the & operator. 

The equals operator, ==, is used to compare two values, variables, or other pieces of data. For example, if you want to test if a user's input is equal to a certain value in order to perform a command, you would use this operator.

The OR operator, |, is used when at least one of the statements in a conditional statement must be true for the statement to be true. If both are true, the statement still holds. For example, if you are trying to find which observations in a data set are from Italy or have a population over 1 million, you could subset the data by finding the observations where the country equals Italy OR the population is greater than 1 million. 

The XOR operator, ^, is used when only one of the statements in a conditional statement must be true for the statement to be true. If both are true, the statement is false. In other words, either statement 1 is true or statement 2 is true. For example, if you are trying perform a command on certain observations if they have either a population below 10 million or a life expectancy below 50 you would use XOR.

#### Describe the difference between .loc and .iloc. Provide an example of how to extract a series of consecutive observations from a data frame. Stretch goal: provide an example of how to extract all observations from a series of consecutive columns.

.loc locates data based on its row label given in the data frame. .iloc locates data based on its iteger row label, which starts at 0. To extract a series of consecutive observations from a data frame, you can define the series of observations in the command. For example:
```
data.iloc[1:3]
```
returns the observations in rows 1 and 2. If .loc was used, the observations may not be consecutive. Likewise, the extract all observations from a series of consecutive columns, set the row range as : and the columns as the series of column indices. For example, the following code will return all observations for columns 1 and 2, including their row labels.
```
data.iloc[:,1:3]
```

#### Describe how an api works. Provide an example of how to construct a request to a remote server in order to pull data, write it to a local file and then import it to your current work session.

An API in an Application Programming Interface which serves as a messenger between users and the database. Users can use an API to retrieve information while the private database from which the information comes stays secure. An API receives a request from a user, then sends this request to the database, then returns the requested information back to the user. To construct a request to a remote server, use the url address ending with the name of the data file, for example data.csv, in the parameter of a get() function to pull data.  
```
df = requests.get(url_to_data\data.csv)
```

#### Describe the apply() function from the pandas library. What is its purpose? Using apply() to various class objects is an alternative (potentially preferable approach) to writing what other type of command? Why do you think apply() could be a preferred approach?

The apply() function from the pandas library is used to apply a certain function to all rows or columns in a data frame. Arguments within the command determine what function, either from previous code, another library, or a lamda function, as well as where to apply the function. This function is an alternative to applying a for loop to a series of data. Using apply() is more concise and may be faster in some cases. 

#### Also describe an alternative approach to filtering the number of columns in a data frame. Instead of using .iloc, what other approach might be used to select, filter and assign a subset number of variables to a new data frame?

Another approach to filtering the number of columns in a data frame is by selecting which columns you need using brackets and the string labels for each column. The example below assigns outcomes from two columns in the data set to a new data frame. If only one column is subset, only one set of brackets is used. If more than one columns are needed, two sets of brackets are necessary.
```
new_df = df[['year', 'country']]
```

#### References

Gazarov, Petr. “What Is an API? In English, Please.” FreeCodeCamp, 26 Mar. 2020, www.freecodecamp.org/news/what-is-an-api-in-english-please-b880a3214a82/. 

“IO Tools (Text, CSV, HDF5, ...).” IO Tools (Text, CSV, HDF5, ...) - Pandas 1.2.2 Documentation, pandas.pydata.org/pandas-docs/stable/user_guide/io.html. 

“Pandas.DataFrame.apply.” Pandas.DataFrame.apply - Pandas 1.2.2 Documentation, pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.apply.html. 
