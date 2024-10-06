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

This interoperability makes Pandas a flexible and powerful tool for data manipulation and analysis, leveraging the mathematical capabilities of NumPy..


### Console display

In pandas, you can adjust the console display settings using several built-in options that control how data is presented in the console. Here are some key settings you can tweak:

### 1. **Display Maximum Rows and Columns:**

- `pd.set_option('display.max_rows', n)` – This sets the maximum number of rows displayed (replace `n` with the desired number of rows).
- `pd.set_option('display.max_columns', n)` – This sets the maximum number of columns displayed.

For example:
```python
import pandas as pd

# Show all rows and columns
pd.set_option('display.max_rows', None)
pd.set_option('display.max_columns', None)
```

### 2. **Control Display Width:**

- `pd.set_option('display.width', n)` – Sets the total display width.
- `pd.set_option('display.max_colwidth', n)` – Sets the maximum width of a single column.

Example:
```python
# Set display width to 100 characters
pd.set_option('display.width', 100)

# Set max column width to 50 characters
pd.set_option('display.max_colwidth', 50)
```

### 3. **Display Floating Point Precision:**

- `pd.set_option('display.float_format', '{:.2f}'.format)` – Formats floating-point numbers to two decimal places.

Example:
```python
# Display floats with two decimal places
pd.set_option('display.float_format', '{:.2f}'.format)
```

### 4. **Display Column Headers and Index:**

- `pd.set_option('display.show_dimensions', True)` – Displays the dimensions (number of rows and columns) below the output.

Example:
```python
# Show dimensions at the end of the DataFrame output
pd.set_option('display.show_dimensions', True)
```

These settings can help make your DataFrame output more readable depending on your needs.

### Head and tail

In pandas, the `head()` and `tail()` methods are used to view the first and last few rows of a DataFrame, respectively.

### 1. **`head()` Method**
The `head()` method returns the first n rows of a DataFrame or Series.

```python
# Syntax:
df.head(n)

# Example:
import pandas as pd

data = {'A': [1, 2, 3, 4, 5], 'B': [10, 20, 30, 40, 50]}
df = pd.DataFrame(data)

# Display the first 3 rows (default is 5 if n is not specified)
print(df.head(3))
```

Output:
```
   A   B
0  1  10
1  2  20
2  3  30
```

### 2. **`tail()` Method**
The `tail()` method returns the last n rows of a DataFrame or Series.

```python
# Syntax:
df.tail(n)

# Example:
# Display the last 2 rows
print(df.tail(2))
```

Output:
```
   A   B
3  4  40
4  5  50
```

Both `head()` and `tail()` are useful for quickly inspecting a portion of the data without needing to print the entire DataFrame.


### Attributes and underlying data

In pandas, a DataFrame (or Series) has several attributes that provide access to the underlying data, metadata, and structural information. Here are some key attributes related to underlying data and the structure of a DataFrame or Series:

### 1. **`.values`**
- Returns the underlying data as a NumPy array (deprecated in favor of `.to_numpy()`).

```python
import pandas as pd

data = {'A': [1, 2, 3], 'B': [4, 5, 6]}
df = pd.DataFrame(data)

# Get the underlying data as a NumPy array
print(df.values)
```

Output:
```
array([[1, 4],
       [2, 5],
       [3, 6]])
```

### 2. **`.to_numpy()`**
- The recommended way to get the underlying data as a NumPy array (more flexible than `.values`).

```python
# Get the underlying data using .to_numpy()
print(df.to_numpy())
```

Output:
```
array([[1, 4],
       [2, 5],
       [3, 6]])
```

### 3. **`.index`**
- Returns the index (row labels) of the DataFrame.

```python
# Get the row index (0, 1, 2)
print(df.index)
```

Output:
```
RangeIndex(start=0, stop=3, step=1)
```

### 4. **`.columns`**
- Returns the column labels of the DataFrame.

```python
# Get the column labels ('A', 'B')
print(df.columns)
```

Output:
```
Index(['A', 'B'], dtype='object')
```

### 5. **`.dtypes`**
- Returns the data types of each column.

```python
# Get the data types of the columns
print(df.dtypes)
```

Output:
```
A    int64
B    int64
dtype: object
```

### 6. **`.shape`**
- Returns the shape (number of rows and columns) of the DataFrame as a tuple.

```python
# Get the shape of the DataFrame
print(df.shape)
```

Output:
```
(3, 2)
```

### 7. **`.size`**
- Returns the total number of elements in the DataFrame (rows × columns).

```python
# Get the total number of elements
print(df.size)
```

Output:
```
6
```

### 8. **`.ndim`**
- Returns the number of dimensions (2 for DataFrame, 1 for Series).

```python
# Get the number of dimensions
print(df.ndim)
```

Output:
```
2
```

### 9. **`.T` (Transpose)**
- Returns the transpose of the DataFrame (i.e., rows become columns and vice versa).

```python
# Transpose the DataFrame
print(df.T)
```

Output:
```
   0  1  2
A  1  2  3
B  4  5  6
```

These attributes provide easy access to the structure and underlying data of a DataFrame or Series for manipulation, analysis, or further processing.


### Accelerated operations

Pandas, built on top of NumPy, allows for **accelerated operations** using vectorization, broadcasting, and efficient low-level implementations. These operations are optimized for performance, especially for large datasets. Below are examples of how to leverage accelerated operations in pandas:

### 1. **Vectorized Operations**
Pandas supports element-wise operations that apply functions to entire columns or DataFrames without needing explicit loops. These operations are highly optimized.

```python
import pandas as pd

# Sample DataFrame
data = {'A': [1, 2, 3], 'B': [4, 5, 6]}
df = pd.DataFrame(data)

# Vectorized addition (adding a constant)
df['A'] = df['A'] + 10

# Vectorized subtraction (element-wise)
df['B'] = df['B'] - df['A']

print(df)
```

Output:
```
    A  B
0  11 -7
1  12 -7
2  13 -7
```

### 2. **Using NumPy Functions**
Pandas integrates well with NumPy, allowing you to perform accelerated operations using NumPy functions on DataFrame and Series objects.

```python
import numpy as np

# Apply a NumPy function (e.g., square root)
df['A_sqrt'] = np.sqrt(df['A'])

print(df)
```

Output:
```
    A  B  A_sqrt
0  11 -7  3.3166
1  12 -7  3.4641
2  13 -7  3.6055
```

### 3. **Broadcasting**
Broadcasting allows applying operations between DataFrames or Series of different shapes, automatically expanding dimensions to make the shapes compatible.

```python
# Broadcasting a scalar (single value) across a DataFrame
df['C'] = df['A'] * 2

print(df)
```

Output:
```
    A  B  A_sqrt   C
0  11 -7  3.3166  22
1  12 -7  3.4641  24
2  13 -7  3.6055  26
```

### 4. **`apply()` with NumPy for Row/Column-wise Operations**
The `.apply()` method can be used to apply functions along rows or columns in an accelerated manner, especially if combined with NumPy functions.

```python
# Apply NumPy log function along a column
df['A_log'] = df['A'].apply(np.log)

print(df)
```

