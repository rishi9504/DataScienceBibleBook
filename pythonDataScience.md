## Introduction to Python for Data Science

Python is a high-level, interpreted programming Janguage that is widely used in various domains of software development, such as web development, scientific computing, artificial intelligence, data analysis, and more.
Python is designed to be simple, easy to fearn, and efficient, making it & popular choice for beginners and experienced developers alike. Python is known for its clear and concise syntax, which emphasizes readability and reduces the cost of program maintenance. The language supports multiple progeamming paradigms, including object-oriented, functional, and procedaral programming.

Python has a vast and robust standand library that provides many useful modules and functions to perform a wide range of tasks. Python is an open-source Janguage, which means that it ks free to use, distribute, and modify. Python's popularity has been growing steadily over the years, and it is now one of the most widely used programming languages in the world.

Undoubtedly one of the most sought-after languages, and very important for data science, python is one of those languages where one needs to make his/her hands dirty if he wants to persuade a career in data science.

Python is simple to use, bui it is a real programming language, offering much more structure and support for large programs than shell seripts or batch files can offer. On the other hand, Python also offers much more error checking than C, and, being a very high-level language, it has high-level data types built in, such as flexible arrays and dictionaries. Because of its more general data types, Python is applicable to a much larger problem domain than Awk or even Perl, yet many things are at least as easy in Python as in those languages.

Python allows you to split your program into modules that can be reused in other Python programs. It comes with a large collection of standard modules that you can use as the basis of your programs — or as examples to start learning to program in Python. Some of these modules provide things like file I/O, system calls, sockets, and even interfaces to graphical user interface toolkits like Tk.

Python is an interpreted language, which can save you considerable time during program development because no compilation and linking is necessary. The interpreter can be used interactively, which makes it easy to experiment with features of the language, write throw-away programs, o test functions during bottom-up program development. It is also a handy desk calculator.

### Keywords And Identifiers 

In Python, a keyword is a reserved word that has a special meaning and cannot be used as an identifier (e.g., variable name, function name). Here is a list of Python keywords:

1. `False`
2. `None`
3. `True`
4. `and`
5. `as`
6. `assert`
7. `async`
8. `await`
9. `break`
10. `class`
11. `continue`
12. `def`
13. `del`
14. `elif`
15. `else`
16. `except`
17. `finally`
18. `for`
19. `from`
20. `global`
21. `if`
22. `import`
23. `in`
24. `is`
25. `lambda`
26. `nonlocal`
27. `not`
28. `or`
29. `pass`
30. `raise`
31. `return`
32. `try`
33. `while`
34. `with`
35. `yield`

You can get this list programmatically using the `keyword` module:

```python
import keyword

print(keyword.kwlist)
```

This will print the list of keywords in the current version of Python you are using.


In Python, an identifier is a name that you can use to refer to variables, functions, classes, and modules. It must start with a letter or underscore, and can contain letters, digits, and underscores. It is case-sensitive, so `my_variable` and `My_Variable` refer to different variables.

Here are some examples of valid identifiers:
- `x`
- `my_variable`
- `my_long_variable_name`
- `_my_variable`
- `MyClass`
- `my_function`
- `my_module`

Here are some examples of invalid identifiers:
- `123` (cannot start with a digit)
- `my variable` (cannot contain spaces)
- `my-variable` (cannot contain hyphens)
- `my@variable` (cannot contain symbols)

You can use variables, functions, and classes with valid identifiers. However, it is considered good practice to choose descriptive names for your identifiers, as it makes your code easier to read and understand.

### Comments

In Python, you can add comments to your code to make it easier to read and understand. Comments are ignored by the interpreter and do not affect the execution of the program.

There are two types of comments in Python: single-line comments and multi-line comments.

