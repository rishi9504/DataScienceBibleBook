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
In a Pandas `DataFrame`, you can easily select, delete, and add columns. Below are detailed explanations and examples of how to perform each of these operations.

### 1. Column Selection

You can select columns from a `DataFrame` using different methods:

#### a) Selecting a Single Column

- **By Column Name**: This returns a `Series` representing the selected column.
  ```python
  import pandas as pd

  data = {
      'Name': ['Alice', 'Bob', 'Charlie'],
      'Age': [25, 30, 35],
      'City': ['New York', 'Los Angeles', 'Chicago']
  }
  df = pd.DataFrame(data)

  # Select the 'Name' column
  name_column = df['Name']
  print(name_column)
  ```

  Output:
  ```
  0     Alice
  1       Bob
  2   Charlie
  Name: Name, dtype: object
  ```

#### b) Selecting Multiple Columns

- **By Column Names**: This returns a `DataFrame` with the selected columns.
  ```python
  # Select 'Name' and 'City' columns
  selected_columns = df[['Name', 'City']]
  print(selected_columns)
  ```

  Output:
  ```
        Name         City
  0    Alice     New York
  1      Bob  Los Angeles
  2  Charlie     Chicago
  ```

#### c) Selecting Columns by Index (using `.iloc`)

- **Using `.iloc`**: You can also use `.iloc` for positional indexing.
  ```python
  # Select the first two columns
  selected_columns = df.iloc[:, [0, 1]]
  print(selected_columns)
  ```

### 2. Column Deletion

You can delete columns from a `DataFrame` using the `drop` method or the `del` keyword.

#### a) Deleting Columns Using `drop`

- **By Column Name**:
  ```python
  # Drop the 'Age' column (in-place deletion)
  df.drop('Age', axis=1, inplace=True)
  print(df)
  ```

  Output:
  ```
        Name         City
  0    Alice     New York
  1      Bob  Los Angeles
  2  Charlie     Chicago
  ```

- **Drop Multiple Columns**:
  ```python
  # Drop both 'Name' and 'City' columns
  df = df.drop(['Name', 'City'], axis=1)
  print(df)
  ```

#### b) Deleting Columns Using `del`

- **Using `del`**: This is an alternative way to delete a column.
  ```python
  # Restore the original DataFrame
  df = pd.DataFrame(data)

  # Delete the 'City' column
  del df['City']
  print(df)
  ```

  Output:
  ```
        Name  Age
  0    Alice   25
  1      Bob   30
  2  Charlie   35
  ```

### 3. Adding Columns

You can add new columns to a `DataFrame` in several ways.

#### a) Adding a New Column with Scalar Values

- **Assigning a Scalar Value**:
  ```python
  # Add a new column 'Country' with a single value for all rows
  df['Country'] = 'USA'
  print(df)
  ```

  Output:
  ```
        Name  Age Country
  0    Alice   25     USA
  1      Bob   30     USA
  2  Charlie   35     USA
  ```

#### b) Adding a New Column with a List or Series

- **Assigning a List or `Series`**:
  ```python
  # Add a new column 'Score' with values from a list
  df['Score'] = [85, 90, 95]
  print(df)
  ```

  Output:
  ```
        Name  Age Country  Score
  0    Alice   25     USA     85
  1      Bob   30     USA     90
  2  Charlie   35     USA     95
  ```

#### c) Adding a Column Based on Existing Columns

- **Using Existing Columns**:
  ```python
  # Add a new column 'Age in 10 Years' based on the 'Age' column
  df['Age in 10 Years'] = df['Age'] + 10
  print(df)
  ```

  Output:
  ```
        Name  Age Country  Score  Age in 10 Years
  0    Alice   25     USA     85               35
  1      Bob   30     USA     90               40
  2  Charlie   35     USA     95               45
  ```


- **Column Selection**: Use bracket notation `df['col']` for a single column or `df[['col1', 'col2']]` for multiple columns.
- **Column Deletion**: Use `df.drop()` or `del df['col']` to remove columns.
- **Column Addition**: Assign a new column using `df['new_col']` and provide values through a scalar, list, or calculation based on existing columns.


