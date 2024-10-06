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
In Pandas, applying functions to `DataFrame` or `Series` objects allows for flexible manipulation of data. There are several ways to apply functions, whether they are custom user-defined functions (UDFs) or built-in functions. Pandas provides different methods for function application, such as `apply()`, `applymap()`, and `map()`.

### **Methods of Function Application in Pandas**

1. **`apply()`**: Applies a function along an axis (rows or columns) of a `DataFrame` or `Series`.
2. **`applymap()`**: Applies a function element-wise to the entire `DataFrame`.
3. **`map()`**: Applies a function element-wise to a `Series`.

---

### 1. **`apply()`**

The `apply()` function is one of the most versatile in Pandas. It allows you to apply a custom or built-in function along an axis (rows or columns) in both `DataFrame` and `Series`.

#### **For Series**

You can use `apply()` to apply a function to each element of a Series.

```python
import pandas as pd

# Sample Series
s = pd.Series([1, 2, 3, 4, 5])

# Apply a lambda function to square each element
squared = s.apply(lambda x: x ** 2)
print(squared)
```

Output:
```
0     1
1     4
2     9
3    16
4    25
dtype: int64
```

#### **For DataFrame**

In a `DataFrame`, `apply()` allows you to apply a function either along rows (axis=1) or along columns (axis=0).

- **Applying a function to each column** (axis=0 is the default):

```python
# Sample DataFrame
df = pd.DataFrame({
    'A': [1, 2, 3, 4],
    'B': [10, 20, 30, 40]
})

# Apply a function to calculate the sum of each column
column_sum = df.apply(sum)
print(column_sum)
```

Output:
```
A     10
B    100
dtype: int64
```

- **Applying a function to each row** (axis=1):

```python
# Apply a function to calculate the sum of each row
row_sum = df.apply(lambda row: row['A'] + row['B'], axis=1)
print(row_sum)
```

Output:
```
0    11
1    22
2    33
3    44
dtype: int64
```

#### **Applying Custom Functions**

You can define your own custom functions and use them with `apply()`.

```python
# Define a custom function that adds 5 to a number
def add_five(x):
    return x + 5

# Apply the custom function to each column
df_applied = df.apply(add_five)
print(df_applied)
```

Output:
```
   A   B
0  6  15
1  7  25
2  8  35
3  9  45
```

### 2. **`applymap()`**

`applymap()` is used to apply a function element-wise to an entire `DataFrame`. Unlike `apply()`, which operates on rows or columns, `applymap()` works on each individual element.

```python
# Apply a lambda function to square each element in the DataFrame
df_squared = df.applymap(lambda x: x ** 2)
print(df_squared)
```

Output:
```
    A    B
0   1  100
1   4  400
2   9  900
3  16 1600
```

- **Explanation**: `applymap()` applies the given function (`lambda x: x ** 2`) to each individual element in the `DataFrame`, squaring each value.

### 3. **`map()`**

`map()` is used to apply a function element-wise to a `Series`. It can also be used to map values according to a dictionary, a Series, or a function.

#### **Applying a Function to a Series**

```python
# Apply a lambda function to double each element in the Series
s_mapped = s.map(lambda x: x * 2)
print(s_mapped)
```

Output:
```
0     2
1     4
2     6
3     8
4    10
dtype: int64
```

#### **Mapping Using a Dictionary**

You can also use `map()` to map values in a `Series` to new values according to a dictionary.

```python
# Mapping old values to new values using a dictionary
s_mapped_dict = s.map({1: 10, 2: 20, 3: 30})
print(s_mapped_dict)
```

Output:
```
0    10.0
1    20.0
2    30.0
3     NaN
4     NaN
dtype: float64
```

- **Explanation**: The values `1`, `2`, and `3` in the original `Series` are mapped to `10`, `20`, and `30`, respectively. Since `4` and `5` are not in the dictionary, they are mapped to `NaN`.

---

### **Function Application in Practice**

#### **Example: Applying a Conditional Function**

You can apply more complex custom functions based on conditions.

```python
# Define a custom function to label values
def categorize(x):
    if x < 20:
        return 'Low'
    elif x < 40:
        return 'Medium'
    else:
        return 'High'

# Apply the custom function to a column in the DataFrame
df['Category'] = df['B'].apply(categorize)
print(df)
```

Output:
```
   A   B Category
0  1  10      Low
1  2  20   Medium
2  3  30   Medium
3  4  40     High
```

#### **Example: Normalizing Data Across Columns**

```python
# Apply normalization to each column in the DataFrame
df_normalized = df[['A', 'B']].apply(lambda x: (x - x.min()) / (x.max() - x.min()))
print(df_normalized)
```

Output:
```
     A    B
0  0.00  0.00
1  0.33  0.33
2  0.67  0.67
3  1.00  1.00
```

- **Explanation**: This normalizes the values in columns `A` and `B` using the min-max scaling formula.

---


| Method     | Description                                      | Input              | Applies To    |
|------------|--------------------------------------------------|--------------------|---------------|
| `apply()`  | Apply function along rows (axis=1) or columns (axis=0) | Function           | DataFrame, Series |
| `applymap()` | Apply function element-wise to the entire DataFrame | Function           | DataFrame     |
| `map()`    | Map values in a Series using a function, dictionary, or Series | Function, Dictionary | Series        |

These function application methods allow you to flexibly manipulate and transform your data for various tasks such as normalization, conditional operations, and element-wise transformations.
#### Aggregation API
In Pandas, aggregation refers to the process of performing some calculation or summary statistic on data. Pandas provides an **Aggregation API** to facilitate operations like summing, counting, or averaging over data grouped by certain criteria. Aggregation can be performed on both `DataFrame` and `Series` using various methods like `groupby()`, `agg()`, or applying functions directly.

### **Common Aggregation Functions**
Some of the common functions used for aggregation include:
- **`sum()`**: Sum of values.
- **`mean()`**: Average of values.
- **`count()`**: Count of non-null values.
- **`min()`**: Minimum value.
- **`max()`**: Maximum value.
- **`std()`**: Standard deviation.
- **`var()`**: Variance.
- **`median()`**: Median value.
- **`prod()`**: Product of values.

### **1. Aggregation with `groupby()`**
The `groupby()` function is one of the most common ways to perform aggregation. It groups data based on one or more columns and allows you to apply aggregation functions on the groups.

#### **Basic Example**

```python
import pandas as pd

# Sample DataFrame
data = {
    'Category': ['A', 'B', 'A', 'B', 'A', 'B'],
    'Values': [10, 20, 30, 40, 50, 60]
}

df = pd.DataFrame(data)

# Group by 'Category' and sum the 'Values'
grouped_sum = df.groupby('Category')['Values'].sum()
print(grouped_sum)
```

Output:
```
Category
A     90
B    120
Name: Values, dtype: int64
```

- **Explanation**: The data is grouped by the `Category` column, and the sum of the `Values` for each group is calculated.

#### **Multiple Aggregations**

You can apply multiple aggregation functions using `agg()`.