Output:
```
    A  B  A_sqrt   C     A_log
0  11 -7  3.3166  22  2.397895
1  12 -7  3.4641  24  2.484907
2  13 -7  3.6055  26  2.564949
```

### 5. **Boolean Indexing (Filtering)**
Boolean indexing allows for efficient filtering based on conditions. It avoids loops and speeds up selection and filtering.

```python
# Filter rows where column 'A' is greater than 11
filtered_df = df[df['A'] > 11]

print(filtered_df)
```

Output:
```
    A  B  A_sqrt   C     A_log
1  12 -7  3.4641  24  2.484907
2  13 -7  3.6055  26  2.564949
```

### 6. **Parallelization with `swifter` (Optional)** 
You can accelerate operations further by using external libraries like `swifter` to automatically parallelize the `apply()` function.

```bash
pip install swifter
```

```python
import swifter

# Parallelize apply operations
df['A_exp'] = df['A'].swifter.apply(np.exp)

print(df)
```

### 7. **`eval()` and `query()` for Efficient Expressions**
`eval()` and `query()` are optimized for evaluating expressions and conditions over DataFrames.

```python
# Use eval to compute a new column from an expression
df.eval('D = A + B', inplace=True)

# Use query to filter rows efficiently
result = df.query('A > 12')

print(result)
```

Output:
```
    A  B  A_sqrt   C     A_log   D
2  13 -7  3.6055  26  2.564949  6
```

### 8. **GroupBy with Aggregations**
`groupby()` operations can be accelerated by applying efficient aggregations like `mean()`, `sum()`, `count()`, etc.

```python
# Group by and compute the sum of columns 'A' and 'B'
grouped = df.groupby('A').sum()

print(grouped)
```

- **Vectorization** allows applying operations to entire arrays/DataFrames at once.
- **Broadcasting** enables operations between objects of different shapes.
- **NumPy functions** are seamlessly integrated.
- **Boolean indexing** efficiently filters rows.
- **`eval()` and `query()`** improve performance for expressions.


### Flexible binary operations
Pandas provides **flexible binary operations** that allow element-wise operations between two DataFrames, Series, or between a DataFrame/Series and a scalar. These operations include addition, subtraction, multiplication, division, etc. The key feature of flexible binary operations is the ability to handle missing data and align on indexes or columns.

Here’s an overview of the flexible binary operations and how to use them:

### 1. **Common Binary Operations**
Pandas provides a set of **arithmetic methods** that are flexible versions of standard operators:

| Operation  | Equivalent Operator | Flexible Method  |
|------------|---------------------|------------------|
| Addition   | `+`                 | `add()`          |
| Subtraction| `-`                 | `sub()`          |
| Multiplication | `*`             | `mul()`          |
| Division   | `/`                 | `div()`          |
| Floor Division | `//`            | `floordiv()`     |
| Modulus    | `%`                 | `mod()`          |
| Power      | `**`                | `pow()`          |

### 2. **Element-wise Binary Operations**

These flexible methods allow you to specify how to handle missing data and to align on both rows and columns.

```python
import pandas as pd
import numpy as np

# Sample DataFrames
df1 = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, 5, 6]})
df2 = pd.DataFrame({'A': [10, 20, 30], 'B': [40, 50, 60]})

# Element-wise addition with alignment
result = df1.add(df2, fill_value=0)

print(result)
```

Output:
```
      A     B
0   11.0   44.0
1   22.0   55.0
2   30.0   66.0
```

In this example, `df1.add(df2, fill_value=0)` ensures that missing values (`NaN`) in `df1` are treated as `0` during the addition.

### 3. **Using `fill_value` for Handling Missing Data**
The `fill_value` parameter specifies a value to use in place of `NaN` before performing the operation.

```python
# Example of subtraction with fill_value
result = df1.sub(df2, fill_value=10)

print(result)
```

Output:
```
       A     B
0   -9.0  -36.0
1  -18.0  -45.0
2  -20.0  -54.0
```

Here, missing values in `df1` are replaced by `10` before subtraction, ensuring a clean result without `NaN` in the output.

### 4. **Aligning on Index or Columns**
By default, pandas aligns on both the index and columns when performing binary operations. However, you can perform operations only along specific axes.

```python
# Align along columns only
result = df1.mul(df2, axis='columns')

print(result)
```

Output:
```
       A     B
0   10.0  160.0
1   40.0  250.0
2    NaN  360.0
```

This multiplies each column of `df1` by the corresponding column in `df2`.

### 5. **Operations with Scalars**
Flexible binary operations also work with scalar values, broadcasting the scalar across the DataFrame or Series.

```python
# Add scalar to all elements
result = df1.add(10)

print(result)
```

Output:
```
      A     B
0   11.0   14.0
1   12.0   15.0
2    NaN   16.0
```

### 6. **Operations between DataFrame and Series (Row-wise / Column-wise Broadcasting)**
Pandas automatically aligns a Series with the DataFrame index (row-wise operation). To perform column-wise operations, you can specify `axis=0`.

```python
# Sample DataFrame and Series
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
s = pd.Series([10, 20])

# Subtract the Series from DataFrame columns (row-wise operation)
result = df.sub(s, axis=0)

print(result)
```

Output:
```
    A  B
0  -9 -6
1 -18 -15
2 NaN NaN
```

To perform a column-wise operation, you can use `axis=1`.

```python
# Column-wise subtraction with Series
result = df.sub(pd.Series([10, 20], index=['A', 'B']), axis=1)

print(result)
```

Output:
```
   A  B
0 -9 -16
1 -8 -15
2 -7 -14
```

### 7. **Other Binary Operations:**
There are more binary methods for combining data with custom handling of missing values and alignment. For example:
- `combine()`: Performs binary operations using a custom function and supports filling missing values.

```python
# Custom binary operation using combine
result = df1['A'].combine(df2['A'], lambda x, y: x if x > y else y)

print(result)
```

Output:
```
0    10.0
1    20.0
2    30.0
Name: A, dtype: float64
```

- **Vectorized element-wise operations** (`add()`, `sub()`, `mul()`, etc.).
- **Automatic alignment on index and columns**.
- **Handling of missing data using `fill_value`**.
- **Flexible row-wise or column-wise broadcasting with Series**.

These flexible binary operations offer a great way to perform efficient and customized element-wise computations across DataFrames or Series.


  #### Matching / broadcasting behavior

  **Matching and broadcasting behavior** in pandas refers to how pandas aligns data structures like DataFrames and Series when performing operations, particularly binary operations. These behaviors ensure that operations are flexible, allowing for element-wise computations even when the shapes of the data structures differ.

### Key Concepts in Matching and Broadcasting:

1. **Alignment on Index and Columns**: When performing operations between DataFrames or between a DataFrame and a Series, pandas aligns the labels (indexes and columns) before applying the operation. If any label is missing, `NaN` will be introduced in the result.

2. **Broadcasting**: If two objects (like a DataFrame and Series) have different shapes, pandas will "broadcast" the smaller object along the axis (rows or columns) to match the larger object. This is analogous to NumPy’s broadcasting but adapted for labeled data.