### Assigning new columns in method chains
In Pandas, method chaining is a powerful technique that allows you to perform multiple operations on a `DataFrame` in a single line of code, making your code more readable and concise. However, when it comes to assigning new columns within a method chain, the typical approach of directly assigning a new column (e.g., `df['new_column'] = value`) does not fit well within a chain. To address this, Pandas provides the `assign()` method, which allows you to add or modify columns within a method chain.

### Using `assign()` to Add or Modify Columns in Method Chains

The `assign()` method returns a new `DataFrame` with the additional or modified columns, allowing it to be seamlessly integrated into a method chain.

#### Example 1: Adding a New Column

```python
import pandas as pd

# Create a sample DataFrame
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35]
})

# Method chaining with assign to add a new column
df = (df
      .assign(Age_in_10_Years=df['Age'] + 10)
      .assign(Salary=[50000, 60000, 70000])
     )

print(df)
```

Output:
```
      Name  Age  Age_in_10_Years  Salary
0    Alice   25               35   50000
1      Bob   30               40   60000
2  Charlie   35               45   70000
```

#### Example 2: Modifying an Existing Column

```python
# Method chaining with assign to modify an existing column
df = (df
      .assign(Age_in_10_Years=df['Age_in_10_Years'] + 5)
     )

print(df)
```

Output:
```
      Name  Age  Age_in_10_Years  Salary
0    Alice   25               40   50000
1      Bob   30               45   60000
2  Charlie   35               50   70000
```

#### Example 3: Adding Multiple Columns at Once

You can add multiple columns in a single `assign()` call by passing multiple key-value pairs.

```python
# Adding multiple new columns in a single assign call
df = (df
      .assign(
          Bonus=df['Salary'] * 0.1,
          Total_Compensation=df['Salary'] + df['Salary'] * 0.1
      )
     )

print(df)
```

Output:
```
      Name  Age  Age_in_10_Years  Salary   Bonus  Total_Compensation
0    Alice   25               40   50000  5000.0              55000.0
1      Bob   30               45   60000  6000.0              66000.0
2  Charlie   35               50   70000  7000.0              77000.0
```

### Key Points

- **Chaining-Compatible**: The `assign()` method returns a new `DataFrame`, making it suitable for method chaining.
- **Multiple Assignments**: You can add or modify multiple columns in a single `assign()` call by passing multiple keyword arguments.
- **Readability**: Method chaining with `assign()` enhances readability and ensures that your data transformation pipeline is clear and concise.


The `assign()` method is the preferred approach for adding or modifying columns within method chains in Pandas. It allows you to keep your code concise and maintainable, enabling you to perform complex data manipulations in a streamlined manner.
### Indexing / selection in DataFrame

Indexing and selection in a Pandas `DataFrame` allow you to access and manipulate data effectively. Here’s a detailed guide on different ways to perform indexing and selection.

### 1. Selecting Columns

#### a) Selecting a Single Column

- **Using Bracket Notation**:
  ```python
  import pandas as pd

  # Sample DataFrame
  df = pd.DataFrame({
      'Name': ['Alice', 'Bob', 'Charlie'],
      'Age': [25, 30, 35],
      'City': ['New York', 'Los Angeles', 'Chicago']
  })

  # Select a single column
  name_column = df['Name']
  print(name_column)
  ```

  Output:
  ```
  0     Alice
  1       Bob
  2   Charlie
  Name: Name, dtype: object
  ```

#### b) Selecting Multiple Columns

- **Using a List of Column Names**:
  ```python
  # Select multiple columns
  selected_columns = df[['Name', 'City']]
  print(selected_columns)
  ```

  Output:
  ```
        Name         City
  0    Alice     New York
  1      Bob  Los Angeles
  2  Charlie     Chicago
  ```

### 2. Selecting Rows

#### a) Selecting Rows by Index Position

- **Using `.iloc` for Positional Indexing**:
  ```python
  # Select the first row (position 0)
  first_row = df.iloc[0]
  print(first_row)
  ```

  Output:
  ```
  Name       Alice
  Age           25
  City    New York
  Name: 0, dtype: object
  ```

#### b) Selecting Rows by Index Label