```python
# Apply multiple aggregation functions to the 'Values' column
grouped_agg = df.groupby('Category')['Values'].agg(['sum', 'mean', 'count'])
print(grouped_agg)
```

Output:
```
           sum  mean  count
Category                     
A           90  30.0      3
B          120  40.0      3
```

- **Explanation**: Here, the sum, mean, and count are calculated for each group in the `Category` column.

#### **Applying Different Aggregations to Different Columns**

You can apply different aggregation functions to different columns by passing a dictionary to `agg()`.

```python
# Sample DataFrame with multiple columns
data = {
    'Category': ['A', 'B', 'A', 'B', 'A', 'B'],
    'Values': [10, 20, 30, 40, 50, 60],
    'Scores': [100, 200, 300, 400, 500, 600]
}

df = pd.DataFrame(data)

# Apply different aggregations to 'Values' and 'Scores'
grouped_multi_agg = df.groupby('Category').agg({
    'Values': 'sum',
    'Scores': ['mean', 'max']
})
print(grouped_multi_agg)
```

Output:
```
           Values Scores      
              sum  mean  max
Category                      
A              90   300  500
B             120   400  600
```

- **Explanation**: The sum is calculated for the `Values` column, while the mean and max are calculated for the `Scores` column.

### **2. Aggregation with `agg()` (Aggregation API)**

Pandas provides the `agg()` method that allows you to apply one or more functions on DataFrames or Series, regardless of whether you use `groupby()` or not.

#### **Applying Aggregations on Entire DataFrame**

You can use `agg()` directly on a `DataFrame` without using `groupby()` to apply aggregation functions across the entire DataFrame.

```python
# Apply multiple aggregation functions on the DataFrame
df_agg = df.agg({
    'Values': ['sum', 'mean'],
    'Scores': ['max', 'min']
})
print(df_agg)
```

Output:
```
       Values  Scores
sum      210.0     NaN
mean      35.0     NaN
max        NaN   600.0
min        NaN   100.0
```

- **Explanation**: Aggregations like sum and mean are applied to the `Values` column, and max and min are applied to the `Scores` column.

### **3. `transform()` vs `agg()`**

- **`agg()`**: Returns a reduced version of the data (aggregated result).
- **`transform()`**: Returns a new DataFrame or Series with the same shape as the original, where the function is applied to each group.

#### **`transform()` Example**

```python
# Transform the data using the mean of each group
df['Transformed'] = df.groupby('Category')['Values'].transform('mean')
print(df)
```

Output:
```
  Category  Values  Scores  Transformed
0        A      10     100         30.0
1        B      20     200         40.0
2        A      30     300         30.0
3        B      40     400         40.0
4        A      50     500         30.0
5        B      60     600         40.0
```

- **Explanation**: The `transform()` function applies the mean for each group in the `Category` column, and the result is added back to the original `DataFrame` with the same shape.

### **4. Aggregation with `pivot_table()`**

The `pivot_table()` function allows you to summarize data with aggregation in a more structured format, similar to Excel pivot tables.

```python
# Create a pivot table
pivot = df.pivot_table(values='Values', index='Category', aggfunc=['sum', 'mean'])
print(pivot)
```

Output:
```
           sum  mean
Category             
A           90  30.0
B          120  40.0
```

### **5. Custom Aggregation Functions**

You can apply custom functions during aggregation using `agg()`.

```python
# Define a custom function
def range_func(x):
    return x.max() - x.min()

# Apply the custom function using agg()
custom_agg = df.groupby('Category')['Values'].agg(range_func)
print(custom_agg)
```

Output:
```
Category
A    40
B    40
Name: Values, dtype: int64
```

- **Explanation**: The custom function calculates the range (max - min) for the `Values` column in each group.

---

### **Key Aggregation Methods in Pandas**

| Method             | Description                                             |
|--------------------|---------------------------------------------------------|
| `groupby()`        | Groups data based on one or more keys and applies aggregation. |
| `agg()`            | Applies one or more aggregation functions to `DataFrame` or `Series`. |
| `transform()`      | Applies a function element-wise to groups but keeps the original shape. |
| `pivot_table()`    | Creates a pivot table, summarizing data with aggregation. |
| `apply()`          | Applies a function along rows or columns (can also aggregate). |

Aggregation in Pandas is very powerful for data summarization and transformation. It’s especially useful for data analysis, enabling you to gain insights into your data quickly.



#### Transform API
The **`transform()` API** in Pandas is a powerful tool that allows you to perform element-wise transformations of a `Series` or `DataFrame`, while retaining the same shape as the original data. It is typically used with `groupby()` to apply functions to individual groups in a dataset, and the result is "broadcasted" back to the original structure.

Unlike `agg()` (which returns a reduced version of the data), `transform()` keeps the shape of the original `DataFrame` or `Series`, making it useful for creating new columns or performing operations that should align with the original data.

### **Key Features of `transform()`**
- **Same shape**: The transformed data has the same shape as the original.
- **Element-wise transformation**: It applies the function to each group independently and broadcasts the result to match the index of the original data.
- **Customizable functions**: You can use both built-in or custom functions.

### **Syntax**

```python
DataFrame.transform(func, axis=0, *args, **kwargs)
```

- **`func`**: The function to apply to the data.
- **`axis`**: Whether to apply the function along rows (axis=0) or columns (axis=1).
- **`*args` and `**kwargs`**: Additional arguments passed to the function.

---

### **Using `transform()` with GroupBy**

`transform()` is commonly used in conjunction with `groupby()` to perform transformations on groups of data. Here’s a simple example:

#### **Example: Mean of Each Group**

```python
import pandas as pd

# Sample DataFrame
df = pd.DataFrame({
    'Category': ['A', 'B', 'A', 'B', 'A', 'B'],
    'Values': [10, 20, 30, 40, 50, 60]
})

# Apply transform to calculate the mean of each group
df['Mean'] = df.groupby('Category')['Values'].transform('mean')
print(df)
```

Output:
```
  Category  Values  Mean
0        A      10  30.0
1        B      20  40.0
2        A      30  30.0
3        B      40  40.0
4        A      50  30.0
5        B      60  40.0
```

- **Explanation**: `transform('mean')` calculates the mean for each group in the `Category` column, and the result is broadcasted back to each corresponding row.

### **Comparison: `transform()` vs `agg()`**

| Feature          | `transform()`                       | `agg()`                         |
|------------------|-------------------------------------|---------------------------------|
| Shape of output  | Same as original `DataFrame`/`Series`| Aggregated/reduced version       |
| Use cases        | Element-wise operations, aligned with the original data | Summarization, reduced results   |
| Result           | Transformed values for each group   | One result per group            |

### **Common Use Cases**

#### 1. **Standardizing Data (Z-Score)**

```python
# Calculate the Z-score for each value in its respective group
df['Z-Score'] = df.groupby('Category')['Values'].transform(lambda x: (x - x.mean()) / x.std())
print(df)
```

Output:
```
  Category  Values  Z-Score
0        A      10 -0.92582
1        B      20 -1.00000
2        A      30  0.00000
3        B      40  0.00000
4        A      50  0.92582
5        B      60  1.00000
```