---

### 1. **Row-wise Broadcasting (Aligning on Index)**

When performing operations between a DataFrame and a Series, pandas aligns the Series along the DataFrame’s index (rows). This means that the Series values will be broadcasted across each row of the DataFrame, applying element-wise operations.

#### Example:
```python
import pandas as pd

# DataFrame with multiple rows
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})

# Series with values corresponding to DataFrame's index
s = pd.Series([10, 20, 30])

# Row-wise broadcasting (Series is aligned along rows)
result = df.sub(s, axis=0)

print(result)
```

Output:
```
    A   B
0  -9  -6
1 -18 -15
2 -27 -24
```

Here, pandas broadcasts the Series `s` (with values `[10, 20, 30]`) row-wise. The value `10` is subtracted from row 0, `20` from row 1, and `30` from row 2.

### 2. **Column-wise Broadcasting (Aligning on Columns)**

If you want to align a Series along the columns (i.e., apply an operation across each column), you can specify `axis=1`. The Series will be broadcasted along the columns.

#### Example:
```python
# Series with values corresponding to DataFrame's columns
s_col = pd.Series([10, 20], index=['A', 'B'])

# Column-wise broadcasting
result = df.sub(s_col, axis=1)

print(result)
```

Output:
```
   A   B
0 -9 -16
1 -8 -15
2 -7 -14
```

Here, `s_col` (with values `[10, 20]` corresponding to columns `'A'` and `'B'`) is broadcasted column-wise. The value `10` is subtracted from column `A` and `20` from column `B`.

### 3. **DataFrame vs DataFrame Operations (Alignment on Index and Columns)**

When performing operations between two DataFrames, pandas aligns both the **index** and the **columns**. If one DataFrame is missing labels that exist in the other, pandas fills in those positions with `NaN`.

#### Example:
```python
df1 = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, 5, 6]})
df2 = pd.DataFrame({'A': [10, 20, 30], 'C': [40, 50, 60]})

# DataFrames with different columns and NaN values
result = df1.add(df2, fill_value=0)

print(result)
```

Output:
```
      A    B     C
0   11.0  4.0  40.0
1   22.0  5.0  50.0
2   30.0  6.0  60.0
```

In this case:
- The column `A` exists in both `df1` and `df2`, so they are aligned and added.
- Column `B` exists only in `df1`, while column `C` exists only in `df2`. These columns are filled with the `fill_value` (`0`) where missing.
- Missing values (`NaN`) in `df1['A']` are treated as `0` during the addition.

### 4. **Scalar Broadcasting**

When performing operations between a DataFrame (or Series) and a scalar, pandas applies the scalar across all elements of the DataFrame or Series.

#### Example:
```python
# Scalar addition
result = df.add(10)

print(result)
```

Output:
```
      A   B
0  11.0  14
1  12.0  15
2   NaN  16
```

Here, the scalar `10` is broadcasted to every element in the DataFrame, adding `10` to each value. If there is a `NaN` in the DataFrame, it remains `NaN`.

### 5. **Handling Missing Data in Matching**

Pandas introduces `NaN` values if there is a mismatch in labels between two objects. However, you can use the `fill_value` parameter in binary operations to specify a value to use instead of `NaN`.

#### Example:
```python
# Fill missing values with 0 before performing the operation
result = df1.sub(df2, fill_value=0)

print(result)
```

Output:
```
      A    B     C
0   -9.0  4.0 -40.0
1  -18.0  5.0 -50.0
2  -30.0  6.0 -60.0
```

In this example  Missing values in `df1` and `df2` are filled with `0` before performing the subtraction, ensuring no `NaN` values in the output.

#### Flexible comparisons

Pandas supports **flexible comparison operations** that allow you to compare DataFrames, Series, or between a DataFrame/Series and a scalar in a flexible manner. These comparison operations (e.g., `==`, `>`, `<`, etc.) return a DataFrame or Series of booleans, where `True` represents the condition being met and `False` represents the condition not being met.

The **flexible comparison methods** in pandas allow for handling missing data (`NaN`), alignment of indexes and columns, and applying the comparisons element-wise.

### 1. **Flexible Comparison Methods**
Pandas provides the following flexible comparison methods:

| Operation      | Equivalent Operator | Flexible Method |
|----------------|---------------------|-----------------|
| Equal to       | `==`                 | `eq()`          |
| Not equal to   | `!=`                 | `ne()`          |
| Greater than   | `>`                  | `gt()`          |
| Greater than or equal to | `>=`        | `ge()`          |
| Less than      | `<`                  | `lt()`          |
| Less than or equal to | `<=`          | `le()`          |

These methods allow for optional handling of missing values using the `fill_value` parameter, which can be used to replace `NaN` before performing the comparison.

### 2. **Element-wise Comparisons Between DataFrames**

When comparing two DataFrames, pandas performs **element-wise comparisons** and aligns the indexes and columns.

#### Example:
```python
import pandas as pd
import numpy as np

# Sample DataFrames
df1 = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, 5, 6]})
df2 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 10, 6]})

# Element-wise comparison: Equal (eq)
result = df1.eq(df2)

print(result)
```

Output:
```
       A     B
0   True  True
1   True  False
2  False  True
```

Here, pandas compares `df1` and `df2` element-wise, returning `True` where the elements are equal and `False` where they are not. Missing values (`NaN`) are not equal to any value, including another `NaN`.

### 3. **Handling Missing Data with `fill_value`**
You can handle missing data by specifying a `fill_value` to replace `NaN` before performing the comparison. This is useful when you want to treat missing values as a specific value during the comparison.

#### Example:
```python
# Handle NaN by treating them as 0 before comparison
result = df1.eq(df2, fill_value=0)

print(result)
```

Output:
```
       A     B
0   True  True
1   True  False
2  False  True
```

In this example, missing values in `df1` are replaced with `0` before the comparison.

### 4. **Comparisons Between DataFrame and Scalar**

Pandas allows comparisons between a DataFrame (or Series) and a scalar, applying the comparison element-wise across the entire DataFrame.

#### Example:
```python
# Comparison of DataFrame elements greater than a scalar
result = df1.gt(3)

print(result)
```

Output:
```
       A      B
0  False   True
1  False   True
2  False   True
```

Here, pandas checks if each element in `df1` is greater than `3`. If the condition is met, `True` is returned; otherwise, `False`.

### 5. **Comparisons Between DataFrame and Series (Row-wise or Column-wise Broadcasting)**

Pandas aligns Series with the DataFrame index for row-wise comparisons, or with the columns for column-wise comparisons.

#### Row-wise Broadcasting Example:
```python
# Series aligned with rows
s = pd.Series([1, 5, 6])

# Compare each row in DataFrame with the Series
result = df1.lt(s, axis=0)

print(result)
```

Output:
```
       A      B
0  False  False
1   True  False
2  False  False
```

Here, the Series values `[1, 5, 6]` are compared with each row of `df1`. For each element, it checks if it is less than the corresponding value in the Series.