- **Using `.loc` for Label-Based Indexing**:
  ```python
  # Assuming custom index labels
  df = pd.DataFrame({
      'Name': ['Alice', 'Bob', 'Charlie'],
      'Age': [25, 30, 35],
      'City': ['New York', 'Los Angeles', 'Chicago']
  }, index=['a', 'b', 'c'])

  # Select the row with index label 'a'
  row_a = df.loc['a']
  print(row_a)
  ```

  Output:
  ```
  Name       Alice
  Age           25
  City    New York
  Name: a, dtype: object
  ```

#### c) Selecting Multiple Rows

- **Using `.iloc` for Multiple Rows**:
  ```python
  # Select the first two rows
  first_two_rows = df.iloc[0:2]
  print(first_two_rows)
  ```

  Output:
  ```
        Name  Age         City
  a    Alice   25     New York
  b      Bob   30  Los Angeles
  ```

- **Using `.loc` for Multiple Rows**:
  ```python
  # Select rows with labels 'a' and 'c'
  selected_rows = df.loc[['a', 'c']]
  print(selected_rows)
  ```

  Output:
  ```
        Name  Age     City
  a    Alice   25  New York
  c  Charlie   35  Chicago
  ```

### 3. Boolean Indexing

You can use boolean conditions to filter rows.

```python
# Select rows where Age > 30
age_filter = df[df['Age'] > 30]
print(age_filter)
```

Output:
```
        Name  Age     City
c  Charlie   35  Chicago
```

### 4. Mixed Selection of Rows and Columns

#### a) Selecting Specific Rows and Columns

- **Using `.iloc` for Positional Indexing**:
  ```python
  # Select the first row and the first two columns
  selection = df.iloc[0, 0:2]
  print(selection)
  ```

  Output:
  ```
  Name    Alice
  Age        25
  Name: a, dtype: object
  ```

- **Using `.loc` for Label-Based Indexing**:
  ```python
  # Select specific rows and columns by labels
  selection = df.loc['a', ['Name', 'City']]
  print(selection)
  ```

  Output:
  ```
  Name       Alice
  City    New York
  Name: a, dtype: object
  ```

### 5. Conditional Selection with `query()`

The `query()` method allows you to select rows based on a condition.

```python
# Select rows where the City is 'Chicago'
chicago_filter = df.query("City == 'Chicago'")
print(chicago_filter)
```

Output:
```
        Name  Age     City
c  Charlie   35  Chicago
```

### 6. Setting Values in a DataFrame

You can also set values in a `DataFrame` using `.iloc`, `.loc`, or direct column assignment.

- **Setting a Value for a Specific Cell**:
  ```python
  # Set the 'Age' of the first row to 26
  df.loc['a', 'Age'] = 26
  print(df)
  ```

  Output:
  ```
        Name  Age         City
  a    Alice   26     New York
  b      Bob   30  Los Angeles
  c  Charlie   35     Chicago
  ```


- **Column Selection**: Use `df['column']` for a single column, `df[['col1', 'col2']]` for multiple columns.
- **Row Selection**: Use `.iloc[]` for positional indexing, `.loc[]` for label-based indexing.
- **Boolean Indexing**: Filter rows using conditions like `df[df['column'] > value]`.
- **Mixed Selection**: Combine row and column indexing to access specific parts of the `DataFrame`.
- **Conditional Selection with `query()`**: Use `df.query("condition")` for more readable 
conditional filtering.


### Data alignment and arithmetic

Data alignment and arithmetic in Pandas allow you to perform operations on `DataFrame` and `Series` objects while aligning data based on their indices (both row and column labels). This ensures that arithmetic operations are performed correctly even when the data structures involved have different shapes or labels.

### 1. Data Alignment

Data alignment refers to the automatic matching of data based on index labels during arithmetic operations. When performing operations between `Series` or `DataFrame` objects, Pandas aligns the data on both the row and column labels.

#### Example 1: Alignment in `Series`

```python
import pandas as pd

# Two Series with different indices
s1 = pd.Series([1, 2, 3], index=['a', 'b', 'c'])
s2 = pd.Series([4, 5, 6], index=['b', 'c', 'd'])

# Adding the two Series
result = s1 + s2
print(result)
```

Output:
```
a    NaN
b    6.0
c    8.0
d    NaN
dtype: float64
```

- **Explanation**: The result shows that the values from `s1` and `s2` are aligned by their indices. The indices `b` and `c` exist in both `Series`, so their values are added. The indices `a` and `d` exist only in one `Series`, so the result is `NaN` for those indices.