Single-line comments start with the `#` symbol and continue until the end of the line. For example:
```
# this is a comment 
data = "This is a string"
```
Multi line comments starts and ends with triple hash (###) and can contain multiple lines for more information about the code.
```
"""
This is a multi-line comment in Python.
It can span multiple lines and is used to provide explanations, documentation, or notes within the code.
Multi-line comments are enclosed within triple quotes.
"""
```
### Docstring in Python

A docstring in Python is a string literal that is used to document a specific segment of code. It provides a convenient way of associating documentation with Python modules, functions, classes, and methods. Docstrings are enclosed in triple quotes (`""" """` or `''' '''`), allowing for multi-line text.

Here's an example of how docstrings are used in Python:

##### Example in a Function

```python
def add(a, b):
    """
    Add two numbers and return the result.

    Parameters:
    a (int or float): The first number.
    b (int or float): The second number.

    Returns:
    int or float: The sum of the two numbers.
    """
    return a + b
```

##### Example in a Class

```python
class Dog:
    """
    A class to represent a dog.

    Attributes:
    name (str): The name of the dog.
    age (int): The age of the dog.
    """

    def __init__(self, name, age):
        """
        Initialize a new Dog instance.

        Parameters:
        name (str): The name of the dog.
        age (int): The age of the dog.
        """
        self.name = name
        self.age = age

    def bark(self):
        """
        Simulate the dog barking.

        Returns:
        str: A message indicating the dog is barking.
        """
        return f"{self.name} is barking."
```

##### Accessing Docstrings

Docstrings can be accessed using the `__doc__` attribute or the `help()` function.

```python
print(add.__doc__)
print(Dog.__doc__)
print(Dog.bark.__doc__)

help(add)
help(Dog)
help(Dog.bark)
```

##### Purpose of Docstrings

- **Documentation:** Provide information about the purpose and usage of code segments.
- **Readability:** Improve code readability by explaining what a function, class, or module does.
- **Help and Documentation Tools:** Used by tools like `pydoc` and IDEs to generate documentation.

By including docstrings, you help other developers (and yourself) understand the code more easily.


## Types in Python
In Python, variables do not have a fixed type; instead, they refer to objects that have a type. Here are the common built-in types for variables in Python:

### Numeric Types

1. **Integer (`int`)**: Represents whole numbers.
    ```python
    a = 10
    ```
   
2. **Floating Point (`float`)**: Represents real numbers with a decimal point.
    ```python
    b = 3.14
    ```
   
3. **Complex Number (`complex`)**: Represents complex numbers.
    ```python
    c = 1 + 2j
    ```

### Sequence Types

1. **String (`str`)**: Represents a sequence of characters.
    ```python
    d = "Hello, World!"
    ```
   
2. **List (`list`)**: Represents an ordered, mutable collection of items.
    ```python
    e = [1, 2, 3, 4, 5]
    ```
   
3. **Tuple (`tuple`)**: Represents an ordered, immutable collection of items.
    ```python
    f = (1, 2, 3, 4, 5)
    ```

4. **Range (`range`)**: Represents a sequence of numbers.
    ```python
    g = range(10)
    ```

### Set Types

1. **Set (`set`)**: Represents an unordered collection of unique items.
    ```python
    h = {1, 2, 3, 4, 5}
    ```
   
2. **Frozen Set (`frozenset`)**: Represents an immutable set.
    ```python
    i = frozenset([1, 2, 3, 4, 5])
    ```

### Mapping Types

1. **Dictionary (`dict`)**: Represents a collection of key-value pairs.
    ```python
    j = {"name": "Alice", "age": 25}
    ```

### Boolean Type

1. **Boolean (`bool`)**: Represents `True` or `False`.
    ```python
    k = True
    l = False
    ```

### Binary Types

1. **Bytes (`bytes`)**: Represents a sequence of bytes.
    ```python
    m = b"Hello"
    ```
   
2. **Byte Array (`bytearray`)**: Represents a mutable sequence of bytes.
    ```python
    n = bytearray(b"Hello")
    ```
   
3. **Memory View (`memoryview`)**: Represents a memory view object.
    ```python
    o = memoryview(b"Hello")
    ```

### None Type

1. **NoneType (`None`)**: Represents the absence of a value.
    ```python
    p = None
    ```

### Type Checking

You can check the type of a variable using the `type()` function:

```python
print(type(a))  # <class 'int'>
print(type(d))  # <class 'str'>
print(type(j))  # <class 'dict'>
```

### Type Conversion

You can convert between types using built-in functions like `int()`, `float()`, `str()`, `list()`, `tuple()`, etc.:

```python
q = float(a)  # Convert int to float
r = str(a)    # Convert int to string
s = list(f)   # Convert tuple to list
```
## Operators in Python
Operators in Python are special symbols that perform operations on variables and values. Python supports various types of operators, which can be categorized as follows:

### Arithmetic Operators

These operators perform basic arithmetic operations:

1. **Addition (`+`)**
   ```python
   a = 10
   b = 20
   result = a + b  # result is 30
   ```
   
2. **Subtraction (`-`)**
   ```python
   result = b - a  # result is 10
   ```
   
3. **Multiplication (`*`)**
   ```python
   result = a * b  # result is 200
   ```
   
4. **Division (`/`)**
   ```python
   result = b / a  # result is 2.0
   ```
   
5. **Floor Division (`//`)**
   ```python
   result = b // a  # result is 2
   ```
   
6. **Modulus (`%`)**
   ```python
   result = b % a  # result is 0
   ```
   
7. **Exponentiation (`**`)**
   ```python
   result = a ** 2  # result is 100
   ```

### Comparison Operators

These operators compare two values and return a Boolean result (`True` or `False`):

1. **Equal (`==`)**
   ```python
   result = (a == b)  # result is False
   ```
   
2. **Not Equal (`!=`)**
   ```python
   result = (a != b)  # result is True
   ```
   
3. **Greater Than (`>`)**
   ```python
   result = (b > a)  # result is True
   ```
   
4. **Less Than (`<`)**
   ```python
   result = (a < b)  # result is True
   ```
   
5. **Greater Than or Equal To (`>=`)**
   ```python
   result = (b >= a)  # result is True
   ```
   
6. **Less Than or Equal To (`<=`)**
   ```python
   result = (a <= b)  # result is True
   ```

### Logical Operators

These operators are used to combine conditional statements:

1. **AND (`and`)**
   ```python
   result = (a > 5 and b < 30)  # result is True
   ```
   
2. **OR (`or`)**
   ```python
   result = (a > 15 or b < 30)  # result is True
   ```
   
3. **NOT (`not`)**
   ```python
   result = not(a > 15)  # result is True
   ```

### Assignment Operators

These operators are used to assign values to variables:

1. **Assignment (`=`)**
   ```python
   a = 5
   ```
   
2. **Add AND (`+=`)**
   ```python
   a += 3  # equivalent to a = a + 3
   ```
   
3. **Subtract AND (`-=`)**
   ```python
   a -= 2  # equivalent to a = a - 2
   ```
   
4. **Multiply AND (`*=`)**
   ```python
   a *= 2  # equivalent to a = a * 2
   ```
   
5. **Divide AND (`/=`)**
   ```python
   a /= 2  # equivalent to a = a / 2
   ```
   
6. **Floor Divide AND (`//=`)**
   ```python
   a //= 2  # equivalent to a = a // 2
   ```
   
7. **Modulus AND (`%=`)**
   ```python
   a %= 3  # equivalent to a = a % 3
   ```
   
8. **Exponentiate AND (`**=`)**
   ```python
   a **= 2  # equivalent to a = a ** 2
   ```

### Bitwise Operators

These operators perform bit-level operations on integers:

1. **AND (`&`)**
   ```python
   result = a & b
   ```
   
2. **OR (`|`)**
   ```python
   result = a | b
   ```
   
3. **XOR (`^`)**
   ```python
   result = a ^ b
   ```
   
4. **NOT (`~`)**
   ```python
   result = ~a
   ```
   
5. **Left Shift (`<<`)**
   ```python
   result = a << 1
   ```
   
6. **Right Shift (`>>`)**
   ```python
   result = a >> 1
   ```

### Membership Operators

These operators test for membership in a sequence (like lists, strings, or tuples):

1. **In (`in`)**
   ```python
   result = 3 in [1, 2, 3]  # result is True
   ```
   
2. **Not In (`not in`)**
   ```python
   result = 4 not in [1, 2, 3]  # result is True
   ```

### Identity Operators

These operators compare the memory locations of two objects:

1. **Is (`is`)**
   ```python
   result = a is b  # result is False if a and b are not the same object
   ```
   
2. **Is Not (`is not`)**
   ```python
   result = a is not b  # result is True if a and b are not the same object
   ```

### Usage Examples

#### Arithmetic Example

```python
a = 10
b = 5
print(a + b)  # Output: 15
print(a - b)  # Output: 5
print(a * b)  # Output: 50
print(a / b)  # Output: 2.0
print(a % b)  # Output: 0
print(a ** b)  # Output: 100000
print(a // b)  # Output: 2
```

#### Logical Example

```python
x = True
y = False
print(x and y)  # Output: False
print(x or y)  # Output: True
print(not x)  # Output: False
```

## Mutable or immutable objects in Python

In Python, objects can be categorized as either mutable or immutable. This distinction is crucial for understanding how objects behave when you manipulate them, especially in terms of memory allocation and performance.

### Immutable Objects

Immutable objects are objects whose state or value cannot be modified after they are created. If you need to modify an immutable object, a new object must be created. Common examples of immutable objects in Python include:

- **Integers (`int`)**
- **Floating Point Numbers (`float`)**
- **Strings (`str`)**
- **Tuples (`tuple`)**
- **Frozen Sets (`frozenset`)**
- **Bytes (`bytes`)**

#### Example of Immutable Objects

```python
# String (immutable)
s = "Hello"
s = s + " World"  # Creates a new string object
print(s)  # Output: Hello World

# Tuple (immutable)
t = (1, 2, 3)
t = t + (4, 5)  # Creates a new tuple object
print(t)  # Output: (1, 2, 3, 4, 5)
```

### Mutable Objects

Mutable objects are objects whose state or value can be modified after they are created. Modifications are made in place without creating a new object. Common examples of mutable objects in Python include:

- **Lists (`list`)**
- **Dictionaries (`dict`)**
- **Sets (`set`)**
- **Byte Arrays (`bytearray`)**

#### Example of Mutable Objects

```python
# List (mutable)
lst = [1, 2, 3]
lst.append(4)  # Modifies the list in place
print(lst)  # Output: [1, 2, 3, 4]

# Dictionary (mutable)
d = {"name": "Alice", "age": 25}
d["age"] = 26  # Modifies the dictionary in place
print(d)  # Output: {'name': 'Alice', 'age': 26}

# Set (mutable)
s = {1, 2, 3}
s.add(4)  # Modifies the set in place
print(s)  # Output: {1, 2, 3, 4}
```

### Key Differences

1. **Modification:**
   - **Immutable:** Once created, the object cannot be altered. Any modification results in a new object being created.
   - **Mutable:** The object can be altered in place, and modifications do not result in a new object being created.

2. **Performance:**
   - **Immutable:** Safer for concurrent access and can be more memory-efficient in certain scenarios due to internal optimizations.
   - **Mutable:** More flexible and typically easier to work with when modifications are frequent.

3. **Identity:**
   - **Immutable:** Since the value cannot change, objects with the same value can share the same memory address.
   - **Mutable:** Each object has a unique memory address, even if they have the same value initially.

4. **Usage in Collections:**
   - **Immutable:** Can be used as keys in dictionaries or elements in sets because their hash value remains constant.
   - **Mutable:** Cannot be used as keys in dictionaries or elements in sets because their hash value can change.

### Practical Implications

Understanding the difference between mutable and immutable objects helps in:

- **Avoiding Bugs:** Ensures you do not unintentionally change the value of objects.
- **Optimizing Performance:** Helps in selecting the appropriate type for a given use case.
- **Using Collections Effectively:** Ensures you use objects that can be hashed when necessary (e.g., dictionary keys).

### Example Illustrating Mutability and Immutability

```python
# Immutable Example
a = 10
b = a
b = b + 5
print(a)  # Output: 10 (a remains unchanged)
print(b)  # Output: 15 (b is a new object)

# Mutable Example
lst1 = [1, 2, 3]
lst2 = lst1
lst2.append(4)
print(lst1)  # Output: [1, 2, 3, 4] (lst1 is modified)
print(lst2)  # Output: [1, 2, 3, 4] (lst2 reflects the modification)
```

In the example, modifying `b` does not affect `a` because integers are immutable. However, modifying `lst2` affects `lst1` because lists are mutable and both variables reference the same object.

### Built in sequence in Python

Python provides several built-in sequence types, which are fundamental to working with collections of data. Here are the main built-in sequences:

### 1. Strings (`str`)

Strings are immutable sequences of Unicode characters. They are defined using single quotes (`'`), double quotes (`"`), or triple quotes (`'''` or `"""`).

```python
s = "Hello, World!"
print(s[0])  # Output: H
print(s[1:5])  # Output: ello
print(s[::-1])  # Output: !dlroW ,olleH
```

### 2. Lists (`list`)

Lists are mutable sequences, typically used to store collections of homogeneous items. They are defined using square brackets (`[]`).

```python
lst = [1, 2, 3, 4, 5]
lst.append(6)
print(lst)  # Output: [1, 2, 3, 4, 5, 6]
print(lst[2])  # Output: 3
print(lst[1:4])  # Output: [2, 3, 4]
```

### 3. Tuples (`tuple`)

Tuples are immutable sequences, typically used to store collections of heterogeneous data. They are defined using parentheses (`()`).

```python
t = (1, 2, 3, 4, 5)
print(t[0])  # Output: 1
print(t[1:3])  # Output: (2, 3)
```

### 4. Ranges (`range`)

Ranges represent an immutable sequence of numbers and are commonly used for looping a specific number of times in `for` loops. They are defined using the `range()` function.

```python
r = range(10)
print(list(r))  # Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

for i in range(1, 5):
    print(i)
```

### 5. Byte Sequences

#### Bytes (`bytes`)
Bytes are immutable sequences of bytes, typically used for binary data. They are defined using the `b` prefix and single or double quotes.

```python
b = b"Hello"
print(b[0])  # Output: 72 (ASCII value of 'H')
print(b[1:4])  # Output: b'ell'
```

#### Bytearray (`bytearray`)
Bytearrays are mutable sequences of bytes.

```python
ba = bytearray(b"Hello")
ba[0] = 77  # ASCII value of 'M'
print(ba)  # Output: bytearray(b'Mello')
```

#### Memoryview (`memoryview`)
Memoryview provides a way to access the internal data of an object that supports the buffer protocol without copying it.

```python
mv = memoryview(b"Hello")
print(mv[1])  # Output: 101 (ASCII value of 'e')
```

### Common Sequence Operations

Here are some common operations that can be performed on sequences:

#### Indexing

Indexing in Python is a way to access individual elements of a sequence (such as a string, list, or tuple) by referring to their position within the sequence. Each element in a sequence is assigned a unique index number starting from 0. Python also supports negative indexing, which starts from -1 for the last element.

### Indexing in Different Sequence Types

#### Strings

Strings are sequences of characters. You can access individual characters using their index.

```python
s = "Hello, World!"
print(s[0])   # Output: 'H'
print(s[7])   # Output: 'W'
print(s[-1])  # Output: '!'
print(s[-3])  # Output: 'l'
```

#### Lists

Lists are mutable sequences, typically used to store collections of homogeneous items. You can access, modify, and delete elements using their index.

```python
lst = [10, 20, 30, 40, 50]
print(lst[0])   # Output: 10
print(lst[2])   # Output: 30
print(lst[-1])  # Output: 50

# Modifying an element
lst[1] = 25
print(lst)  # Output: [10, 25, 30, 40, 50]

# Deleting an element
del lst[3]
print(lst)  # Output: [10, 25, 30, 50]
```

#### Tuples

Tuples are immutable sequences, typically used to store collections of heterogeneous data. You can access elements using their index, but you cannot modify or delete them.

```python
t = (1, 2, 3, 4, 5)
print(t[0])   # Output: 1
print(t[3])   # Output: 4
print(t[-1])  # Output: 5

# Attempting to modify a tuple will raise an error
# t[1] = 10  # TypeError: 'tuple' object does not support item assignment
```

### Slicing

Slicing allows you to access a range of elements in a sequence. The syntax for slicing is `[start:stop:step]`.

```python
# List slicing
lst = [10, 20, 30, 40, 50]
print(lst[1:4])   # Output: [20, 30, 40] (elements from index 1 to 3)
print(lst[:3])    # Output: [10, 20, 30] (elements from start to index 2)
print(lst[3:])    # Output: [40, 50] (elements from index 3 to end)
print(lst[::2])   # Output: [10, 30, 50] (every second element)

# String slicing
s = "Hello, World!"
print(s[0:5])   # Output: 'Hello'
print(s[7:])    # Output: 'World!'
print(s[-6:])   # Output: 'World!'
print(s[::-1])  # Output: '!dlroW ,olleH' (reversed string)
```

### Negative Indexing

Negative indexing allows you to access elements from the end of the sequence.

```python
lst = [10, 20, 30, 40, 50]
print(lst[-1])  # Output: 50 (last element)
print(lst[-2])  # Output: 40 (second to last element)
print(lst[-3:])  # Output: [30, 40, 50] (last three elements)
print(lst[:-3])  # Output: [10, 20] (all but the last three elements)
```

### Practical Applications

#### Accessing Elements

```python
lst = ['a', 'b', 'c', 'd', 'e']
print(lst[0])  # Output: 'a'
print(lst[-1])  # Output: 'e'
```

#### Modifying Elements

```python
lst[1] = 'z'
print(lst)  # Output: ['a', 'z', 'c', 'd', 'e']
```

#### Slicing for Subsets

```python
subset = lst[1:4]
print(subset)  # Output: ['z', 'c', 'd']
```

#### Reversing a Sequence

```python
reversed_lst = lst[::-1]
print(reversed_lst)  # Output: ['e', 'd', 'c', 'z', 'a']
```

#### Copying a Sequence

```python
copy_lst = lst[:]
print(copy_lst)  # Output: ['a', 'z', 'c', 'd', 'e']
```

#### Skipping Elements

```python
skipped_elements = lst[::2]
print(skipped_elements)  # Output: ['a', 'c', 'e']
```



#### Concatenation

Concatenation in Python refers to joining two or more sequences of the same type. It is commonly used with strings, lists, and tuples. Let's explore concatenation for each of these sequence types:

### String Concatenation

You can concatenate strings using the `+` operator or by using string formatting methods.

#### Using the `+` Operator

```python
str1 = "Hello"
str2 = "World"
result = str1 + " " + str2
print(result)  # Output: Hello World
```

#### Using String Formatting

1. **`format()` Method**

```python
str1 = "Hello"
str2 = "World"
result = "{} {}".format(str1, str2)
print(result)  # Output: Hello World
```

2. **F-Strings (Python 3.6+)**

```python
str1 = "Hello"
str2 = "World"
result = f"{str1} {str2}"
print(result)  # Output: Hello World
```

### List Concatenation

You can concatenate lists using the `+` operator or the `extend()` method.

#### Using the `+` Operator

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
result = list1 + list2
print(result)  # Output: [1, 2, 3, 4, 5, 6]
```

#### Using the `extend()` Method

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
list1.extend(list2)
print(list1)  # Output: [1, 2, 3, 4, 5, 6]
```

### Tuple Concatenation

You can concatenate tuples using the `+` operator.

```python
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)
result = tuple1 + tuple2
print(result)  # Output: (1, 2, 3, 4, 5, 6)
```

### Concatenation Using `itertools.chain`

For larger sequences, you can use `itertools.chain` to concatenate without creating intermediate objects.

```python
import itertools

list1 = [1, 2, 3]
list2 = [4, 5, 6]
result = list(itertools.chain(list1, list2))
print(result)  # Output: [1, 2, 3, 4, 5, 6]
```

### Practical Examples

#### Concatenating Multiple Strings

```python
str1 = "Python"
str2 = "is"
str3 = "awesome"
result = str1 + " " + str2 + " " + str3
print(result)  # Output: Python is awesome
```

#### Concatenating Lists with Different Types

```python
list1 = [1, "apple", 3.5]
list2 = ["banana", 4, True]
result = list1 + list2
print(result)  # Output: [1, 'apple', 3.5, 'banana', 4, True]
```

#### Concatenating Nested Lists

```python
list1 = [[1, 2], [3, 4]]
list2 = [[5, 6], [7, 8]]
result = list1 + list2
print(result)  # Output: [[1, 2], [3, 4], [5, 6], [7, 8]]
```

### Efficiency Considerations

- **Strings:** Frequent concatenation using the `+` operator can be inefficient due to the creation of new string objects. Using `str.join()` for concatenating multiple strings is more efficient.
  
  ```python
  strings = ["Hello", "World", "Python", "is", "great"]
  result = " ".join(strings)
  print(result)  # Output: Hello World Python is great
  ```

- **Lists:** Using `extend()` is more memory efficient than `+` when you need to modify an existing list.
  
  ```python
  list1 = [1, 2, 3]
  list2 = [4, 5, 6]
  list1.extend(list2)
  print(list1)  # Output: [1, 2, 3, 4, 5, 6]
  ```

#### Repetition 

We can use repetition by just using the * operator and mentioning the number of times we want the value to be repeated.

```python
print("Hello" * 3)  # Output: HelloHelloHello
print([1, 2] * 2)  # Output: [1, 2, 1, 2]
```


