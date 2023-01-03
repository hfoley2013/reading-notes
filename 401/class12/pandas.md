# Pandas

## Readings

* [Pandas in 10](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)
* [Pandas - Getting Started](https://pandas.pydata.org/pandas-docs/stable/getting_started/intro_tutorials/index.html)
* [Real Python - Pandas Tutorials](https://realpython.com/learning-paths/pandas-data-science/)
* [VIDEO: What is Pandas](https://www.youtube.com/watch?v=dcqPhpY7tWk&t=391s)

## Reference

* [Master Pandas](https://towardsdatascience.com/be-a-more-efficient-data-scientist-today-master-pandas-with-this-guide-ea362d27386)

## Notes

### What is Pandas?

Pandas is a software library written for the Python programming language for data manipulation and analysis. It offers data structures for efficiently storing large datasets and tools for working with them. The library is designed to make it easy to work with tabular or structured data, such as data stored in a spreadsheet or a database table. Some of the main features of pandas include:

* The ability to load and work with large datasets that don't fit into memory.
* Tools for merging, grouping, and aggregating data.
* Functions for cleaning and preprocessing data.
* Tools for reading and writing data in different formats, such as CSV, Excel, and SQL databases.

### Common functions for data analysis

* `head()` and `tail()`
  * These functions allow you to view the first or last few rows of a DataFrame.
* `info()`
  * This function displays information about a DataFrame, such as the data types of each column and the number of non-null values.
* `describe()`
  * This function computes summary statistics of a DataFrame's numerical columns.
* `value_counts()`
  * This function counts the number of occurrences of each unique value in a categorical column.
* `groupby()`
  * This function allows you to group a DataFrame by one or more columns and apply a function to each group.
* `pivot_table()`
  * This function creates a pivot table, which is a summary of a dataset with different dimensions.
* `plot()`
  * This function generates plots of the data in a DataFrame.
* `hist()`
  * Generates a histogram of the data

### Time Series Analysis

* Plotting the time series
  * You can use the plot() function to generate a line plot of the time series data. This can help you visualize trends and patterns in the data.

  ```py
  import pandas as pd

  # Load the time series data into a pandas DataFrame
  df = pd.read_csv('time_series_data.csv')

  # Plot the time series data
  df.plot(x='date', y='value')
  ```

* Filtering the data
  * You can use boolean indexing to filter the time series data based on a certain condition
  * For example, you might want to select only the data for a certain year or month.

  ```py
  # Select only the data for 2018
  df_2018 = df[df['date'].dt.year == 2018]

  # Select only the data for January
  df_january = df[df['date'].dt.month == 1]
  ```

* Resampling the data
  * You can use the `resample()` function to resample the time series data to a different frequency.
  * For example, you might want to resample the data from daily to monthly data.

  ```py
  # Resample the data to monthly mean
  df_monthly = df.resample('M', on='date').mean()
  ```

* Rolling statistics
  * You can use the `rolling()` function to calculate rolling statistics, such as the rolling mean or rolling standard deviation.

  ```py
  # Calculate the rolling mean with a window size of 30
  df['rolling_mean'] = df['value'].rolling(30).mean()

  # Calculate the rolling standard deviation with a window size of 30
  df['rolling_std'] = df['value'].rolling(30).std()
  ```

### Compatible Libraries

* `tqdm`
  
  * When working with large datasets, pandas can take some time running `.map()`, `.apply()`, `.applymap()` operations.
  * `tqdm` is a very useful package that helps predict when theses operations will finish executing.

  ```py  
  from tqdm import tqdm_notebook
  tqdm_notebook().pandas()
  # Will show progress/loading bar in Jupyter Notebook
  ```
  