#### Example 2: Alignment in `DataFrame`

```python
# Two DataFrames with overlapping and non-overlapping columns and rows
df1 = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4, 5, 6]
}, index=['a', 'b', 'c'])

df2 = pd.DataFrame({
    'B': [7, 8, 9],
    'C': [10, 11, 12]
}, index=['b', 'c', 'd'])

# Adding the two DataFrames
result = df1 + df2
print(result)
```

Output:
```
     A     B   C
a  NaN   NaN NaN
b  NaN  12.0 NaN
c  NaN  14.0 NaN
d  NaN   NaN NaN
```

- **Explanation**: The operation aligns both rows and columns. Only the common indices (`b`, `c`) and columns (`B`) between `df1` and `df2` are summed. The rest of the values are filled with `NaN` because they don’t have corresponding pairs in the other `DataFrame`.

### 2. Arithmetic Operations

Pandas supports element-wise arithmetic operations on `Series` and `DataFrame` objects, handling the alignment automatically.

#### Basic Arithmetic Operations

- **Addition (`+`)**: Adds corresponding elements.
- **Subtraction (`-`)**: Subtracts corresponding elements.
- **Multiplication (`*`)**: Multiplies corresponding elements.
- **Division (`/`)**: Divides corresponding elements.

These operations can be performed directly between `Series`, between `DataFrame`, or between a `Series` and a `DataFrame`.

#### Example 3: Arithmetic Between `Series`

```python
s1 = pd.Series([1, 2, 3], index=['a', 'b', 'c'])
s2 = pd.Series([4, 5, 6], index=['b', 'c', 'd'])

# Subtraction
result = s1 - s2
print(result)
```

Output:
```
a    NaN
b   -3.0
c   -3.0
d    NaN
dtype: float64
```

- **Explanation**: The subtraction occurs only where the indices match. The result is `NaN` for unmatched indices.

#### Example 4: Arithmetic Between `DataFrame` and `Series`

```python
# DataFrame and Series with matching columns
df = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4, 5, 6]
}, index=['a', 'b', 'c'])

s = pd.Series([1, 2], index=['A', 'B'])

# Subtract Series from DataFrame
result = df - s
print(result)
```

Output:
```
   A  B
a  0  2
b  1  3
c  2  4
```

- **Explanation**: The `Series` is broadcast across the `DataFrame`, and the subtraction is applied element-wise by matching the column labels.

### 3. Filling Missing Data During Arithmetic

You can handle missing data (resulting from non-overlapping indices) during arithmetic operations by using the `fill_value` parameter.

#### Example 5: Filling Missing Data

```python
# Add DataFrames with a fill_value of 0
result = df1.add(df2, fill_value=0)
print(result)
```

Output:
```
     A     B     C
a  1.0   4.0   0.0
b  2.0  12.0   0.0
c  3.0  14.0   0.0
d  0.0   9.0  12.0
```

- **Explanation**: The `fill_value` ensures that missing data is treated as `0` during the addition, rather than resulting in `NaN`.

### 4. Arithmetic Operations with Alignment Control

You can control the alignment behavior using the `align()` method, which allows for more advanced alignment operations.

#### Example 6: Using `align()`

```python
# Align df1 and df2 explicitly
aligned_df1, aligned_df2 = df1.align(df2, join='outer', axis=0)

# Perform an operation after alignment
result = aligned_df1 + aligned_df2
print(result)
```

- **Explanation**: The `align()` method can be used to explicitly align two `DataFrame` or `Series` objects before performing operations. The `join` parameter controls how to handle the alignment (`outer`, `inner`, `left`, `right`).


- **Data Alignment**: Pandas automatically aligns data based on index labels during arithmetic operations, ensuring that operations are applied only to matching elements.
- **Arithmetic Operations**: Perform element-wise operations such as addition, subtraction, multiplication, and division, while handling alignment.
- **Handling Missing Data**: Use `fill_value` to replace missing data with a specific value during arithmetic operations.
- **Advanced Alignment**: Use the `align()` method for more control over how data is aligned before performing operations.

These features make Pandas a powerful tool for data analysis, allowing you to work seamlessly with datasets of varying shapes and structures.