- **Explanation**: The Z-score standardizes the data within each group by subtracting the mean and dividing by the standard deviation.

#### 2. **Filling Missing Values by Group**

```python
# Create a DataFrame with missing values
df_nan = pd.DataFrame({
    'Category': ['A', 'B', 'A', 'B', 'A', 'B'],
    'Values': [10, None, 30, None, 50, 60]
})

# Fill missing values with the mean of each group
df_nan['Filled'] = df_nan.groupby('Category')['Values'].transform(lambda x: x.fillna(x.mean()))
print(df_nan)
```

Output:
```
  Category  Values  Filled
0        A     10.0    10.0
1        B      NaN    60.0
2        A     30.0    30.0
3        B      NaN    60.0
4        A     50.0    50.0
5        B     60.0    60.0
```

- **Explanation**: Missing values in the `Values` column are filled with the mean of the respective groups.

#### 3. **Ranking Within Groups**

You can use `transform()` to rank values within each group.

```python
# Rank the values within each group
df['Rank'] = df.groupby('Category')['Values'].transform('rank')
print(df)
```

Output:
```
  Category  Values  Rank
0        A      10   1.0
1        B      20   1.0
2        A      30   2.0
3        B      40   2.0
4        A      50   3.0
5        B      60   3.0
```

- **Explanation**: The `Values` column is ranked within each group of the `Category` column.

### **Applying Custom Functions**

You can define your own custom functions and use them with `transform()`.

#### Example: Custom Transformation Function

```python
# Define a custom function to multiply by 2
def custom_function(x):
    return x * 2

# Apply the custom function to the 'Values' column
df['Transformed'] = df.groupby('Category')['Values'].transform(custom_function)
print(df)
```

Output:
```
  Category  Values  Transformed
0        A      10          20
1        B      20          40
2        A      30          60
3        B      40          80
4        A      50         100
5        B      60         120
```

- **Explanation**: Each value in the `Values` column is multiplied by 2 within its group.

---

### **Summary of `transform()` Key Concepts**

- **Retains Shape**: Unlike aggregation, `transform()` does not reduce the data size; it applies the transformation element-wise.
- **Used with `groupby()`**: Frequently used with `groupby()` to apply transformations across groups.
- **Broadcasting**: Results are broadcasted to align with the original data structure, making it useful for adding new columns.
- **Custom Functions**: Can be used with both built-in functions (`mean`, `rank`, etc.) and custom-defined functions.

### **Typical Use Cases for `transform()`**

- **Standardization**: Standardizing data within groups (e.g., Z-score normalization).
- **Missing Value Handling**: Filling missing values within groups.
- **Ranking**: Ranking elements within groups.
- **Smoothing/Transforming Data**: Applying custom smoothing or transformation functions while maintaining the original shape.

The `transform()` method is especially helpful when you need to compute group-wise operations without losing the original structure of the data, making it perfect for tasks like feature engineering in machine learning workflows.


### Reindexing and altering labels
Reindexing and altering labels in Pandas allows you to change the row and column labels (indexes) of a `DataFrame` or `Series`. This is a powerful feature when you need to modify the structure of your data, align it with another dataset, or rename the row/column labels for clarity.

### **1. Reindexing**
Reindexing allows you to change the labels (indices) of the rows and columns. If the new labels don’t match the existing ones, missing values (`NaN`) will be introduced.

#### **Reindexing a `Series`**

```python
import pandas as pd

# Create a Series
s = pd.Series([1, 2, 3], index=['a', 'b', 'c'])

# Reindex the Series
s_reindexed = s.reindex(['a', 'b', 'd', 'e'])
print(s_reindexed)
```

Output:
```
a    1.0
b    2.0
d    NaN
e    NaN
dtype: float64
```

- **Explanation**: The Series is reindexed to a new list `['a', 'b', 'd', 'e']`. Since `'d'` and `'e'` were not in the original index, missing values (`NaN`) are introduced.

#### **Reindexing a `DataFrame`**

```python
# Create a DataFrame
df = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4, 5, 6]
}, index=['a', 'b', 'c'])

# Reindex the DataFrame
df_reindexed = df.reindex(['a', 'b', 'd'])
print(df_reindexed)
```

Output:
```
     A    B
a  1.0  4.0
b  2.0  5.0
d  NaN  NaN
```

- **Explanation**: The DataFrame is reindexed, and missing values are introduced for the new index `'d'`.

### **Reindexing with `fill_value`**
You can fill missing values introduced by reindexing with a specific value using the `fill_value` parameter.

```python
# Reindex and fill missing values with 0
df_filled = df.reindex(['a', 'b', 'd'], fill_value=0)
print(df_filled)
```

Output:
```
     A  B
a  1.0  4
b  2.0  5
d  0.0  0
```

- **Explanation**: Missing values introduced by reindexing are filled with `0`.

### **Reindexing Columns**
You can reindex columns just like rows.

```python
# Reindex columns
df_columns_reindexed = df.reindex(columns=['A', 'C'])
print(df_columns_reindexed)
```

Output:
```
     A   C
a  1.0 NaN
b  2.0 NaN
c  3.0 NaN
```

- **Explanation**: The `C` column did not exist in the original DataFrame, so `NaN` values are introduced.

### **Reindexing with `method` (Forward or Backward Fill)**
You can use the `method` parameter to fill missing values with forward-fill (`ffill`) or backward-fill (`bfill`).

```python
# Reindex and forward-fill missing values
df_ffill = df.reindex(['a', 'b', 'd'], method='ffill')
print(df_ffill)
```

Output:
```
     A  B
a  1.0  4
b  2.0  5
d  2.0  5
```

- **Explanation**: The missing row for `'d'` is filled using the forward-fill method, which propagates the previous value.

---

### **2. Altering Labels**

Pandas provides various methods to rename or alter the row and column labels of a `DataFrame` or `Series`.

#### **Renaming Labels with `rename()`**
The `rename()` function allows you to alter row and column labels in a flexible way.

```python
# Rename the row labels
df_renamed = df.rename(index={'a': 'alpha', 'b': 'beta'})
print(df_renamed)
```

Output:
```
       A  B
alpha  1  4
beta   2  5
c      3  6
```

- **Explanation**: The row labels `'a'` and `'b'` are renamed to `'alpha'` and `'beta'`.

#### **Renaming Columns**

```python
# Rename the columns
df_columns_renamed = df.rename(columns={'A': 'Column1', 'B': 'Column2'})
print(df_columns_renamed)
```

Output:
```
   Column1  Column2
a        1        4
b        2        5
c        3        6
```

- **Explanation**: The columns `'A'` and `'B'` are renamed to `'Column1'` and `'Column2'`.

#### **Renaming Using a Function**
You can also pass a function to `rename()` to apply transformations to the labels.

```python
# Rename the row labels using a function
df_func_renamed = df.rename(index=str.upper)
print(df_func_renamed)
```

Output:
```
   A  B
A  1  4
B  2  5
C  3  6
```