#### Column-wise Broadcasting Example:
```python
# Series aligned with columns
s = pd.Series({'A': 2, 'B': 5})

# Compare each column in DataFrame with the Series
result = df1.ge(s, axis=1)

print(result)
```

Output:
```
       A      B
0  False  False
1  True   True
2  False  True
```

Here, the Series values `{'A': 2, 'B': 5}` are compared column-wise with the DataFrame. For example, column `A` is compared against `2` and column `B` is compared against `5`.

### 6. **Chaining Comparisons with Logical Operators**
You can combine multiple comparisons using logical operators (`&` for AND, `|` for OR) to perform more complex comparisons.

#### Example:
```python
# Compare multiple conditions: Greater than 1 and less than 6
result = (df1 > 1) & (df1 < 6)

print(result)
```

Output:
```
       A      B
0  False  True
1   True  True
2  False  False
```

This checks if the elements in `df1` are greater than `1` and less than `6`.

### 7. **Comparisons on Series**

Pandas allows similar comparison operations on Series. Comparisons between Series align based on the index.

#### Example:
```python
# Sample Series
s1 = pd.Series([1, 2, np.nan], index=['A', 'B', 'C'])
s2 = pd.Series([1, 3, 3], index=['A', 'B', 'C'])

# Element-wise comparison: Not equal (ne)
result = s1.ne(s2)

print(result)
```

Output:
```
A    False
B     True
C     True
dtype: bool
```

Here, the two Series `s1` and `s2` are compared element-wise, returning `True` where the elements are not equal.



These flexible comparisons in pandas offer a powerful way to analyze and filter data based on conditions.
#### Boolean reductions
**Boolean reductions** in pandas are methods that reduce a DataFrame or Series of booleans to a single value (or a Series/column of values). These reductions typically answer questions like "Are all values `True`?" or "Is there at least one `True`?". Boolean reductions are commonly used for checking the outcomes of comparisons or conditions.

Here are the key Boolean reduction methods in pandas:

### 1. **`all()`**: Check if all elements are `True`

The `all()` method returns `True` if **all** elements are `True`, and `False` otherwise. You can apply it across an axis of a DataFrame (either rows or columns).

#### Example (Series):
```python
import pandas as pd

# Sample Series
s = pd.Series([True, True, False])

# Check if all elements are True
result = s.all()

print(result)  # Output: False
```

#### Example (DataFrame):
```python
# Sample DataFrame
df = pd.DataFrame({'A': [True, True, False], 'B': [True, True, True]})

# Check if all elements in each column are True
result = df.all()

print(result)
```

Output:
```
A    False
B     True
dtype: bool
```

Here, `all()` checks if all elements in each column are `True`. For column `A`, it returns `False` since one value is `False`, while for column `B`, it returns `True`.

You can also apply `all()` across rows by specifying `axis=1`.

#### Example (Row-wise):
```python
# Check if all elements in each row are True
result = df.all(axis=1)

print(result)
```

Output:
```
0     True
1     True
2    False
dtype: bool
```

### 2. **`any()`**: Check if any element is `True`

The `any()` method returns `True` if **at least one** element is `True`, and `False` if all elements are `False`.

#### Example (Series):
```python
# Check if any element is True
result = s.any()

print(result)  # Output: True
```

#### Example (DataFrame):
```python
# Check if any element in each column is True
result = df.any()

print(result)
```

Output:
```
A     True
B     True
dtype: bool
```

In this case, both columns contain at least one `True` value, so the result is `True` for both.

#### Example (Row-wise):
```python
# Check if any element in each row is True
result = df.any(axis=1)

print(result)
```

Output:
```
0     True
1     True
2     True
dtype: bool
```

### 3. **`sum()`**: Count the number of `True` values

In a Boolean context, `True` is equivalent to `1`, and `False` is equivalent to `0`. Therefore, you can use the `sum()` method to count how many elements are `True`.

#### Example (Series):
```python
# Count the number of True values
result = s.sum()

print(result)  # Output: 2
```

Here, two elements in the Series are `True`, so the result is `2`.

#### Example (DataFrame):
```python
# Count the number of True values in each column
result = df.sum()

print(result)
```

Output:
```
A    2
B    3
dtype: int64
```

You can also count `True` values row-wise by specifying `axis=1`.

#### Example (Row-wise):
```python
# Count the number of True values in each row
result = df.sum(axis=1)

print(result)
```

Output:
```
0    2
1    2
2    1
dtype: int64
```

### 4. **`idxmax()`**: Index of the first `True` value

The `idxmax()` method returns the index (or label) of the first occurrence of `True`. If no `True` values are found, it returns the first index (since `False` is treated as `0` and `True` as `1`).

#### Example (Series):
```python
# Find the index of the first True value
result = s.idxmax()

print(result)  # Output: 0
```

#### Example (DataFrame):
```python
# Find the index of the first True value in each column
result = df.idxmax()

print(result)
```

Output:
```
A    0
B    0
dtype: int64
```

### 5. **`idxmin()`**: Index of the first `False` value

The `idxmin()` method returns the index (or label) of the first occurrence of `False`. If all values are `True`, it returns the first index.

#### Example (Series):
```python
# Find the index of the first False value
result = s.idxmin()

print(result)  # Output: 2
```

#### Example (DataFrame):
```python
# Find the index of the first False value in each column
result = df.idxmin()

print(result)
```

Output:
```
A    2
B    NaN
dtype: object
```

In this case, column `A` has a `False` value at index `2`, while column `B` does not contain any `False` values, so `NaN` is returned.

### 6. **`count()`**: Count non-`NaN` values (can be used with booleans)

The `count()` method counts the number of non-`NaN` values in the DataFrame or Series. It can also be used with booleans to count how many elements were considered in the reduction.

#### Example:
```python
# Count non-NaN values in each column
result = df.count()

print(result)
```

Output:
```
A    3
B    3
dtype: int64
```

### 7. **`notna()` and `isna()` with Boolean Reductions**

`notna()` returns a DataFrame or Series with `True` for non-missing values and `False` for `NaN` values. You can combine this with `sum()`, `all()`, and `any()` for further reductions.

#### Example:
```python
# Sample DataFrame with NaN values
df = pd.DataFrame({'A': [True, np.nan, False], 'B': [np.nan, True, False]})

# Check if all values are non-NaN in each column
result = df.notna().all()

print(result)
```

Output:
```
A    False
B    False
dtype: bool
```


1. **`all()`**: Checks if all elements are `True`.
2. **`any()`**: Checks if at least one element is `True`.
3. **`sum()`**: Counts the number of `True` values.
4. **`idxmax()`**: Returns the index of the first `True` value.
5. **`idxmin()`**: Returns the index of the first `False` value.
6. **`count()`**: Counts the number of non-`NaN` values.
7. **`notna()`/`isna()`**: Used with Boolean reductions to handle missing data.


#### Comparing if objects are equivalent

In pandas, comparing if objects (DataFrames, Series, or other pandas structures) are equivalent can be done using various methods to check for equality in both values and structure (index, columns, etc.). These methods help determine whether two objects are identical in their content, shape, and missing data.