### Transposing
Transposing in Pandas involves flipping the rows and columns of a `DataFrame` or `Series`, effectively rotating the data structure. This is particularly useful when you need to switch the orientation of your data for analysis or visualization.

### 1. Transposing a DataFrame

To transpose a `DataFrame`, you can use the `.T` attribute or the `.transpose()` method. Both achieve the same result.

#### Example: Transposing a DataFrame

```python
import pandas as pd

# Sample DataFrame
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
})

# Transpose the DataFrame
df_transposed = df.T
print(df_transposed)
```

Output:
```
             0    1        2
Name     Alice  Bob  Charlie
Age         25   30       35
City  New York  Los Angeles  Chicago
```

- **Explanation**: The rows become columns, and the columns become rows. The original column labels (`'Name'`, `'Age'`, `'City'`) become the new index of the transposed `DataFrame`, and the original index (0, 1, 2) becomes the column labels.

### 2. Transposing a Series

A `Series` transposition isn't as common as with `DataFrame` because a `Series` is essentially a one-dimensional structure. However, when you transpose a `Series`, it effectively remains the same, as there’s only one axis to flip.

#### Example: Transposing a Series

```python
# Sample Series
s = pd.Series([1, 2, 3], index=['a', 'b', 'c'])

# Transpose the Series
s_transposed = s.T
print(s_transposed)
```

Output:
```
a    1
b    2
c    3
dtype: int64
```

- **Explanation**: The `Series` remains unchanged when transposed, as it is inherently one-dimensional.

### 3. Handling MultiIndex in Transposition

If your `DataFrame` or `Series` has a `MultiIndex`, transposing can be a bit more complex. The levels of the `MultiIndex` will also be flipped.

#### Example: Transposing a MultiIndex DataFrame

```python
# Sample MultiIndex DataFrame
arrays = [
    ['A', 'A', 'B', 'B'],
    ['one', 'two', 'one', 'two']
]
index = pd.MultiIndex.from_arrays(arrays, names=('upper', 'lower'))
df = pd.DataFrame({
    'col1': [1, 2, 3, 4],
    'col2': [5, 6, 7, 8]
}, index=index)

# Transpose the MultiIndex DataFrame
df_transposed = df.T
print(df_transposed)
```

Output:
```
upper       A        B     
lower     one  two  one  two
col1        1    2    3    4
col2        5    6    7    8
```

- **Explanation**: After transposition, the original rows (`A-one`, `A-two`, `B-one`, `B-two`) become columns, and the columns (`col1`, `col2`) become rows.

### 4. Practical Uses of Transposing

Transposing can be particularly useful in scenarios such as:
- **Reformatting Data**: When your data is in a wide format and you need it in a long format, or vice versa.
- **Pivoting Data**: Transposing can help when you need to pivot your data for aggregation or analysis.
- **Improving Readability**: Certain datasets might be easier to read or analyze when transposed.


- **Transposing a DataFrame**: Use `.T` or `.transpose()` to flip rows and columns.
- **Transposing a Series**: Transposing a `Series` has no effect because it’s one-dimensional.
- **MultiIndex Considerations**: Transposing a `MultiIndex` `DataFrame` flips the levels of the index as well.

### DataFrame interoperability with NumPy functions

Pandas `DataFrame` objects are designed to work seamlessly with NumPy, making it easy to apply NumPy functions to your data. This interoperability allows you to leverage the extensive set of mathematical and statistical functions available in NumPy directly on Pandas `DataFrame` and `Series`.

### 1. Applying NumPy Functions to DataFrames

You can apply NumPy functions to an entire `DataFrame` or `Series`. The function will be applied element-wise to the data.

#### Example 1: Applying a NumPy Function Element-wise

```python
import pandas as pd
import numpy as np

# Sample DataFrame
df = pd.DataFrame({
    'A': [1, 4, 9, 16],
    'B': [1, 2, 3, 4]
})

# Apply the square root function from NumPy
sqrt_df = np.sqrt(df)
print(sqrt_df)
```

Output:
```
          A    B
0  1.000000  1.0
1  2.000000  1.414214
2  3.000000  1.732051
3  4.000000  2.000000
```

- **Explanation**: The `np.sqrt()` function is applied element-wise to each value in the `DataFrame`, resulting in a new `DataFrame` with the square roots of the original values.