- **Explanation**: The row labels are converted to uppercase using the `str.upper` function.

---

### **3. Resetting Index**
The `reset_index()` method is used to reset the index of the `DataFrame` back to the default integer index. This is useful when you want to discard the current index and convert it into a column.

```python
# Reset the index
df_reset = df.reset_index()
print(df_reset)
```

Output:
```
  index  A  B
0     a  1  4
1     b  2  5
2     c  3  6
```

- **Explanation**: The current index is turned into a column, and the default integer index is restored.

#### **Dropping the Old Index**
You can use the `drop=True` option in `reset_index()` if you don’t want to retain the old index as a column.

```python
# Reset index and drop the old index
df_reset_dropped = df.reset_index(drop=True)
print(df_reset_dropped)
```

Output:
```
   A  B
0  1  4
1  2  5
2  3  6
```

- **Explanation**: The old index is discarded, and the DataFrame is reindexed from `0`.

---

### **4. Setting Index**
The `set_index()` method allows you to set a column (or multiple columns) as the index of the `DataFrame`.

```python
# Set the 'A' column as the index
df_set_index = df.set_index('A')
print(df_set_index)
```

Output:
```
   B
A   
1  4
2  5
3  6
```

- **Explanation**: The `A` column is set as the index.

### **Setting Multiple Indexes**

```python
# Create a DataFrame with multiple columns
df_multi = pd.DataFrame({
    'City': ['New York', 'Los Angeles', 'Chicago'],
    'Year': [2020, 2021, 2020],
    'Population': [8.3, 3.9, 2.7]
})

# Set multiple columns as index
df_multi_index = df_multi.set_index(['City', 'Year'])
print(df_multi_index)
```

Output:
```
                    Population
City        Year              
New York    2020          8.3
Los Angeles 2021          3.9
Chicago     2020          2.7
```

- **Explanation**: Both `City` and `Year` columns are used as a hierarchical index.

---


- **Reindexing**: Change row and column labels. Missing labels introduce `NaN`. You can fill missing values or use methods like `ffill`.
- **Altering Labels**: Use `rename()` to rename row and column labels. You can rename directly with a dictionary or apply functions.
- **Resetting Index**: Restore the default integer index and optionally keep or drop the old index.
- **Setting Index**: Set one or more columns as the index, which is useful for organizing data.

Reindexing and altering labels are essential for data cleaning and preparation in Pandas, enabling you to reshape your data structure to suit analysis requirements.


### Iteration  
Iteration in pandas allows you to loop through the rows or columns of a `DataFrame` or `Series`. However, unlike traditional Python objects, Pandas is optimized for vectorized operations, which are much faster than explicit iteration. Therefore, iterating over DataFrames or Series is generally not recommended for large datasets. When necessary, though, Pandas provides a number of methods to iterate over rows and columns.

Here are the most commonly used methods for iteration in Pandas:

### **1. Iterating over Rows**

#### **Using `iterrows()`**
- **`iterrows()`** generates an iterator that returns each row as a tuple of the index and the row as a `Series`. 
- The index represents the row label, and the `Series` contains the values in that row.

```python
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
})

# Iterate over rows
for index, row in df.iterrows():
    print(f"Index: {index}")
    print(f"Name: {row['Name']}, Age: {row['Age']}, City: {row['City']}")
```

Output:
```
Index: 0
Name: Alice, Age: 25, City: New York
Index: 1
Name: Bob, Age: 30, City: Los Angeles
Index: 2
Name: Charlie, Age: 35, City: Chicago
```

- **Pros**: Easy to use, readable.
- **Cons**: `iterrows()` is slow, especially for large DataFrames, as it returns a copy of each row, not a reference.

#### **Using `itertuples()`**
- **`itertuples()`** is faster than `iterrows()` because it returns rows as namedtuples, which are more efficient and allow for attribute-style access (`row.Name` instead of `row['Name']`).

```python
# Iterate using itertuples
for row in df.itertuples():
    print(f"Index: {row.Index}, Name: {row.Name}, Age: {row.Age}, City: {row.City}")
```

Output:
```
Index: 0, Name: Alice, Age: 25, City: New York
Index: 1, Name: Bob, Age: 30, City: Los Angeles
Index: 2, Name: Charlie, Age: 35, City: Chicago
```

- **Pros**: Faster than `iterrows()`, attributes are easily accessible.
- **Cons**: Doesn’t handle non-string column names well (e.g., column names with spaces).

#### **Using `apply()`**
- **`apply()`** allows you to apply a function along the axis of a DataFrame (rows or columns). This is a vectorized approach and much faster than explicit iteration.

```python
# Define a function to process rows
def process_row(row):
    return f"{row['Name']} is {row['Age']} years old and lives in {row['City']}."

# Apply the function to each row
df['Description'] = df.apply(process_row, axis=1)
print(df)
```

Output:
```
      Name  Age         City                           Description
0    Alice   25     New York    Alice is 25 years old and lives in New York.
1      Bob   30  Los Angeles  Bob is 30 years old and lives in Los Angeles.
2  Charlie   35      Chicago   Charlie is 35 years old and lives in Chicago.
```

- **Pros**: Fast, vectorized, suitable for more complex row-wise operations.
- **Cons**: May not be intuitive for simple iteration tasks.

### **2. Iterating over Columns**

You can iterate over columns in a `DataFrame` in several ways:

#### **Using `iteritems()`**
- **`iteritems()`** generates an iterator that yields column names and the corresponding data as a `Series`.

```python
# Iterate over columns
for col_name, col_data in df.iteritems():
    print(f"Column: {col_name}")
    print(col_data)
```

Output:
```
Column: Name
0      Alice
1        Bob
2    Charlie
Name: Name, dtype: object
Column: Age
0    25
1    30
2    35
Name: Age, dtype: int64
Column: City
0       New York
1    Los Angeles
2       Chicago
Name: City, dtype: object
```

- **Pros**: Simple, easy to understand.
- **Cons**: Iterating over columns is not very common, as most operations can be done with vectorized methods.

#### **Using `apply()` on Columns**
You can use the `apply()` function to apply a function to each column.

```python
# Apply a function to each column
df_col_sum = df[['Age']].apply(sum)
print(df_col_sum)
```

Output:
```
Age    90
dtype: int64
```

- **Pros**: Vectorized, fast.
- **Cons**: More suitable for applying transformations rather than simple iteration.

### **3. Iterating Over Cells**

If you need to iterate over individual cells, you can use `iterrows()` or `itertuples()` along with column access, but it’s generally better to avoid this for performance reasons.

#### **Using Nested Loops**
You can combine the `iterrows()` or `itertuples()` methods with a loop over column names to access each individual cell.

```python
# Iterate over rows and columns
for index, row in df.iterrows():
    for col in df.columns:
        print(f"Row {index}, Column {col}: {row[col]}")
```

- **Pros**: Flexible, easy to implement.
- **Cons**: Very slow for large DataFrames.

### **4. Vectorized Operations (Preferred Over Iteration)**