Here are the common ways to compare objects for equivalence in pandas:

### 1. **`equals()`**: Check if two objects are exactly the same
The `equals()` method checks if two pandas objects are **element-wise identical**, including both the values and the index/column structure. It returns `True` only if the two objects are exactly the same.

#### Example:
```python
import pandas as pd

# Sample DataFrames
df1 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
df2 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
df3 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 7]})

# Check if df1 and df2 are equivalent
result = df1.equals(df2)
print(result)  # Output: True

# Check if df1 and df3 are equivalent
result = df1.equals(df3)
print(result)  # Output: False
```

Here, `df1.equals(df2)` returns `True` because the two DataFrames have the same values, index, and column structure, while `df1.equals(df3)` returns `False` because one value differs.

#### Example (Series):
```python
# Sample Series
s1 = pd.Series([1, 2, 3])
s2 = pd.Series([1, 2, 3])
s3 = pd.Series([1, 2, 4])

# Check if s1 and s2 are equivalent
result = s1.equals(s2)
print(result)  # Output: True

# Check if s1 and s3 are equivalent
result = s1.equals(s3)
print(result)  # Output: False
```

### 2. **`==` (Element-wise comparison)**: Check if elements are equal

Using the `==` operator, you can perform an **element-wise comparison** between two DataFrames or Series. The result is a DataFrame or Series of booleans indicating whether each element is equal.

#### Example:
```python
# Element-wise comparison between df1 and df3
result = df1 == df3
print(result)
```

Output:
```
       A      B
0   True   True
1   True   True
2   True  False
```

This returns a DataFrame where `True` indicates matching elements and `False` indicates differences.

#### Example (Series):
```python
# Element-wise comparison between s1 and s3
result = s1 == s3
print(result)
```

Output:
```
0     True
1     True
2    False
dtype: bool
```

### 3. **`compare()`**: Show differences between two DataFrames

The `compare()` method is useful for identifying differences between two DataFrames. It returns a DataFrame showing where the values differ, along with the values from both DataFrames at those points.

#### Example:
```python
# Compare df1 and df3 to see differences
result = df1.compare(df3)

print(result)
```

Output:
```
     B        
  self other
2     6     7
```

In this case, the `compare()` method shows that in row 2, column `B`, `df1` has the value `6` while `df3` has the value `7`.

### 4. **`identical()` (in the context of indexes)**: Compare indexes

The `Index.equals()` method checks whether two indexes are identical.

#### Example:
```python
# Sample DataFrames with different indexes
df4 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]}, index=[0, 1, 2])
df5 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]}, index=[0, 1, 3])

# Check if the indexes are identical
result = df4.index.equals(df5.index)
print(result)  # Output: False
```

Here, the `index.equals()` method compares the indexes of `df4` and `df5`, which are not identical.

### 5. **`np.array_equal()`**: Compare objects for exact equivalence (with NumPy)

In some cases, you might want to use NumPy's `array_equal()` function for comparing pandas objects. This method checks if both the values and structure (including NaNs) are identical.

#### Example:
```python
import numpy as np

# Compare df1 and df2 with np.array_equal
result = np.array_equal(df1.values, df2.values)
print(result)  # Output: True
```

This function checks if the underlying values of `df1` and `df2` are exactly the same.

### 6. **`assert_frame_equal()` and `assert_series_equal()`**: Assert DataFrame or Series equality (used for testing)

Pandas provides `assert_frame_equal()` and `assert_series_equal()` functions for testing whether two objects are equal. If the objects are not equal, an assertion error is raised. This is especially useful for testing in development.

#### Example:
```python
from pandas.testing import assert_frame_equal

# Assert that df1 and df2 are equal (no output means they are equal)
assert_frame_equal(df1, df2)

# Assert that df1 and df3 are equal (this will raise an AssertionError)
# assert_frame_equal(df1, df3)
```

### 7. **Handling `NaN` Values in Comparisons**

Pandas treats `NaN` values as unequal to any value, including other `NaN` values, which can cause issues when comparing objects containing missing data.

#### Example:
```python
# Sample DataFrames with NaN values
df6 = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, 5, 6]})
df7 = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, 5, 6]})

# Check if df6 and df7 are equivalent
result = df6.equals(df7)
print(result)  # Output: True
```

Here, `equals()` considers `NaN` values in the same positions to be equal. However, an element-wise comparison with `==` would return `False` for `NaN` values.


1. **`equals()`**: Check if two objects are exactly identical in both values and structure.
2. **`==`**: Perform element-wise comparison, returning a DataFrame/Series of booleans.
3. **`compare()`**: Highlight the differences between two DataFrames.
4. **`Index.equals()`**: Check if two indexes are identical.
5. **`np.array_equal()`**: Use NumPy to compare the underlying data arrays.
6. **`assert_frame_equal()` / `assert_series_equal()`**: Assert equality, raising an error if not equal (useful in tests).
7. **Handling `NaN` values**: `equals()` treats `NaN` in the same positions as equivalent, but `==` does not.



#### Comparing array-like objects

In pandas, comparing **array-like objects** (such as Series, DataFrames, NumPy arrays, or lists) involves various methods to check if they have equivalent values, structures, or shapes. Depending on the type of comparison, you may need to focus on element-wise comparison, shape matching, or deeper checks for equivalence, including handling NaN values.

Here are some methods and techniques to compare array-like objects in pandas:

### 1. **Element-wise Comparison using `==` Operator**

When comparing two array-like objects (Series, DataFrames, or NumPy arrays), you can use the `==` operator for **element-wise** comparisons. This will return a DataFrame or Series of booleans showing where elements match.

#### Example (Comparing Series):
```python
import pandas as pd

# Two Series for comparison
s1 = pd.Series([1, 2, 3])
s2 = pd.Series([1, 2, 4])

# Element-wise comparison
result = s1 == s2

print(result)
```

Output:
```
0     True
1     True
2    False
dtype: bool
```

#### Example (Comparing DataFrames):
```python
# Two DataFrames for comparison
df1 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
df2 = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 7]})

# Element-wise comparison
result = df1 == df2

print(result)
```

Output:
```
       A      B
0   True   True
1   True   True
2   True  False
```

This element-wise comparison shows which elements match and which do not.

### 2. **`numpy.array_equal()`**: Compare Arrays or Pandas Objects for Exact Equivalence

For comparing two arrays (or pandas objects treated as arrays), `numpy.array_equal()` is a good choice because it checks if both the values and shapes are identical, including handling NaN values.

#### Example (Comparing DataFrames):
```python
import numpy as np

# Use np.array_equal to compare DataFrames
result = np.array_equal(df1.values, df2.values)

print(result)  # Output: False
```

In this case, `np.array_equal()` checks if the underlying NumPy arrays in the two DataFrames are identical.

#### Example (Handling NaN values):
```python
df3 = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, 5, 6]})
df4 = pd.DataFrame({'A': [1, 2, np.nan], 'B': [4, 5, 6]})

# Use np.array_equal to compare DataFrames with NaN values
result = np.array_equal(df3.values, df4.values, equal_nan=True)

print(result)  # Output: True
```

