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

#### Describe what is a data frame? Identify a library of functions that is particularly useful for working with data frames. In order to read a file in its remote
location within the file system of your operating system, which command would you use? Provide an example of how to read a file and import it into your work session 
in order to create a new data frame. Also, describe why specifying an argument within a read_() function can be significant. Does data that is saved as a file in a different 
type of format require a particular argument in order for a data frame to be successfully imported? Also, provide an example that describes a data frame you created.
How do you determine how many rows and columns are in a data frame? Is there an alternate terminology for describing rows and columns?

A data frame is a ____. The Pandas library is particularly useful for working with data frames. In order to read a file in its remote location, you can use read_csv() within 
the pandas library. 
```
df = pd.read_csv(foldername\name_of_file)
```
Data that is saved in a different format may use a different read function. For example, read_html() is used to read an html file. Specifying the type of file to be read 
indicates the reader function which converts the data into something that can be read and processed in a python file. However, files similar to csv, tsv for example, can
be specified in the argument of the function by adding the seperation as "\t". (https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html)
```
data = pd.read_csv(path_to_data, sep = '\t')
```
To count the rows and columns in a data frame, you can use .shape command, which will give the number of rows, then columns. Rows and columns may also be known as observations
and variables. 