Instead of iterating explicitly, you should use vectorized operations, which are much faster in Pandas. For example, adding a constant to a column:

```python
# Add 5 to each value in the 'Age' column (vectorized operation)
df['Age'] = df['Age'] + 5
print(df)
```

Output:
```
      Name  Age         City
0    Alice   30     New York
1      Bob   35  Los Angeles
2  Charlie   40      Chicago
```

- **Pros**: Much faster, takes advantage of underlying NumPy optimizations.
- **Cons**: Less intuitive than simple Python loops for beginners, but critical for performance with large datasets.

### **Summary of Iteration Methods**

| Method         | Iterates Over | Pros                                             | Cons                                           |
|----------------|---------------|--------------------------------------------------|------------------------------------------------|
| `iterrows()`   | Rows          | Easy to use, returns index and Series            | Slow, returns a copy of each row               |
| `itertuples()` | Rows          | Faster, returns namedtuple                       | Non-string column names may cause issues       |
| `iteritems()`  | Columns       | Simple, returns column name and Series           | Not very common, slow for large DataFrames     |
| `apply()`      | Rows/Columns  | Vectorized, fast, flexible                       | Takes more time to understand for beginners    |
| Vectorized Ops | Cells         | Extremely fast, utilizes Pandas/NumPy optimizations | Not always intuitive, requires a different mindset|


- **Avoid explicit iteration** unless necessary. Use vectorized operations like `apply()`, which are optimized for performance.
- **`iterrows()` and `itertuples()`** are common for small datasets or when you need to perform row-wise operations.
- **`apply()`** is ideal for applying a function across rows or columns in a more efficient manner.
- **Vectorized operations** should be your go-to approach for performance-critical tasks, especially with large datasets.

### .dt accessor
The `.dt` accessor in pandas is a powerful tool for handling date and time data. It allows you to access various properties and methods for `datetime`-like objects in a `Series`. The `.dt` accessor provides convenient access to datetime-related attributes such as day, month, year, weekday, and time-specific properties like hour, minute, and second, as well as methods like `floor()`, `ceil()`, and `strftime()` for formatting datetime values.

The `.dt` accessor can only be used with `Series` or `DataFrame` columns that contain datetime-like values, such as `datetime64`, `timedelta64`, or `Period` dtype.

### **1. Basic Usage of `.dt` Accessor**

#### **Converting to Datetime**
Before using `.dt`, ensure that your data is in a `datetime` format. You can convert strings to `datetime` using `pd.to_datetime()`.

```python
import pandas as pd

# Create a DataFrame with date strings
df = pd.DataFrame({
    'date': ['2023-01-01', '2023-02-14', '2023-03-31']
})

# Convert to datetime
df['date'] = pd.to_datetime(df['date'])

print(df)
```

Output:
```
        date
0 2023-01-01
1 2023-02-14
2 2023-03-31
```

#### **Accessing Year, Month, Day, etc.**
Once the column is in datetime format, you can use `.dt` to extract specific parts of the datetime.

```python
# Extract year, month, and day using .dt
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
df['day'] = df['date'].dt.day

print(df)
```

Output:
```
        date  year  month  day
0 2023-01-01  2023      1    1
1 2023-02-14  2023      2   14
2 2023-03-31  2023      3   31
```

- **`.dt.year`**: Extracts the year.
- **`.dt.month`**: Extracts the month.
- **`.dt.day`**: Extracts the day.

### **2. Extracting Time Components**

If your data contains both date and time information, you can use the `.dt` accessor to extract the time components such as hour, minute, and second.

```python
# Create a DataFrame with datetime strings including time
df = pd.DataFrame({
    'datetime': ['2023-01-01 08:30:00', '2023-02-14 12:45:00', '2023-03-31 18:15:00']
})

# Convert to datetime
df['datetime'] = pd.to_datetime(df['datetime'])

# Extract time components
df['hour'] = df['datetime'].dt.hour
df['minute'] = df['datetime'].dt.minute
df['second'] = df['datetime'].dt.second

print(df)
```

Output:
```
             datetime  hour  minute  second
0 2023-01-01 08:30:00     8      30       0
1 2023-02-14 12:45:00    12      45       0
2 2023-03-31 18:15:00    18      15       0
```

- **`.dt.hour`**: Extracts the hour.
- **`.dt.minute`**: Extracts the minute.
- **`.dt.second`**: Extracts the second.

### **3. Accessing Date Properties**

You can also use `.dt` to extract other date-related properties such as day of the week, quarter, and whether a date is the beginning or end of a month, quarter, or year.

```python
# Extract additional date-related properties
df['day_of_week'] = df['datetime'].dt.dayofweek   # 0 = Monday, 6 = Sunday
df['day_name'] = df['datetime'].dt.day_name()     # Returns the name of the day
df['quarter'] = df['datetime'].dt.quarter         # Extract quarter of the year
df['is_month_start'] = df['datetime'].dt.is_month_start  # Is the date the start of the month?
df['is_month_end'] = df['datetime'].dt.is_month_end      # Is the date the end of the month?

print(df)
```

Output:
```
             datetime  day_of_week   day_name  quarter  is_month_start  is_month_end
0 2023-01-01 08:30:00            6     Sunday        1            True         False
1 2023-02-14 12:45:00            1    Tuesday        1           False         False
2 2023-03-31 18:15:00            4    Friday        1           False          True
```

- **`.dt.dayofweek`**: Returns the day of the week (Monday=0, Sunday=6).
- **`.dt.day_name()`**: Returns the name of the day (e.g., 'Monday', 'Tuesday').
- **`.dt.quarter`**: Returns the quarter of the year (1, 2, 3, or 4).
- **`.dt.is_month_start`**: Returns `True` if the date is the first day of the month.
- **`.dt.is_month_end`**: Returns `True` if the date is the last day of the month.

### **4. Time Differences (Timedelta)**

When working with durations or differences between datetime values, you can use the `.dt` accessor on `timedelta` objects.

```python
# Create a DataFrame with time differences
df = pd.DataFrame({
    'start': ['2023-01-01 08:00:00', '2023-02-14 09:30:00'],
    'end': ['2023-01-01 12:00:00', '2023-02-14 11:45:00']
})

# Convert to datetime
df['start'] = pd.to_datetime(df['start'])
df['end'] = pd.to_datetime(df['end'])

# Calculate time difference
df['duration'] = df['end'] - df['start']

# Extract time difference components
df['hours'] = df['duration'].dt.total_seconds() / 3600
df['minutes'] = df['duration'].dt.total_seconds() / 60

print(df)
```

Output:
```
                start                 end     duration     hours    minutes
0 2023-01-01 08:00:00 2023-01-01 12:00:00  0 days 04:00:00  4.000000   240.0
1 2023-02-14 09:30:00 2023-02-14 11:45:00  0 days 02:15:00  2.250000   135.0
```

- **`.dt.total_seconds()`**: Returns the total duration in seconds.
- **`.dt.days`, `.dt.seconds`, `.dt.microseconds`**: Extract days, seconds, or microseconds from a `Timedelta` object.