The `equal_nan=True` argument ensures that `NaN` values are treated as equal.

### 3. **`pandas.DataFrame.equals()` and `pandas.Series.equals()`**

The `equals()` method is the most reliable way to check if two pandas objects are element-wise identical, including both the values and the structure (e.g., index and columns).

#### Example (Comparing Series):
```python
# Check if two Series are equivalent
result = s1.equals(s2)

print(result)  # Output: False
```

#### Example (Comparing DataFrames):
```python
# Check if two DataFrames are equivalent
result = df1.equals(df2)

print(result)  # Output: False
```

This method returns `True` only if the two objects are identical, including their index and column structures.

### 4. **`pandas.DataFrame.compare()`**: Show Differences Between DataFrames

The `compare()` method allows you to find and display the differences between two DataFrames.

#### Example:
```python
# Use compare() to show differences between df1 and df2
result = df1.compare(df2)

print(result)
```

Output:
```
     B        
  self other
2     6     7
```

The result shows the values that differ between `df1` and `df2` in column `B`, with the values from both DataFrames (`self` and `other`).

### 5. **Broadcasting and Alignment in Pandas**

When comparing arrays of different shapes, pandas will attempt to **broadcast** or **align** the objects based on their index or column labels. This ensures that comparisons are made element-wise between the appropriate values.

#### Example (Different Indexes):
```python
# DataFrames with different indexes
df5 = pd.DataFrame({'A': [1, 2, 3]}, index=[0, 1, 2])
df6 = pd.DataFrame({'A': [1, 2, 3]}, index=[1, 2, 3])

# Element-wise comparison with automatic alignment
result = df5 == df6

print(result)
```

Output:
```
       A
0    NaN
1    True
2    True
3    NaN
```

In this case, pandas aligns the DataFrames based on their index, and non-aligned values are treated as `NaN`.

### 6. **`assert_series_equal()` and `assert_frame_equal()`**

In testing environments, pandas provides functions to assert that two Series or DataFrames are equal. These functions raise an `AssertionError` if the objects are not equal.

#### Example (Testing for Equality):
```python
from pandas.testing import assert_series_equal, assert_frame_equal

# Asserting that two DataFrames are equal (raises no error if true)
assert_frame_equal(df1, df2)  # Will raise an AssertionError because they're not equal
```

### 7. **Handling NaN Values in Comparisons**

By default, `NaN` values are not considered equal to each other in pandas. However, you can use special methods to handle this.

- **`pandas.Series.eq()`** or **`pandas.DataFrame.eq()`**: These methods perform element-wise comparisons and allow you to specify how `NaN` values should be handled.
  
#### Example:
```python
# Use eq() to compare two Series while treating NaN as equal
result = s1.eq(s2, fill_value=np.nan)

print(result)
```

This approach fills missing values (like `NaN`) before performing the comparison.



1. **`==` operator**: Performs element-wise comparison and returns a DataFrame or Series of booleans.
2. **`numpy.array_equal()`**: Checks if two arrays (or DataFrame/Series values) are exactly the same, with an option to handle NaNs.
3. **`equals()`**: Checks if two pandas objects (DataFrames/Series) are exactly the same, including index/column structure.
4. **`compare()`**: Shows the differences between two DataFrames.
5. **Broadcasting and alignment**: Handles comparisons between objects of different shapes by aligning them based on labels.
6. **`assert_series_equal()` and `assert_frame_equal()`**: Used in testing to assert equality of Series or DataFrames.
7. **Handling NaN values**: Special methods (`eq()`, `numpy.array_equal()`, etc.) allow you to handle comparisons involving `NaN` values.


#### Combining overlapping data sets

Combining overlapping datasets in Pandas is essential when you need to merge data from different sources, especially when the datasets share some common columns or rows but differ in others. Pandas provides multiple ways to combine overlapping datasets, such as `merge()`, `concat()`, `join()`, and arithmetic operations with alignment.

### Methods to Combine Overlapping DataSets:

1. **Using `merge()` for Overlapping Datasets**
2. **Using `concat()` for Overlapping Datasets**
3. **Using `combine_first()` to Fill Missing Data**
4. **Using `join()` to Combine Datasets on Index**
5. **Arithmetic Operations and Alignment**

### 1. Using `merge()` for Overlapping Datasets

The `merge()` function is used for database-style joins between two datasets on one or more common columns. It handles overlapping data based on a key or index.

#### Example: Merging Overlapping Datasets on a Key

```python
import pandas as pd

# Dataset 1
df1 = pd.DataFrame({
    'ID': [1, 2, 3],
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35]
})

# Dataset 2
df2 = pd.DataFrame({
    'ID': [2, 3, 4],
    'City': ['New York', 'Los Angeles', 'Chicago'],
    'Salary': [50000, 60000, 70000]
})

# Merge on the 'ID' column
merged_df = pd.merge(df1, df2, on='ID', how='outer')
print(merged_df)
```

Output:
```
   ID     Name   Age         City   Salary
0   1    Alice  25.0          NaN      NaN
1   2      Bob  30.0     New York  50000.0
2   3  Charlie  35.0  Los Angeles  60000.0
3   4      NaN   NaN      Chicago  70000.0
```

- **Explanation**: The `merge()` function combines `df1` and `df2` based on the common `ID` column. The `how='outer'` argument ensures that all rows from both datasets are included, and missing values are filled with `NaN`.

#### Types of Joins:
- **Inner Join** (`how='inner'`): Only rows with keys present in both DataFrames are kept.
- **Left Join** (`how='left'`): All rows from the left DataFrame are kept, with matching data from the right DataFrame.
- **Right Join** (`how='right'`): All rows from the right DataFrame are kept, with matching data from the left DataFrame.
- **Outer Join** (`how='outer'`): All rows from both DataFrames are included.

### 2. Using `concat()` for Overlapping Datasets

The `concat()` function concatenates two or more DataFrames along a particular axis (either rows or columns). This is useful when you want to stack datasets vertically or horizontally.

#### Example: Concatenating Overlapping Datasets Vertically

```python
# Concatenate along rows (axis=0)
concatenated_df = pd.concat([df1, df2], axis=0, ignore_index=True)
print(concatenated_df)
```

Output:
```
    Age     City  ID     Name   Salary
0  25.0      NaN   1    Alice      NaN
1  30.0      NaN   2      Bob      NaN
2  35.0      NaN   3  Charlie      NaN
3   NaN      New York   2      NaN  50000.0
4   NaN  Los Angeles   3      NaN  60000.0
5   NaN      Chicago   4      NaN  70000.0
```

- **Explanation**: `concat()` combines the two DataFrames vertically. Since there are overlapping columns (`ID`), they are aligned, but other columns will be filled with `NaN` where there are no matching values.

#### Example: Concatenating Overlapping Datasets Horizontally

```python
# Concatenate along columns (axis=1)
concatenated_df = pd.concat([df1, df2], axis=1)
print(concatenated_df)
```