### 2. Aggregation Functions

NumPy's aggregation functions, such as `np.sum()`, `np.mean()`, and `np.std()`, can be used to aggregate values across a `DataFrame` or `Series`.

#### Example 2: Aggregating Data

```python
# Sum of each column
column_sum = np.sum(df)
print(column_sum)
```

Output:
```
A    30
B    10
dtype: int64
```

- **Explanation**: The `np.sum()` function sums the values of each column in the `DataFrame`, returning a `Series` with the sums.

#### Example 3: Aggregating Along Rows

```python
# Mean of each row
row_mean = np.mean(df, axis=1)
print(row_mean)
```

Output:
```
0    1.0
1    3.0
2    6.0
3   10.0
dtype: float64
```

- **Explanation**: The `axis=1` parameter tells NumPy to perform the operation across rows (instead of columns), resulting in the mean of each row.

### 3. Broadcasting with NumPy Functions

NumPy functions that support broadcasting can also be applied to `DataFrame` objects. Broadcasting allows you to perform operations between arrays of different shapes.

#### Example 4: Broadcasting

```python
# Add a NumPy array to a DataFrame
arr = np.array([1, 2])
broadcast_result = df + arr
print(broadcast_result)
```

Output:
```
    A  B
0   2  3
1   5  4
2  10  5
3  17  6
```

- **Explanation**: The `arr` is broadcasted across the `DataFrame` columns, adding `[1, 2]` to each row.

### 4. Using NumPy Functions for Conditional Operations

You can also use NumPy's conditional functions like `np.where()` to perform element-wise conditional operations.

#### Example 5: Conditional Operations with `np.where`

```python
# Create a new column based on a condition
df['C'] = np.where(df['A'] > 10, 'High', 'Low')
print(df)
```

Output:
```
    A  B     C
0   1  1   Low
1   4  2   Low
2   9  3   Low
3  16  4  High
```

- **Explanation**: The `np.where()` function creates a new column `C` where the value is `'High'` if the corresponding value in column `A` is greater than 10, and `'Low'` otherwise.

### 5. Handling Missing Data with NumPy

NumPy functions can be used in conjunction with Pandas' missing data handling capabilities.

#### Example 6: Replacing Missing Data

```python
# Introduce missing data
df.loc[2, 'B'] = np.nan

# Replace missing values with a default value
filled_df = df.fillna(np.mean(df))
print(filled_df)
```

Output:
```
      A     B     C
0   1.0  1.0   Low
1   4.0  2.0   Low
2   9.0  2.333333  Low
3  16.0  4.0  High
```

- **Explanation**: The `np.mean(df)` calculates the mean of each column, and `fillna()` replaces the `NaN` values with these means.

### 6. Combining NumPy and Pandas for Custom Operations

You can combine the power of NumPy and Pandas to perform more complex operations on your data.

#### Example 7: Custom Operation Using NumPy and Pandas

```python
# Apply a custom NumPy function to a DataFrame
custom_result = df.apply(lambda x: np.log(x) if np.issubdtype(x.dtype, np.number) else x)
print(custom_result)
```

Output:
```
          A         B     C
0  0.000000  0.000000   Low
1  1.386294  0.693147   Low
2  2.197225  0.847298   Low
3  2.772589  1.386294  High
```

- **Explanation**: The `apply()` method is used to apply a custom function (in this case, `np.log`) to each element in the `DataFrame`. The function checks the data type and only applies `np.log` to numeric data, leaving other data types unchanged.


- **Element-wise Operations**: NumPy functions can be applied directly to `DataFrame` and `Series` objects for element-wise operations.
- **Aggregation**: NumPy aggregation functions (e.g., `np.sum`, `np.mean`) can summarize data across rows or columns.
- **Broadcasting**: NumPy broadcasting rules apply to operations between `DataFrame` objects and NumPy arrays.
- **Conditional Operations**: Use `np.where()` for element-wise conditional operations in Pandas.
- **Handling Missing Data**: NumPy functions can be combined with Pandas' missing data handling capabilities.
- **Custom Operations**: Combine NumPy and Pandas to create custom functions and operations.

This interoperability makes Pandas a flexible and powerful tool for data manipulation and analysis, leveraging the mathematical capabilities of NumPy.
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


