### **5. Rounding, Flooring, and Ceiling with `.dt`**

You can use the `.dt` accessor to round, floor, or ceil datetime values to a specific frequency.

```python
# Create a DataFrame with datetime values
df = pd.DataFrame({
    'datetime': pd.to_datetime(['2023-01-01 12:34:56', '2023-02-14 09:10:15'])
})

# Floor, ceil, and round the datetime values to the nearest hour
df['floor'] = df['datetime'].dt.floor('H')
df['ceil'] = df['datetime'].dt.ceil('H')
df['round'] = df['datetime'].dt.round('H')

print(df)
```

Output:
```
             datetime               floor                ceil               round
0 2023-01-01 12:34:56 2023-01-01 12:00:00 2023-01-01 13:00:00 2023-01-01 13:00:00
1 2023-02-14 09:10:15 2023-02-14 09:00:00 2023-02-14 10:00:00 2023-02-14 09:00:00
```

- **`.dt.floor('H')`**: Rounds down to the nearest hour.
- **`.dt.ceil('H')`**: Rounds up to the nearest hour.
- **`.dt.round('H')`**: Rounds to the nearest hour.

### **6. Formatting with `.dt.strftime()`**

You can format datetime values as strings using `.dt.strftime()`, which works similarly to Python's `strftime()` function.

```python
# Format the datetime values as strings
df['formatted'] = df['datetime'].dt.strftime('%Y-%m-%d %H:%M:%S')

print(df)
```

Output:
```
             datetime           formatted
0 2023-01-01 12:34:56  2023-01-01 12:34:56
```

### Vectorized string methods

Pandas provides a set of vectorized string methods through the `.str` accessor, allowing for efficient operations on Series or DataFrame columns containing text data. These methods are applied element-wise to the string values in the Series, which makes them much faster than using Python loops for string manipulation.

### **Commonly Used Vectorized String Methods**

Here are some common string operations that can be performed using the `.str` accessor:

### **1. String Case Conversion**

- **`str.lower()`**: Converts all characters in the string to lowercase.
- **`str.upper()`**: Converts all characters in the string to uppercase.
- **`str.title()`**: Converts the first character of each word to uppercase and the rest to lowercase.
- **`str.capitalize()`**: Converts the first character of the string to uppercase and the rest to lowercase.

```python
import pandas as pd

# Create a Series with text data
s = pd.Series(['Hello', 'World', 'Python', 'Pandas'])

# Convert to lowercase
print(s.str.lower())

# Convert to uppercase
print(s.str.upper())

# Convert to title case
print(s.str.title())

# Capitalize the first character
print(s.str.capitalize())
```

### **2. String Length**

- **`str.len()`**: Returns the length of each string in the Series.

```python
# Get the length of each string
print(s.str.len())
```

### **3. Substring and Slicing**

- **`str.slice()`**: Allows slicing of each string in the Series (similar to Python string slicing).
- **`str.get()`**: Accesses a single character at a given position.

```python
# Slice first 3 characters from each string
print(s.str.slice(0, 3))

# Access the first character of each string
print(s.str.get(0))
```

### **4. Checking for Substrings**

- **`str.contains()`**: Checks if a substring is present in each string.
- **`str.startswith()`**: Checks if each string starts with a specific substring.
- **`str.endswith()`**: Checks if each string ends with a specific substring.

```python
# Check if strings contain the substring 'Py'
print(s.str.contains('Py'))

# Check if strings start with 'P'
print(s.str.startswith('P'))

# Check if strings end with 'd'
print(s.str.endswith('d'))
```

### **5. String Replacement**

- **`str.replace()`**: Replaces occurrences of a substring with another substring.

```python
# Replace 'Pandas' with 'DataFrame'
print(s.str.replace('Pandas', 'DataFrame'))
```

### **6. Removing Leading/Trailing Characters**

- **`str.strip()`**: Removes leading and trailing whitespace (or specific characters).
- **`str.lstrip()`**: Removes leading characters.
- **`str.rstrip()`**: Removes trailing characters.

```python
s_with_spaces = pd.Series(['  Hello  ', '  World  ', '  Pandas  '])

# Strip leading and trailing spaces
print(s_with_spaces.str.strip())

# Strip only leading spaces
print(s_with_spaces.str.lstrip())

# Strip only trailing spaces
print(s_with_spaces.str.rstrip())
```

### **7. Splitting and Joining Strings**

- **`str.split()`**: Splits each string in the Series by a delimiter.
- **`str.join()`**: Joins elements of a list or Series into a single string, with a given separator.

```python
# Split strings by whitespace
print(s.str.split())

# Split by a specific character (e.g., 'o')
print(s.str.split('o'))

# Join elements of a Series with a separator
s_words = pd.Series([['Hello', 'World'], ['Python', 'Pandas']])
print(s_words.str.join(' '))
```

### **8. Extracting Substrings with Regular Expressions**

- **`str.extract()`**: Extracts substrings that match a regular expression.
- **`str.findall()`**: Finds all occurrences of a pattern.

```python
# Extract numbers from strings
s_with_nums = pd.Series(['a1', 'b2', 'c3'])
print(s_with_nums.str.extract('(\d)'))

# Find all lowercase letters
s_with_multiple_matches = pd.Series(['abc123def', 'ghi456jkl'])
print(s_with_multiple_matches.str.findall('[a-z]+'))
```

### **9. String Concatenation**

- **`str.cat()`**: Concatenates strings in a Series with a specified separator.

```python
# Concatenate strings with a space separator
s1 = pd.Series(['Hello', 'Goodbye'])
s2 = pd.Series(['World', 'Everyone'])
print(s1.str.cat(s2, sep=' '))
```

### **10. Repeating Strings**

- **`str.repeat()`**: Repeats each string a specified number of times.

```python
# Repeat each string 2 times
print(s.str.repeat(2))
```

### **11. Detecting String Patterns**

- **`str.match()`**: Determines if strings match a given regular expression pattern.
- **`str.count()`**: Counts occurrences of a pattern in each string.

```python
# Check if strings match a pattern (e.g., start with an uppercase letter)
print(s.str.match('^[A-Z]'))

# Count occurrences of a specific character (e.g., 'o')
print(s.str.count('o'))
```

### **12. Handling Missing Values**

- **`str.isna()`**: Detects missing values (i.e., NaN).
- **`str.fillna()`**: Fills missing values with a specified string.

```python
s_with_nan = pd.Series(['Hello', None, 'Pandas'])
# Check for missing values
print(s_with_nan.str.isna())

# Fill missing values
print(s_with_nan.str.fillna('Missing'))
```

### **Summary Table of Common String Methods**