Output:
```
   ID     Name   Age  ID         City   Salary
0   1    Alice  25.0   2     New York  50000.0
1   2      Bob  30.0   3  Los Angeles  60000.0
2   3  Charlie  35.0   4      Chicago  70000.0
```

- **Explanation**: Here, `concat()` combines the two DataFrames horizontally (along columns). It concatenates them side by side without aligning on any key or index.

### 3. Using `combine_first()` to Fill Missing Data

The `combine_first()` method is useful when you have two datasets that overlap, and you want to combine them while filling missing values from the second dataset.

#### Example: Filling Missing Data

```python
# Fill missing values in df1 with values from df2
combined_df = df1.combine_first(df2)
print(combined_df)
```

Output:
```
    Age         City   ID     Name   Salary
0  25.0          NaN   1    Alice      NaN
1  30.0     New York   2      Bob  50000.0
2  35.0  Los Angeles   3  Charlie  60000.0
3   NaN      Chicago   4       NaN  70000.0
```

- **Explanation**: `combine_first()` fills in missing data (`NaN`) in `df1` with corresponding values from `df2`. It takes data from `df1` as the primary source and fills gaps with `df2`.

### 4. Using `join()` to Combine Datasets on Index

The `join()` method allows you to combine two datasets based on their index, which can be particularly useful when both DataFrames share the same index.

#### Example: Joining on Index

```python
# Set 'ID' as index for both DataFrames
df1 = df1.set_index('ID')
df2 = df2.set_index('ID')

# Join the two DataFrames on index
joined_df = df1.join(df2, how='outer')
print(joined_df)
```

Output:
```
       Name   Age         City   Salary
ID                                     
1     Alice  25.0          NaN      NaN
2       Bob  30.0     New York  50000.0
3   Charlie  35.0  Los Angeles  60000.0
4       NaN   NaN      Chicago  70000.0
```

- **Explanation**: The `join()` method merges `df1` and `df2` on their `ID` index. This is similar to `merge()` but aligns the data on the index by default.

### 5. Arithmetic Operations and Alignment

When performing arithmetic operations between two DataFrames or Series, Pandas automatically aligns the data based on the row and column labels. This ensures that overlapping data is correctly aligned during the operation.

#### Example: Adding Overlapping DataFrames

```python
# Overlapping DataFrames
df1 = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4, 5, 6]
}, index=['a', 'b', 'c'])

df2 = pd.DataFrame({
    'B': [7, 8, 9],
    'C': [10, 11, 12]
}, index=['b', 'c', 'd'])

# Add the two DataFrames
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

- **Explanation**: The addition operation aligns both the rows and columns of `df1` and `df2`. The common index labels (`b`, `c`) and columns (`B`) are added together, while the rest are filled with `NaN` for non-overlapping data.


- **`merge()`**: Used for database-style joins on common keys.
- **`concat()`**: Stacks or concatenates DataFrames vertically or horizontally, useful for combining datasets that may have overlapping columns.
- **`combine_first()`**: Combines overlapping datasets and fills missing data from the second dataset.
- **`join()`**: Combines datasets on their index, similar to `merge()`, but based on index alignment.
- **Arithmetic Operations**: Automatically align data based on indices when performing arithmetic operations on overlapping datasets.

These methods provide flexibility for combining and manipulating overlapping datasets in Pandas for different use cases.
#### General DataFrame combine
The `combine()` function in Pandas provides a way to combine two `DataFrame` objects element-wise, based on a custom function. It's a more flexible alternative to merging or concatenation when you want to apply specific logic on how to combine elements from overlapping datasets.

### **Syntax of `combine()`**:

```python
DataFrame.combine(other, func, fill_value=None, overwrite=True)
```

- **`other`**: The other `DataFrame` to combine with.
- **`func`**: A function that defines how to combine the two DataFrames. This function is applied element-wise, and it takes two arguments, one for each DataFrame's element.
- **`fill_value`**: If provided, it is used to fill missing values in both DataFrames.
- **`overwrite`**: If `True`, the result will overwrite elements in the first `DataFrame` where there are corresponding values in the second `DataFrame`.

### **Example of `combine()` Usage**

#### Example 1: Element-wise Maximum of Two DataFrames

You can use `combine()` to combine two DataFrames, taking the maximum value element-wise between them.

```python
import pandas as pd

# DataFrame 1
df1 = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4, 5, 6]
})

# DataFrame 2
df2 = pd.DataFrame({
    'A': [3, 2, 1],
    'B': [1, 2, 3]
})

# Combine using a function that takes the maximum of two elements
result = df1.combine(df2, lambda x, y: max(x, y))
print(result)
```

Output:
```
   A  B
0  3  4
1  2  5
2  3  6
```

- **Explanation**: The `lambda` function takes two arguments (`x` and `y`), which are corresponding elements from `df1` and `df2`, and returns the maximum value. This function is applied element-wise across the DataFrames.

#### Example 2: Filling Missing Values from Another DataFrame

You can use `combine()` to fill missing values (`NaN`) in one `DataFrame` using values from another `DataFrame`.

```python
# DataFrame 1 with missing values
df1 = pd.DataFrame({
    'A': [1, None, 3],
    'B': [4, None, 6]
})

# DataFrame 2 with values
df2 = pd.DataFrame({
    'A': [3, 2, 1],
    'B': [1, 2, 3]
})

# Fill missing values in df1 using df2
result = df1.combine(df2, lambda x, y: x if pd.notnull(x) else y)
print(result)
```

Output:
```
     A    B
0  1.0  4.0
1  2.0  2.0
2  3.0  6.0
```

- **Explanation**: The `lambda` function checks if an element in `df1` is not `NaN` (`pd.notnull(x)`). If it's not `NaN`, it takes the value from `df1`; otherwise, it takes the value from `df2`.

### **Combining with Fill Value**

You can use the `fill_value` parameter to ensure that missing values in both DataFrames are replaced with a default value before combining.

#### Example 3: Using `fill_value` in Combine

```python
# DataFrame 1 with missing values
df1 = pd.DataFrame({
    'A': [1, None, 3],
    'B': [None, 5, None]
})

# DataFrame 2 with missing values
df2 = pd.DataFrame({
    'A': [None, 2, None],
    'B': [1, None, 6]
})

# Combine with a fill_value
result = df1.combine(df2, lambda x, y: x + y, fill_value=0)
print(result)
```

Output:
```
     A    B
0  1.0  1.0
1  2.0  5.0
2  3.0  6.0
```

- **Explanation**: The `fill_value=0` ensures that any missing values (`NaN`) are replaced by `0` before the combination. The combination adds the values of `df1` and `df2` element-wise.

### **Overwrite Behavior**

By default, `combine()` will overwrite elements in the first `DataFrame` with values from the second `DataFrame` if they exist. You can change this behavior by setting `overwrite=False`.

#### Example 4: Using `overwrite=False`

```python
# DataFrame 1
df1 = pd.DataFrame({
    'A': [1, None, 3],
    'B': [None, 5, None]
})

# DataFrame 2
df2 = pd.DataFrame({
    'A': [None, 2, None],
    'B': [1, None, 6]
})

