The best place to learn Pandas is the [user guide](https://pandas.pydata.org/docs/user_guide/index.html) itself. We will try to add some extra examples as needed for better understanding following the official user guide.

### Pandas

Pandas is a powerful data manipulation and analysis library for Python. It provides data structures and functions needed to work with structured data seamlessly. The two primary data structures in Pandas are:

**Series:**  A one-dimensional array-like object that can hold any data type, similar to a column in a spreadsheet.
**DataFrame:** A two-dimensional, size-mutable, and potentially heterogeneous tabular data structure with labeled axes (rows and columns), akin to a table or a spreadsheet.

Pandas makes it easy to handle data in a variety of formats, such as CSV, Excel, SQL databases, and more. It offers a range of functionalities including data cleaning, transformation, aggregation, and visualization.

### Series

A `Series` in Pandas is a one-dimensional labeled array capable of holding any data type, such as integers, floats, strings, or even Python objects. It can be thought of as a single column of data.

Here’s a quick overview of key features and how to work with a `Series`:

### Creation

You can create a `Series` using various methods:

1. **From a List or Array**:
   ```python
   import pandas as pd
   
   data = [10, 20, 30, 40]
   series = pd.Series(data)
   ```

2. **From a Dictionary**:
   ```python
   data = {'a': 1, 'b': 2, 'c': 3}
   series = pd.Series(data)
   ```

3. **With an Index**:
   ```python
   data = [10, 20, 30]
   index = ['a', 'b', 'c']
   series = pd.Series(data, index=index)
   ```

### Key Attributes

- **`.index`**: Returns the index (labels) of the Series.
- **`.values`**: Returns the values of the Series as a NumPy array.
- **`.dtype`**: Returns the data type of the Series elements.
- **`.name`**: Gets or sets the name of the Series.

### Basic Operations

- **Accessing Elements**:
  ```python
  series[0]  # Access the first element
  series['a']  # Access the element with label 'a'
  ```

- **Slicing**:
  ```python
  series[1:3]  # Slice the Series
  ```

- **Mathematical Operations**:
  ```python
  series + 10  # Add 10 to each element
  ```

- **Methods**:
  - `.mean()`: Compute the mean of the Series.
  - `.sum()`: Compute the sum of the Series.
  - `.count()`: Count the number of non-NA/null entries.

### Example

```python
import pandas as pd

# Create a Series with data and custom index
data = [10, 20, 30]
index = ['a', 'b', 'c']
series = pd.Series(data, index=index)

print(series)
```

Output:
```
a    10
b    20
c    30
dtype: int64
```
In Pandas, vectorized operations and label alignment are key features that enhance the efficiency and flexibility of data manipulation. Here's how they work with the `Series` data structure:

### Vectorized Operations

Vectorized operations allow you to perform arithmetic operations on entire `Series` or DataFrame objects at once, rather than looping through elements. This is both more efficient and more readable.

**Examples:**

1. **Arithmetic Operations**:
   ```python
   import pandas as pd

   # Create two Series
   series1 = pd.Series([10, 20, 30])
   series2 = pd.Series([1, 2, 3])

   # Add the Series
   result = series1 + series2
   print(result)
   ```

   Output:
   ```
   0    11
   1    22
   2    33
   dtype: int64
   ```

2. **Statistical Operations**:
   ```python
   # Compute the mean
   mean_value = series1.mean()
   print(mean_value)
   ```

   Output:
   ```
   20.0
   ```

3. **Applying Functions**:
   ```python
   # Apply a function to each element
   squared = series1.apply(lambda x: x ** 2)
   print(squared)
   ```

   Output:
   ```
   0    100
   1    400
   2    900
   dtype: int64
   ```

### Label Alignment

Label alignment ensures that operations between `Series` objects align data based on their labels (index). This means that when performing operations on `Series` with different indexes, Pandas will align the data according to the index labels, automatically handling missing data with `NaN` values.

**Examples:**

1. **Aligning Series with Different Indexes**:
   ```python
   # Create two Series with different indexes
   series1 = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
   series2 = pd.Series([1, 2], index=['b', 'd'])

   # Add the Series
   result = series1 + series2
   print(result)
   ```

   Output:
   ```
   a    NaN
   b    22.0
   c    NaN
   d    NaN
   dtype: float64
   ```

   In this example, only the label 'b' exists in both Series, so only that element is calculated (20 + 2). Other labels result in `NaN` because there is no corresponding data in one of the Series.

2. **Reindexing**:
   You can also manually align Series by reindexing:
   ```python
   # Reindex to match
   series1 = series1.reindex(['a', 'b', 'c', 'd'])
   series2 = series2.reindex(['a', 'b', 'c', 'd'])
   
   result = series1 + series2
   print(result)
   ```

   Output:
   ```
   a     NaN
   b    22.0
   c     NaN
   d     NaN
   dtype: float64
   ```


- **Vectorized Operations**: Efficiently perform operations on entire `Series` objects at once, without explicit loops.
- **Label Alignment**: Automatically aligns data based on index labels during operations, making it easier to work with data that may have mismatched indexes.

### Name attribute in series

The `name` attribute in a Pandas `Series` is used to get or set the name of the `Series` object. Naming a `Series` can be helpful for identification, especially when dealing with multiple `Series` or when using them in a `DataFrame`.

#### Getting and Setting the Name

- **Get the Name**:
  ```python
  import pandas as pd

  # Create a Series
  series = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
  
  # Get the name of the Series
  print(series.name)  # Output: None
  ```

  By default, the `name` attribute is `None` if not explicitly set.

- **Set the Name**:
  ```python
  # Set the name of the Series
  series.name = 'my_series'
  print(series.name)  # Output: my_series
  ```

#### Using the Name in Context

Naming a `Series` is useful when combining multiple `Series` or when creating a `DataFrame`. The name of the `Series` becomes the column label in a `DataFrame` when it is used as one of the columns.

**Example:**

```python
import pandas as pd

# Create Series with names
series1 = pd.Series([10, 20, 30], index=['a', 'b', 'c'], name='first')
series2 = pd.Series([1, 2, 3], index=['a', 'b', 'c'], name='second')

# Combine into a DataFrame
df = pd.DataFrame({'first': series1, 'second': series2})
print(df)
```

Output:
```
   first  second
a     10       1
b     20       2
c     30       3
```

In this example, the names of the `Series` (`'first'` and `'second'`) are used as column names in the resulting `DataFrame`.

A `DataFrame` in Pandas is a two-dimensional, size-mutable, and potentially heterogeneous tabular data structure. It is one of the most commonly used data structures in Pandas and is similar to a spreadsheet or SQL table, where data is organized in rows and columns.

### Key Features of DataFrame

- **Two-Dimensional**: Data is organized in rows and columns.
- **Labeled Axes**: Rows and columns are labeled, which allows for easy access to data.
- **Heterogeneous Data**: Different columns can hold different data types (e.g., integers, floats, strings).
- **Size-Mutable**: You can insert or delete rows and columns.

### Creating a DataFrame

There are multiple ways to create a `DataFrame` in Pandas:

1. **From a Dictionary of Lists**:
   ```python
   import pandas as pd

   data = {
       'Name': ['Alice', 'Bob', 'Charlie'],
       'Age': [25, 30, 35],
       'City': ['New York', 'Los Angeles', 'Chicago']
   }
   df = pd.DataFrame(data)
   print(df)
   ```

   Output:
   ```
        Name  Age         City
   0    Alice   25     New York
   1      Bob   30  Los Angeles
   2  Charlie   35     Chicago
   ```

2. **From a List of Dictionaries**:
   ```python
   data = [
       {'Name': 'Alice', 'Age': 25, 'City': 'New York'},
       {'Name': 'Bob', 'Age': 30, 'City': 'Los Angeles'},
       {'Name': 'Charlie', 'Age': 35, 'City': 'Chicago'}
   ]
   df = pd.DataFrame(data)
   print(df)
   ```

3. **From a NumPy Array**:
   ```python
   import numpy as np

   data = np.array([[25, 'New York'], [30, 'Los Angeles'], [35, 'Chicago']])
   df = pd.DataFrame(data, columns=['Age', 'City'])
   print(df)
   ```

4. **From another DataFrame**:
   ```python
   # Create a DataFrame by selecting specific columns from another DataFrame
   df2 = df[['Name', 'City']]
   print(df2)
   ```

### Accessing Data in a DataFrame

- **Selecting Columns**:
  ```python
  print(df['Name'])  # Returns a Series
  print(df[['Name', 'Age']])  # Returns a DataFrame with selected columns
  ```

- **Selecting Rows by Index**:
  ```python
  print(df.loc[0])  # Access by label-based index (returns a Series)
  print(df.iloc[0])  # Access by integer-based index (returns a Series)
  ```

- **Slicing**:
  ```python
  print(df[1:3])  # Selects rows 1 to 2 (exclusive of 3)
  ```

- **Boolean Indexing**:
  ```python
  print(df[df['Age'] > 30])  # Selects rows where the 'Age' column is greater than 30
  ```

### Common Operations on DataFrames

- **Adding a New Column**:
  ```python
  df['Country'] = ['USA', 'USA', 'USA']
  print(df)
  ```

- **Dropping a Column or Row**:
  ```python
  df = df.drop('Country', axis=1)  # Drop a column
  df = df.drop(0, axis=0)  # Drop a row by index
  ```

- **Summary Statistics**:
  ```python
  print(df.describe())  # Summary statistics for numerical columns
  ```

- **Sorting**:
  ```python
  df = df.sort_values(by='Age')  # Sort by 'Age' column
  print(df)
  ```

### Example

```python
import pandas as pd

# Create a DataFrame from a dictionary of lists
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
}
df = pd.DataFrame(data)

# Display the DataFrame
print(df)

# Add a new column
df['Country'] = 'USA'

# Select rows where Age is greater than 30
print(df[df['Age'] > 30])
```

Output:
```
      Name  Age         City
0    Alice   25     New York
1      Bob   30  Los Angeles
2  Charlie   35     Chicago

      Name  Age     City Country
2  Charlie   35  Chicago     USA
```


A `DataFrame` is a versatile and powerful data structure in Pandas that is essential for data analysis and manipulation. It allows you to store and work with tabular data efficiently, making it easier to handle large datasets and perform complex operations with ease.


### Columns selection deletion and addition
### Assigning new columns in method chains
### Indexing / selection in DataFrame
### Data alignment and arithmetic
### Transposing
### DataFrame interoperability with NumPy functions
### Console display
### Head and tail
### Attributes and underlying data
### Accelerated operations
### Flexible binary operations
  #### Matching / broadcasting behavior
  #### Missing data / operations with fill values
  #### Flexible comparisons
  #### Boolean reductions
  #### Comparing if objects are equivalent
  #### Comparing array-like objects
  #### Combining overlapping data sets
  #### General DataFrame combine
  
### Descriptive statistics
#### Summarizing data: describe
#### Index of min/max values
#### Value counts (histogramming) / mode
#### Discretization and quantiling
### Function application
#### Tablewise function application
#### Row or column-wise function application
#### Aggregation API
##### Aggregating with multiple functions
##### Aggregating with a dict
##### Custom describe
#### Transform API
##### Transform with multiple functions
##### Transforming with a dict
#### Applying elementwise functions
### Reindexing and altering labels
##### Reindexing to align with another object
##### Aligning objects with each other with align
##### Filling while reindexing
##### Limits on filling while reindexing
##### Dropping labels from an axis
##### Renaming / mapping labels
### Iteration  
#### items
#### iterrows
#### itertuples
### .dt accessor
### Vectorized string methods
### Sorting
#### By index
#### By values
#### By indexes and values
#### searchsorted
#### smallest / largest values
#### Sorting by a MultiIndex column
### Copying
### dtypes
#### defaults
#### upcasting
#### astype
#### object conversion
### Selecting columns based on dtype


