| Method              | Description                                            |
|---------------------|--------------------------------------------------------|
| `str.lower()`       | Convert strings to lowercase                           |
| `str.upper()`       | Convert strings to uppercase                           |
| `str.len()`         | Return length of each string                           |
| `str.contains()`    | Check if substring is present                          |
| `str.startswith()`  | Check if strings start with a substring                |
| `str.endswith()`    | Check if strings end with a substring                  |
| `str.replace()`     | Replace occurrences of a substring                     |
| `str.split()`       | Split strings by a delimiter                           |
| `str.join()`        | Join elements of a list into a string                  |
| `str.extract()`     | Extract substrings using a regular expression          |
| `str.cat()`         | Concatenate strings with a separator                   |
| `str.repeat()`      | Repeat each string a specified number of times         |
| `str.count()`       | Count occurrences of a substring                       |
| `str.strip()`       | Remove leading/trailing whitespace (or specific chars) |
| `str.isna()`        | Detect missing values                                  |
| `str.fillna()`      | Fill missing values with a specified string            |

These vectorized string methods allow for fast and efficient manipulation of text data in pandas, making it easy to clean, format, and analyze large datasets containing strings.


### Sorting
Sorting in pandas is a straightforward yet essential operation for organizing your data in a specific order. You can sort data in a `DataFrame` or `Series` by one or more columns, either in ascending or descending order. Below are details on how to use sorting methods effectively in pandas.

### **1. Sorting a Series**

To sort a `Series`, you can use the `sort_values()` method. This method sorts the values in the Series and returns a new sorted Series.

#### **Example: Sorting a Series**

```python
import pandas as pd

# Create a Series
s = pd.Series([3, 1, 4, 1, 5, 9, 2, 6, 5])

# Sort the Series in ascending order
sorted_s = s.sort_values()

print(sorted_s)
```

Output:
```
1    1
3    1
0    3
2    4
6    5
4    5
7    6
5    9
dtype: int64
```

### **2. Sorting a DataFrame**

To sort a `DataFrame`, you can also use the `sort_values()` method. You can specify one or more columns to sort by, as well as the sort order (ascending or descending).

#### **Example: Sorting a DataFrame by One Column**

```python
# Create a DataFrame
df = pd.DataFrame({
    'A': [3, 1, 4, 1, 5],
    'B': ['dog', 'cat', 'bird', 'ant', 'elephant']
})

# Sort the DataFrame by column 'A' in ascending order
sorted_df = df.sort_values(by='A')

print(sorted_df)
```

Output:
```
   A        B
1  1      cat
3  1      ant
0  3      dog
2  4     bird
4  5  elephant
```

### **3. Sorting by Multiple Columns**

You can also sort a `DataFrame` by multiple columns by passing a list of column names to the `by` parameter. The order of the columns in the list determines the sorting priority.

#### **Example: Sorting by Multiple Columns**

```python
# Create a DataFrame with multiple columns
df = pd.DataFrame({
    'A': [3, 1, 4, 1, 5],
    'B': ['dog', 'cat', 'bird', 'ant', 'elephant'],
    'C': [2, 2, 1, 1, 0]
})

# Sort by column 'A' first, then by column 'C'
sorted_df_multi = df.sort_values(by=['A', 'C'])

print(sorted_df_multi)
```

Output:
```
   A        B  C
1  1      cat  2
3  1      ant  1
0  3      dog  2
2  4     bird  1
4  5  elephant  0
```

### **4. Sorting Order**

You can specify the sorting order for each column using the `ascending` parameter. This parameter can take a single boolean value (for all columns) or a list of boolean values (for individual column sorting).

#### **Example: Specifying Sorting Order**

```python
# Sort 'A' in ascending order and 'B' in descending order
sorted_df_order = df.sort_values(by=['A', 'B'], ascending=[True, False])

print(sorted_df_order)
```

Output:
```
   A        B  C
1  1      cat  2
3  1      ant  1
0  3      dog  2
2  4     bird  1
4  5  elephant  0
```

### **5. Sorting by Index**

If you want to sort a DataFrame by its index, you can use the `sort_index()` method.

#### **Example: Sorting by Index**

```python
# Create a DataFrame with a custom index
df_indexed = pd.DataFrame({
    'A': [3, 1, 4, 1, 5],
    'B': ['dog', 'cat', 'bird', 'ant', 'elephant']
}, index=['C', 'B', 'D', 'A', 'E'])

# Sort the DataFrame by index
sorted_df_index = df_indexed.sort_index()

print(sorted_df_index)
```

Output:
```
   A        B
A  1      ant
B  1      cat
C  3      dog
D  4     bird
E  5  elephant
```

### **6. In-Place Sorting**

You can sort the DataFrame in place by setting the `inplace` parameter to `True`. This modifies the original DataFrame rather than returning a new one.

#### **Example: In-Place Sorting**

```python
# Create a DataFrame
df_inplace = pd.DataFrame({
    'A': [3, 1, 4, 1, 5],
    'B': ['dog', 'cat', 'bird', 'ant', 'elephant']
})

# Sort the DataFrame by column 'A' in place
df_inplace.sort_values(by='A', inplace=True)

print(df_inplace)
```

Output:
```
   A        B
1  1      cat
3  1      ant
0  3      dog
2  4     bird
4  5  elephant
```

### **7. Handling Missing Values**

By default, missing values (NaNs) are sorted to the end of the sorted DataFrame. You can control this behavior using the `na_position` parameter, which can be set to `'first'` or `'last'`.

#### **Example: Sorting with Missing Values**

```python
# Create a DataFrame with NaN values
df_with_nan = pd.DataFrame({
    'A': [3, 1, 4, None, 5],
    'B': ['dog', 'cat', 'bird', 'ant', 'elephant']
})

# Sort the DataFrame by column 'A', placing NaNs first
sorted_nan_first = df_with_nan.sort_values(by='A', na_position='first')

print(sorted_nan_first)
```

Output:
```
     A        B
3  NaN      ant
1  1.0      cat
0  3.0      dog
2  4.0     bird
4  5.0  elephant
```



| Method                   | Description                                                  |
|--------------------------|--------------------------------------------------------------|
| `sort_values()`          | Sort a Series or DataFrame by values in one or more columns |
| `sort_index()`           | Sort a DataFrame by its index                               |
| `ascending`              | Specify the sort order (True for ascending, False for descending) |
| `inplace`                | Sort in place without returning a new DataFrame             |
| `na_position`            | Specify where to place NaN values ('first' or 'last')       |

Sorting is a powerful tool in pandas that enables efficient organization of your data for further analysis. By utilizing the sorting methods and parameters effectively, you can quickly find and present your data in the desired order.


### Copying
Copying in pandas is an essential operation that allows you to create a new object (such as a DataFrame or Series) that is a duplicate of an existing one. This is particularly important when you want to make modifications to a DataFrame or Series without affecting the original data.

### **1. Shallow vs. Deep Copy**

- **Shallow Copy**: This creates a new object, but it does not create copies of the objects that the original object references. Thus, modifications to the data in the copied object may also affect the original object.
  
- **Deep Copy**: This creates a new object and recursively copies all objects found in the original. Changes to the data in the copied object do not affect the original.

### **2. Copying a DataFrame or Series**

In pandas, you can copy a DataFrame or Series using the `.copy()` method. By default, `.copy()` performs a deep copy, but you can also create a shallow copy if needed.

#### **Example: Creating a DataFrame**