# Combine without overwriting values in df1
result = df1.combine(df2, lambda x, y: x + y, overwrite=False)
print(result)
```

Output:
```
     A    B
0  1.0  NaN
1  NaN  5.0
2  3.0  NaN
```
**Explanation**: Since `overwrite=False`, the values in `df1` are preserved, and the values from `df2` are not used to replace existing `NaN` values.


- **Element-wise Function**: You can define how to combine corresponding elements from two `DataFrames` using a custom function.
- **Handling Missing Data**: You can fill missing values in one DataFrame using another DataFrame's values.
- **Flexible Overwriting**: Control whether or not values in the first DataFrame are overwritten using `overwrite`.
- **Fill Missing Data**: Use `fill_value` to replace `NaN` values before combining.

`combine()` is a versatile method that allows you to perform custom operations to combine two `DataFrames`, especially useful when the default methods like `merge()` or `concat()` don't provide enough flexibility.
  
### Descriptive statistics

In Pandas, descriptive statistics provide insights into the distribution, central tendency, and variability of data within a DataFrame or Series. These statistics include measures like mean, median, standard deviation, minimum, maximum, percentiles, and more. Pandas offers several built-in methods to calculate descriptive statistics easily.

### **Common Descriptive Statistics Methods in Pandas**

1. **`count()`**: Number of non-null observations.
2. **`mean()`**: Mean (average) of the values.
3. **`median()`**: Median value (50th percentile).
4. **`mode()`**: Mode(s) of the data.
5. **`std()`**: Standard deviation of the values.
6. **`var()`**: Variance of the values.
7. **`min()`**: Minimum value.
8. **`max()`**: Maximum value.
9. **`sum()`**: Sum of the values.
10. **`describe()`**: Summary of statistics (count, mean, std, min, 25%, 50%, 75%, and max).
11. **`quantile()`**: Value at a given quantile.
12. **`cumsum()`**: Cumulative sum.
13. **`cumprod()`**: Cumulative product.

### **Basic Descriptive Statistics**

Let's go through some of the basic methods for calculating descriptive statistics in Pandas.

#### **Example DataFrame**

```python
import pandas as pd

# Sample DataFrame
data = {
    'A': [1, 2, 3, 4, 5],
    'B': [10, 20, 30, 40, 50],
    'C': [5, None, 15, 25, 35]
}

df = pd.DataFrame(data)
print(df)
```

Output:
```
   A   B     C
0  1  10   5.0
1  2  20   NaN
2  3  30  15.0
3  4  40  25.0
4  5  50  35.0
```

### 1. **`count()`**

The `count()` method returns the number of non-null (non-NaN) values in each column.

```python
df.count()
```

Output:
```
A    5
B    5
C    4
dtype: int64
```

- **Explanation**: Column `C` has 4 non-null values because one value is missing (`NaN`).

### 2. **`mean()`**

The `mean()` method returns the average of the values for each numeric column.

```python
df.mean()
```

Output:
```
A     3.0
B    30.0
C    20.0
dtype: float64
```

- **Explanation**: The mean is calculated for columns `A`, `B`, and `C`, ignoring missing values (`NaN`).

### 3. **`median()`**

The `median()` method returns the median (50th percentile) for each column.

```python
df.median()
```

Output:
```
A     3.0
B    30.0
C    20.0
dtype: float64
```

- **Explanation**: The median is calculated for each numeric column, ignoring missing values.

### 4. **`mode()`**

The `mode()` method returns the most frequent value(s) for each column. If there's more than one mode, it will return multiple rows.

```python
df.mode()
```

Output:
```
     A     B     C
0  1.0  10.0   5.0
```

- **Explanation**: The mode is calculated for each column. In this case, the most frequent values for columns `A`, `B`, and `C` are returned.

### 5. **`std()`**

The `std()` method returns the standard deviation for each numeric column.

```python
df.std()
```

Output:
```
A    1.581139
B   15.811388
C   12.909944
dtype: float64
```

- **Explanation**: The standard deviation is a measure of how spread out the values are from the mean.

### 6. **`min()` and `max()`**

- **`min()`**: Returns the minimum value for each column.
- **`max()`**: Returns the maximum value for each column.

```python
df.min()
```

Output:
```
A    1.0
B    10.0
C     5.0
dtype: float64
```

```python
df.max()
```

Output:
```
A     5.0
B    50.0
C    35.0
dtype: float64
```

### 7. **`sum()`**

The `sum()` method returns the sum of values for each column.

```python
df.sum()
```

Output:
```
A    15.0
B   150.0
C    80.0
dtype: float64
```

- **Explanation**: The sum is calculated for all the numeric columns.

### 8. **`describe()`**

The `describe()` method provides a summary of statistics for each numeric column, including count, mean, standard deviation, minimum, 25th percentile (Q1), median (50th percentile), 75th percentile (Q3), and maximum.

```python
df.describe()
```

Output:
```
              A          B          C
count  5.000000   5.000000   4.000000
mean   3.000000  30.000000  20.000000
std    1.581139  15.811388  12.909944
min    1.000000  10.000000   5.000000
25%    2.000000  20.000000  12.500000
50%    3.000000  30.000000  20.000000
75%    4.000000  40.000000  27.500000
max    5.000000  50.000000  35.000000
```

- **Explanation**: This method gives a quick overview of the most important descriptive statistics for each column.

### 9. **`quantile()`**

The `quantile()` method calculates the value at a given quantile (percentile). The 0.5 quantile (50th percentile) is the same as the median.

```python
df.quantile(0.75)  # 75th percentile
```

Output:
```
A     4.0
B    40.0
C    27.5
Name: 0.75, dtype: float64
```

- **Explanation**: The 75th percentile is calculated for each column.

### 10. **Cumulative Methods**: `cumsum()`, `cumprod()`

- **`cumsum()`**: Returns the cumulative sum over each column.
- **`cumprod()`**: Returns the cumulative product over each column.

#### Example: Cumulative Sum

```python
df.cumsum()
```

Output:
```
   A    B     C
0  1   10   5.0
1  3   30   NaN
2  6   60  20.0
3  10  100  45.0
4  15  150  80.0
```

- **Explanation**: The cumulative sum adds up the values over time. Missing values (`NaN`) are ignored.

### **Summary of Descriptive Statistics Methods**

| Method     | Description                                                   |
|------------|---------------------------------------------------------------|
| `count()`  | Number of non-null values                                      |
| `mean()`   | Mean of values                                                 |
| `median()` | Median of values                                               |
| `mode()`   | Mode (most frequent value)                                     |
| `std()`    | Standard deviation                                             |
| `var()`    | Variance                                                       |
| `min()`    | Minimum value                                                  |
| `max()`    | Maximum value                                                  |
| `sum()`    | Sum of values                                                  |
| `describe()`| Summary statistics (count, mean, std, min, 25%, 50%, 75%, max)|
| `quantile()`| Value at the given quantile                                   |
| `cumsum()` | Cumulative sum                                                 |
| `cumprod()`| Cumulative product                                             |

These methods provide powerful ways to get a sense of the distribution, spread, and characteristics of your data quickly.

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


