```python
import pandas as pd

# Create a DataFrame
df_original = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4, 5, 6]
})

print("Original DataFrame:")
print(df_original)
```

### **3. Creating a Deep Copy**

```python
# Create a deep copy of the DataFrame
df_deep_copy = df_original.copy()

# Modify the copy
df_deep_copy.loc[0, 'A'] = 10

print("\nDeep Copy DataFrame (Modified):")
print(df_deep_copy)

print("\nOriginal DataFrame After Deep Copy Modification:")
print(df_original)
```

#### **Output**
```
Original DataFrame:
   A  B
0  1  4
1  2  5
2  3  6

Deep Copy DataFrame (Modified):
    A  B
0  10  4
1   2  5
2   3  6

Original DataFrame After Deep Copy Modification:
   A  B
0  1  4
1  2  5
2  3  6
```

### **4. Creating a Shallow Copy**

You can create a shallow copy by passing `deep=False` to the `.copy()` method. Changes to mutable objects in the shallow copy will reflect in the original.

```python
# Create a shallow copy of the DataFrame
df_shallow_copy = df_original.copy(deep=False)

# Modify the original DataFrame
df_original.loc[0, 'A'] = 10

print("\nShallow Copy DataFrame:")
print(df_shallow_copy)

print("\nOriginal DataFrame After Shallow Copy Modification:")
print(df_original)
```

#### **Output**
```
Shallow Copy DataFrame:
   A  B
0  10  4
1   2  5
2   3  6

Original DataFrame After Shallow Copy Modification:
   A  B
0  10  4
1   2  5
2   3  6
```

### **5. Copying with Index and Columns**

When you create a copy, you can also choose to copy the index and columns separately by setting `copy=True` for them.

```python
# Create a new DataFrame with specific index and column copying
df_custom_copy = df_original.copy(deep=True, index=True, columns=True)

print("\nCustom Copy DataFrame:")
print(df_custom_copy)
```

### **6. When to Use Copying**

- **Avoiding Modifications**: When you want to work with a DataFrame without altering the original data.
- **Creating Subsets**: When you create subsets of your data that you want to modify independently.
- **Preventing Data Loss**: To prevent unintended changes that can lead to data loss.

### **7. Important Considerations**

- **Memory Usage**: Deep copies consume more memory since they replicate all underlying data.
- **Performance**: Shallow copies are faster since they do not create a new copy of the underlying data.
- **Changing Data Types**: If the DataFrame contains complex objects, a shallow copy might lead to unexpected behavior if those objects are mutable.


- Use the `.copy()` method to create copies of DataFrames and Series in pandas.
- A deep copy duplicates all data, while a shallow copy references the same data.
- Use shallow copies for efficiency when you don't need to change the original data, and deep copies to work independently without affecting the original.
- Always consider memory usage and performance when deciding between shallow and deep copies.

### dtypes

In pandas, the `dtype` (data type) of a DataFrame or Series specifies the type of data contained in that structure. Understanding and managing data types is crucial for efficient data manipulation and analysis. Here's a comprehensive overview of data types in pandas, how to check them, and how to change them when necessary.

### **1. Common Data Types in Pandas**

Pandas supports several data types, which can be broadly categorized as follows:

- **Integer Types**:
  - `int64`: 64-bit signed integer.
  - `int32`: 32-bit signed integer (less common).

- **Floating Point Types**:
  - `float64`: 64-bit floating point.
  - `float32`: 32-bit floating point (less common).

- **Boolean Type**:
  - `bool`: Represents boolean values (`True` or `False`).

- **Object Type**:
  - `object`: General type for text or mixed types, typically used for strings.

- **String Type**:
  - `string`: A dedicated string data type introduced in newer versions of pandas (1.0+).

- **Datetime and Timedelta Types**:
  - `datetime64[ns]`: Represents date and time.
  - `timedelta[ns]`: Represents differences between dates and times.

- **Categorical Type**:
  - `category`: A data type for categorical data, which can save memory and improve performance when the number of unique values is small compared to the total number of values.

### **2. Checking Data Types**

You can easily check the data types of a DataFrame's columns or a Series using the `.dtypes` attribute.

#### **Example: Checking Data Types of a DataFrame**

```python
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({
    'A': [1, 2, 3],
    'B': [4.0, 5.5, 6.2],
    'C': ['dog', 'cat', 'bird'],
    'D': [True, False, True],
    'E': pd.to_datetime(['2023-01-01', '2023-02-01', '2023-03-01'])
})

# Check data types
print("Data Types:")
print(df.dtypes)
```

#### **Output**
```
Data Types:
A             int64
B           float64
C            object
D              bool
E    datetime64[ns]
dtype: object
```

### **3. Changing Data Types**

You can change the data type of a column in a DataFrame using the `.astype()` method. This is useful when you need to convert data types for analysis or when preparing data for machine learning models.

#### **Example: Changing Data Types**

```python
# Convert column 'A' to float
df['A'] = df['A'].astype(float)

# Convert column 'C' to category
df['C'] = df['C'].astype('category')

print("\nData Types After Conversion:")
print(df.dtypes)
```

#### **Output**
```
Data Types After Conversion:
A             float64
B           float64
C          category
D              bool
E    datetime64[ns]
dtype: object
```

### **4. Handling Categorical Data**

Categorical data can save memory and improve performance. You can convert a column to the categorical type for optimization.

#### **Example: Converting to Categorical**

```python
# Convert column 'C' to categorical
df['C'] = df['C'].astype('category')

print("\nData Types After Categorical Conversion:")
print(df.dtypes)

print("\nUnique Categories in 'C':")
print(df['C'].cat.categories)
```

#### **Output**
```
Data Types After Categorical Conversion:
A             float64
B           float64
C          category
D              bool
E    datetime64[ns]
dtype: object

Unique Categories in 'C':
Index(['bird', 'cat', 'dog'], dtype='object')
```

### **5. Handling Missing Values and Data Types**

When a column contains missing values, the data type can change. For example, if a column of integers has `NaN`, its type will be promoted to `float` since `NaN` is a float.

#### **Example: Handling Missing Values**

```python
# Create a DataFrame with missing values
df_nan = pd.DataFrame({
    'A': [1, 2, None],
    'B': [4.0, None, 6.2],
})

print("\nData Types with Missing Values:")
print(df_nan.dtypes)
```

#### **Output**
```
Data Types with Missing Values:
A    float64
B    float64
dtype: object
```


- **Data Types**: Understanding data types is essential for efficient data manipulation in pandas. Common types include integers, floats, booleans, objects, strings, dates, and categories.
- **Checking Types**: Use `.dtypes` to check the data types of columns in a DataFrame or Series.
- **Changing Types**: Use `.astype()` to convert data types when necessary.
- **Handling Categorical Data**: Use the categorical type for memory efficiency and performance improvement.
- **Missing Values**: Missing values can affect the data type; for instance, integers with `NaN` will be converted to floats.

Understanding and managing data types effectively will help you work more efficiently with pandas and prepare your data for analysis or machine learning tasks.



































