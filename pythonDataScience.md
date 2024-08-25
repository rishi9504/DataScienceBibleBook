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
## Control Statements in Python

### if statement
The `if` statement in Python is used for conditional execution of code blocks. It allows you to execute certain pieces of code only if a specified condition is true. Here's a detailed look at how the `if` statement works in Python, including its various forms and practical examples.

### Basic `if` Statement

The basic `if` statement checks a condition and executes a block of code if the condition evaluates to `True`.

```python
x = 10

if x > 5:
    print("x is greater than 5")
```

### `if-else` Statement

The `if-else` statement provides an alternative block of code to execute if the condition is `False`.

```python
x = 3

if x > 5:
    print("x is greater than 5")
else:
    print("x is not greater than 5")
```

### `if-elif-else` Statement

The `if-elif-else` (short for "else if") statement allows you to check multiple conditions in sequence.

```python
x = 7

if x > 10:
    print("x is greater than 10")
elif x > 5:
    print("x is greater than 5 but not greater than 10")
else:
    print("x is 5 or less")
```

### Nested `if` Statements

You can nest `if` statements within other `if` statements to check multiple conditions at different levels.

```python
x = 8

if x > 5:
    print("x is greater than 5")
    if x > 7:
        print("x is also greater than 7")
    else:
        print("x is 6 or 7")
else:
    print("x is 5 or less")
```

### Using Logical Operators with `if` Statements

You can use logical operators like `and`, `or`, and `not` to combine multiple conditions.

```python
x = 6
y = 8

if x > 5 and y > 7:
    print("Both conditions are true")
    
if x > 5 or y < 7:
    print("At least one condition is true")

if not x > 10:
    print("x is not greater than 10")
```

### Checking Membership with `in` Operator

You can use the `in` operator to check if a value is present in a sequence or a collection.

```python
fruits = ["apple", "banana", "cherry"]

if "banana" in fruits:
    print("Banana is in the list")

if "orange" not in fruits:
    print("Orange is not in the list")
```

### Using `if` with Comparison Operators

You can use various comparison operators (`==`, `!=`, `>`, `<`, `>=`, `<=`) within an `if` statement.

```python
x = 10
y = 20

if x == y:
    print("x is equal to y")
elif x != y:
    print("x is not equal to y")

if x < y:
    print("x is less than y")

if x <= y:
    print("x is less than or equal to y")

if x > y:
    print("x is greater than y")

if x >= y:
    print("x is greater than or equal to y")
```

### Examples

#### Example 1: Determine if a Number is Even or Odd

```python
number = 7

if number % 2 == 0:
    print(f"{number} is even")
else:
    print(f"{number} is odd")
```

#### Example 2: Check Age for Voting Eligibility

```python
age = 18

if age >= 18:
    print("You are eligible to vote")
else:
    print("You are not eligible to vote")
```

#### Example 3: Grade Classification

```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```

### Indentation

In Python, indentation is crucial for defining the scope of an `if` statement. All code blocks within the `if`, `elif`, and `else` statements must be consistently indented.

```python
x = 10

if x > 5:
    print("x is greater than 5")
    if x > 7:
        print("x is also greater than 7")
else:
    print("x is 5 or less")
```

The `if` statement is a fundamental control structure in Python, allowing for conditional execution of code. Proper use of `if`, `elif`, and `else` enables you to create complex decision-making logic in your programs.


### for statement

The `for` statement in Python is used to iterate over a sequence (such as a list, tuple, string, or range) or any other iterable object. The `for` loop allows you to execute a block of code repeatedly for each item in the sequence.

### Basic `for` Loop

The basic `for` loop iterates over each element in a sequence and executes a block of code for each element.

```python
# Iterating over a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

### Iterating Over a Range

The `range()` function generates a sequence of numbers, which is commonly used with `for` loops.

```python
# Iterating over a range of numbers
for i in range(5):
    print(i)  # Output: 0, 1, 2, 3, 4
```

You can also specify a start value and a step value in the `range()` function.

```python
# Specifying start, stop, and step values
for i in range(2, 10, 2):
    print(i)  # Output: 2, 4, 6, 8
```

### Iterating Over a String

You can iterate over each character in a string.

```python
# Iterating over a string
word = "hello"
for char in word:
    print(char)
```

### Iterating Over a Dictionary

When iterating over a dictionary, you can use methods like `items()`, `keys()`, and `values()` to get the dictionary's keys and values.

```python
# Iterating over dictionary items
student_grades = {"Alice": 85, "Bob": 92, "Charlie": 78}
for name, grade in student_grades.items():
    print(f"{name}: {grade}")

# Iterating over dictionary keys
for name in student_grades.keys():
    print(name)

# Iterating over dictionary values
for grade in student_grades.values():
    print(grade)
```

### Nested `for` Loops

You can nest `for` loops inside each other to iterate over multi-dimensional sequences like lists of lists.

```python
# Nested for loop to iterate over a list of lists
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
for row in matrix:
    for element in row:
        print(element)
```

### Using `enumerate()`

The `enumerate()` function adds a counter to an iterable, allowing you to access both the index and the value during iteration.

```python
# Using enumerate to get index and value
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(f"Index {index}: {fruit}")
```

### Using `zip()`

The `zip()` function allows you to iterate over multiple sequences in parallel.

```python
# Using zip to iterate over multiple sequences
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
for name, age in zip(names, ages):
    print(f"{name} is {age} years old")
```

### List Comprehensions

List comprehensions provide a concise way to create lists using `for` loops.

```python
# List comprehension to create a list of squares
squares = [x**2 for x in range(10)]
print(squares)  # Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

### Practical Examples

#### Example 1: Sum of Numbers

```python
# Calculate the sum of numbers from 1 to 10
total = 0
for i in range(1, 11):
    total += i
print(f"Total: {total}")  # Output: Total: 55
```

#### Example 2: Filter Even Numbers

```python
# Filter even numbers from a list
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evens = [num for num in numbers if num % 2 == 0]
print(evens)  # Output: [2, 4, 6, 8, 10]
```

#### Example 3: Flatten a List of Lists

```python
# Flatten a list of lists using nested for loop
nested_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flat_list = [element for sublist in nested_list for element in sublist]
print(flat_list)  # Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Breaking Out of a Loop

You can use the `break` statement to exit a `for` loop prematurely.

```python
# Using break to exit a loop
for i in range(10):
    if i == 5:
        break
    print(i)  # Output: 0, 1, 2, 3, 4
```

### Skipping an Iteration

You can use the `continue` statement to skip the current iteration and move to the next one.

```python
# Using continue to skip an iteration
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)  # Output: 1, 3, 5, 7, 9
```

### Using `else` with `for` Loop

The `else` block after a `for` loop executes if the loop completes normally (i.e., not terminated by a `break` statement).

```python
# Using else with for loop
for i in range(5):
    print(i)
else:
    print("Loop completed without break")
```

The `while` loop in Python is used to repeatedly execute a block of code as long as a given condition is true. It is useful when the number of iterations is not known beforehand and depends on some runtime condition.

### Basic `while` Loop

The basic syntax of a `while` loop is:

```python
while condition:
    # Code block to execute
```

Here, `condition` is a boolean expression. The loop continues to execute the code block as long as the condition evaluates to `True`.

```python
# Example: Print numbers from 1 to 5
count = 1
while count <= 5:
    print(count)
    count += 1
```

### Infinite Loop

A `while` loop can create an infinite loop if the condition never becomes `False`. This can be useful in certain situations but should be used with caution.

```python
# Example of an infinite loop
while True:
    print("This loop will run forever")
    break  # Add a break to prevent it from running forever
```

### Using `break` Statement

The `break` statement can be used to exit the loop prematurely, even if the condition is still `True`.

```python
# Example: Using break to exit the loop
count = 1
while count <= 10:
    print(count)
    if count == 5:
        break
    count += 1
```

### Using `continue` Statement

The `continue` statement skips the rest of the code inside the loop for the current iteration and jumps to the next iteration of the loop.

```python
# Example: Using continue to skip an iteration
count = 0
while count < 10:
    count += 1
    if count % 2 == 0:
        continue
    print(count)  # This will print only odd numbers
```

### Using `else` with `while` Loop

An `else` block can be added after a `while` loop, which will be executed when the loop condition becomes `False`.

```python
# Example: Using else with while loop
count = 1
while count <= 5:
    print(count)
    count += 1
else:
    print("Loop ended")
```

### Practical Examples

#### Example 1: Sum of Numbers

Calculate the sum of numbers from 1 to 100 using a `while` loop.

```python
# Calculate the sum of numbers from 1 to 100
total = 0
num = 1
while num <= 100:
    total += num
    num += 1
print(f"Total: {total}")  # Output: Total: 5050
```

#### Example 2: Factorial of a Number

Calculate the factorial of a number using a `while` loop.

```python
# Calculate the factorial of a number
num = 5
factorial = 1
while num > 0:
    factorial *= num
    num -= 1
print(f"Factorial: {factorial}")  # Output: Factorial: 120
```

#### Example 3: User Input Validation

Prompt the user for input until they enter a valid number.

```python
# Prompt the user for input until a valid number is entered
while True:
    user_input = input("Enter a number: ")
    if user_input.isdigit():
        num = int(user_input)
        break
    else:
        print("Invalid input, please enter a number.")
print(f"You entered: {num}")
```

### Nested `while` Loops

You can nest `while` loops inside each other to handle more complex situations.

```python
# Example: Nested while loops to print a pattern
i = 1
while i <= 5:
    j = 1
    while j <= i:
        print("*", end="")
        j += 1
    print()
    i += 1
```

### Controlling the Loop with Flags

You can use a flag variable to control the execution of a `while` loop.

```python
# Example: Using a flag to control the loop
flag = True
count = 0
while flag:
    print(count)
    count += 1
    if count >= 5:
        flag = False
```

### Efficiency Considerations

- **Avoid Infinite Loops:** Ensure that the loop condition will eventually become `False` to prevent infinite loops that can crash your program.
- **Use Break and Continue Judiciously:** `break` and `continue` statements can make loops more flexible, but overuse can lead to hard-to-read code.


## User-defined functions

User-defined functions in Python are blocks of reusable code that you can define and call as needed in your programs. Functions help you organize your code, make it more readable, and avoid repetition. Here’s how you can define and use functions in Python:

### Defining a Function

You define a function using the `def` keyword, followed by the function name and parentheses. The code block within the function is indented.

```python
def function_name(parameters):
    """docstring"""
    # Code block
    return value
```

- **`function_name`**: The name of the function.
- **`parameters`**: Optional, used to pass values to the function.
- **`docstring`**: Optional, a string that describes the function's purpose.
- **`return`**: Optional, used to return a value from the function.

### Example: A Simple Function

```python
def greet():
    """This function prints a greeting message."""
    print("Hello, world!")

# Calling the function
greet()
```

### Function with Parameters

You can pass parameters to a function to make it more flexible.

```python
def greet(name):
    """This function greets the person passed as a parameter."""
    print(f"Hello, {name}!")

# Calling the function with an argument
greet("Alice")
```

### Function with Return Value

A function can return a value using the `return` statement.

```python
def add(a, b):
    """This function returns the sum of two numbers."""
    return a + b

# Calling the function and storing the result
result = add(3, 5)
print(result)  # Output: 8
```

### Function with Default Parameters

You can define default values for parameters, which are used if no argument is provided.

```python
def greet(name="World"):
    """This function greets the person passed as a parameter, or 'World' by default."""
    print(f"Hello, {name}!")

# Calling the function without an argument
greet()  # Output: Hello, World!

# Calling the function with an argument
greet("Alice")  # Output: Hello, Alice!
```

### Function with Variable Number of Arguments

You can use `*args` to pass a variable number of non-keyword arguments and `**kwargs` to pass a variable number of keyword arguments.

```python
def print_numbers(*args):
    """This function prints all the numbers passed as arguments."""
    for number in args:
        print(number)

# Calling the function with multiple arguments
print_numbers(1, 2, 3, 4, 5)

def print_info(**kwargs):
    """This function prints key-value pairs passed as keyword arguments."""
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# Calling the function with keyword arguments
print_info(name="Alice", age=30, city="New York")
```

### Lambda Functions

Lambda functions are small anonymous functions defined using the `lambda` keyword. They can have any number of parameters but only one expression.

```python
# Lambda function to add two numbers
add = lambda a, b: a + b

# Calling the lambda function
print(add(3, 5))  # Output: 8
```

### Scope and Lifetime of Variables

Variables defined inside a function are local to that function and cannot be accessed outside it. Variables defined outside all functions are global and can be accessed anywhere in the code.

```python
global_var = "I am global"

def my_function():
    local_var = "I am local"
    print(global_var)
    print(local_var)

my_function()
# Output:
# I am global
# I am local

# print(local_var)  # This will raise an error because local_var is not accessible outside the function
```

### Practical Examples

#### Example 1: Factorial Function

```python
def factorial(n):
    """This function returns the factorial of a given number."""
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

# Calling the factorial function
print(factorial(5))  # Output: 120
```

#### Example 2: Fibonacci Sequence

```python
def fibonacci(n):
    """This function returns the Fibonacci sequence up to the nth number."""
    sequence = []
    a, b = 0, 1
    while len(sequence) < n:
        sequence.append(a)
        a, b = b, a + b
    return sequence

# Calling the fibonacci function
print(fibonacci(10))  # Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

#### Example 3: Checking Prime Numbers

```python
def is_prime(num):
    """This function checks if a number is prime."""
    if num < 2:
        return False
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            return False
    return True

# Calling the is_prime function
print(is_prime(11))  # Output: True
print(is_prime(4))   # Output: False
```

### Higher-Order Functions

Functions that take other functions as arguments or return them as results are called higher-order functions.

```python
def apply_function(func, value):
    """This function applies a passed function to a value."""
    return func(value)

# Using a lambda function as an argument
result = apply_function(lambda x: x ** 2, 5)
print(result)  # Output: 25
```
Modules in Python are files containing Python code (functions, classes, variables, etc.) that can be imported and used in other Python programs. Using modules helps you organize your code into manageable, reusable components. Python comes with a rich standard library of modules, and you can also create your own or install third-party modules.

### Importing Modules

You can import a module using the `import` statement.

```python
import math

# Using a function from the math module
print(math.sqrt(16))  # Output: 4.0
```

### Importing Specific Attributes

You can import specific functions, classes, or variables from a module using the `from ... import ...` statement.

```python
from math import sqrt, pi

# Using imported functions and variables
print(sqrt(25))  # Output: 5.0
print(pi)        # Output: 3.141592653589793
```

### Importing All Attributes

You can import all attributes from a module using the `from ... import *` statement, but it's generally discouraged because it can lead to a cluttered namespace and potential conflicts.

```python
from math import *

# Using imported functions and variables
print(sqrt(36))  # Output: 6.0
print(pi)        # Output: 3.141592653589793
```

### Aliasing Modules

You can give a module or its attributes an alias using the `as` keyword.

```python
import math as m

# Using the alias
print(m.sqrt(49))  # Output: 7.0
```

### Creating Your Own Module

To create your own module, you simply need to save a Python file with the functions, classes, and variables you want to include. For example, save the following code in a file named `mymodule.py`.

```python
# mymodule.py

def greet(name):
    return f"Hello, {name}!"

pi = 3.14159
```

You can then import and use your module in another Python script.

```python
# main.py

import mymodule

# Using the module's functions and variables
print(mymodule.greet("Alice"))  # Output: Hello, Alice!
print(mymodule.pi)              # Output: 3.14159
```

### Using `dir()` to List Module Attributes

You can use the `dir()` function to list all the attributes and functions defined in a module.

```python
import math
print(dir(math))
```

### Built-in Modules

Python's standard library includes many useful built-in modules. Here are a few examples:

- `sys`: Provides access to some variables used or maintained by the Python interpreter.
- `os`: Provides functions for interacting with the operating system.
- `datetime`: Supplies classes for manipulating dates and times.
- `random`: Implements pseudo-random number generators.
- `json`: Provides methods for working with JSON data.

#### Example: `os` Module

```python
import os

# Get the current working directory
print(os.getcwd())

# List files and directories in the current directory
print(os.listdir())
```

#### Example: `datetime` Module

```python
import datetime

# Get the current date and time
now = datetime.datetime.now()
print(now)

# Create a specific date
d = datetime.date(2023, 7, 19)
print(d)
```

#### Example: `random` Module

```python
import random

# Generate a random number between 1 and 10
print(random.randint(1, 10))

# Choose a random element from a list
print(random.choice(['apple', 'banana', 'cherry']))
```

### Installing Third-Party Modules

You can install third-party modules using the `pip` package manager. For example, to install the `requests` module for making HTTP requests:

```bash
pip install requests
```

You can then use the installed module in your code.

```python
import requests

# Make an HTTP GET request
response = requests.get('https://api.github.com')
print(response.status_code)
print(response.json())
```

### Packages

A package is a collection of modules in a directory that includes a special `__init__.py` file, which can be empty. Packages allow for a hierarchical structuring of the module namespace using dot notation.

#### Example: Creating a Package

1. Create a directory structure like this:
   ```
   mypackage/
       __init__.py
       module1.py
       module2.py
   ```

2. Define some functions in `module1.py` and `module2.py`:
   ```python
   # module1.py
   def func1():
       print("Function 1 from Module 1")

   # module2.py
   def func2():
       print("Function 2 from Module 2")
   ```

3. Import and use the package in your script:
   ```python
   # main.py
   from mypackage import module1, module2

   module1.func1()  # Output: Function 1 from Module 1
   module2.func2()  # Output: Function 2 from Module 2
   ```

In Python, input and output (I/O) operations are fundamental for interacting with users and handling data. Let's explore how to handle I/O operations in Python, including reading input from the user and printing output to the console, as well as working with files for more advanced I/O operations.

### Input from the User

To read input from the user, you can use the `input()` function. This function reads a line from input, converts it to a string, and returns it.

```python
# Reading input from the user
name = input("Enter your name: ")
print(f"Hello, {name}!")
```

If you need to read a numerical input, you can convert the string input to an integer or float using `int()` or `float()`.

```python
# Reading an integer input
age = int(input("Enter your age: "))
print(f"You are {age} years old.")

# Reading a float input
height = float(input("Enter your height in meters: "))
print(f"Your height is {height} meters.")
```

### Output to the Console

To print output to the console, you use the `print()` function. The `print()` function can take multiple arguments and separates them with a space by default.

```python
# Printing to the console
print("Hello, world!")
print("Name:", name)
print("Age:", age)
```

### Formatting Output

You can format output using f-strings (formatted string literals), the `format()` method, or the `%` operator.

#### Using f-strings (Python 3.6+)

```python
name = "Alice"
age = 30
print(f"Hello, {name}. You are {age} years old.")
```

#### Using the `format()` Method

```python
print("Hello, {}. You are {} years old.".format(name, age))
```

#### Using the `%` Operator

```python
print("Hello, %s. You are %d years old." % (name, age))
```

### File I/O

For more advanced I/O operations, you can read from and write to files. Here’s how you can work with files in Python:

#### Opening a File

Use the `open()` function to open a file. The `open()` function returns a file object, which has methods and attributes for performing various operations.

```python
# Opening a file in read mode
file = open('example.txt', 'r')

# Opening a file in write mode
file = open('example.txt', 'w')

# Opening a file in append mode
file = open('example.txt', 'a')

# Opening a file in binary mode
file = open('example.txt', 'rb')
```

#### Reading from a File

You can read the contents of a file using methods like `read()`, `readline()`, and `readlines()`.

```python
# Reading the entire file
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)

# Reading line by line
with open('example.txt', 'r') as file:
    for line in file:
        print(line, end='')

# Reading lines into a list
with open('example.txt', 'r') as file:
    lines = file.readlines()
    print(lines)
```

#### Writing to a File

You can write to a file using methods like `write()` and `writelines()`.

```python
# Writing to a file
with open('example.txt', 'w') as file:
    file.write("Hello, world!\n")
    file.write("This is a new line.\n")

# Writing a list of lines to a file
lines = ["Line 1\n", "Line 2\n", "Line 3\n"]
with open('example.txt', 'w') as file:
    file.writelines(lines)
```

#### Appending to a File

To append content to an existing file, use the 'a' mode.

```python
# Appending to a file
with open('example.txt', 'a') as file:
    file.write("Appending a new line.\n")
```

#### Closing a File

When you are done with a file, it’s good practice to close it using the `close()` method. However, when using the `with` statement to open a file, it is automatically closed when the block inside the `with` statement is exited.

```python
file = open('example.txt', 'r')
# Perform file operations
file.close()
```

### Practical Examples

#### Example 1: Copying a File

```python
# Copying contents from one file to another
with open('source.txt', 'r') as src:
    with open('destination.txt', 'w') as dest:
        dest.write(src.read())
```

#### Example 2: Counting Lines, Words, and Characters in a File

```python
def count_file_content(filename):
    with open(filename, 'r') as file:
        lines = file.readlines()
        num_lines = len(lines)
        num_words = sum(len(line.split()) for line in lines)
        num_chars = sum(len(line) for line in lines)
    return num_lines, num_words, num_chars

filename = 'example.txt'
lines, words, chars = count_file_content(filename)
print(f"Lines: {lines}, Words: {words}, Characters: {chars}")
```

### Handling Exceptions

It’s important to handle exceptions that may occur during I/O operations, such as file not found errors or permission errors.

```python
try:
    with open('example.txt', 'r') as file:
        content = file.read()
        print(content)
except FileNotFoundError:
    print("The file was not found.")
except IOError:
    print("An error occurred while reading the file.")
```
## Error and Exceptions in detail

In Python, errors and exceptions are crucial aspects of the language that handle unexpected events during program execution. Understanding how to manage these errors is essential for writing robust and fault-tolerant code. Let's dive into the details of errors and exceptions in Python.

### Types of Errors

1. **Syntax Errors**: These are errors in the syntax of the code and are detected at the time of parsing. They occur when the Python parser is unable to interpret a line of code.

    ```python
    # SyntaxError example
    if True
        print("Hello")
    ```

2. **Runtime Errors**: These occur during the execution of the program. They are also known as exceptions and happen when Python encounters an unexpected condition.

    ```python
    # RuntimeError example
    print(10 / 0)  # ZeroDivisionError
    ```

### Common Built-in Exceptions

Here are some common built-in exceptions in Python:

- `ArithmeticError`: Base class for arithmetic errors.
  - `ZeroDivisionError`: Raised when division or modulo by zero takes place.
  - `OverflowError`: Raised when the result of an arithmetic operation is too large.
  - `FloatingPointError`: Raised when a floating point operation fails.

- `AttributeError`: Raised when an attribute reference or assignment fails.
  
  ```python
  obj = None
  obj.attr  # AttributeError
  ```

- `EOFError`: Raised when the `input()` function hits end-of-file condition.

- `ImportError`: Raised when an import statement fails to find the module definition or when a `from ... import` fails.

- `IndexError`: Raised when a sequence subscript is out of range.

  ```python
  lst = [1, 2, 3]
  lst[5]  # IndexError
  ```

- `KeyError`: Raised when a dictionary key is not found.

  ```python
  d = {'key': 'value'}
  d['another_key']  # KeyError
  ```

- `KeyboardInterrupt`: Raised when the user hits the interrupt key (typically Control-C).

- `MemoryError`: Raised when an operation runs out of memory.

- `NameError`: Raised when a local or global name is not found.

  ```python
  print(undefined_variable)  # NameError
  ```

- `OSError`: Base class for operating system-related errors.

- `TypeError`: Raised when an operation or function is applied to an object of inappropriate type.

  ```python
  len(5)  # TypeError
  ```

- `ValueError`: Raised when a built-in operation or function receives an argument that has the right type but an inappropriate value.

  ```python
  int('a')  # ValueError
  ```

### Exception Handling

Python provides a way to handle exceptions using `try`, `except`, `else`, and `finally` blocks.

#### Basic Exception Handling

```python
try:
    # Code that may raise an exception
    result = 10 / 0
except ZeroDivisionError:
    # Code to handle the exception
    print("Cannot divide by zero.")
```

#### Handling Multiple Exceptions

```python
try:
    result = 10 / 0
except (ZeroDivisionError, TypeError):
    print("An error occurred.")
```

#### Catching All Exceptions

```python
try:
    result = 10 / 0
except Exception as e:
    print(f"An error occurred: {e}")
```

#### Using `else` Clause

The `else` block is executed if no exceptions are raised in the `try` block.

```python
try:
    result = 10 / 2
except ZeroDivisionError:
    print("Cannot divide by zero.")
else:
    print("Division successful:", result)
```

#### Using `finally` Clause

The `finally` block is executed no matter what, even if an exception is raised.

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero.")
finally:
    print("This will always execute.")
```

### Raising Exceptions

You can raise exceptions using the `raise` keyword.

```python
# Raising an exception
raise ValueError("A custom error message")
```

### Custom Exceptions

You can define your own exceptions by creating a new class derived from the base `Exception` class.

```python
class MyCustomError(Exception):
    def __init__(self, message):
        self.message = message

# Raising a custom exception
raise MyCustomError("This is a custom error message")
```

### Example: Comprehensive Error Handling

```python
class NegativeNumberError(Exception):
    """Exception raised for errors in the input if the number is negative."""

    def __init__(self, number, message="Number cannot be negative"):
        self.number = number
        self.message = message
        super().__init__(self.message)

def square_root(number):
    if number < 0:
        raise NegativeNumberError(number)
    return number ** 0.5

try:
    num = int(input("Enter a number: "))
    result = square_root(num)
except NegativeNumberError as e:
    print(f"Error: {e.message}. You entered: {e.number}")
except ValueError:
    print("Invalid input. Please enter a valid number.")
else:
    print(f"The square root of {num} is {result}")
finally:
    print("Execution completed.")
```

### Assertions

Assertions are a debugging aid that test a condition. If the condition is false, it raises an `AssertionError` with an optional message.

```python
def divide(a, b):
    assert b != 0, "Division by zero is not allowed"
    return a / b

print(divide(10, 2))  # Works fine
print(divide(10, 0))  # Raises AssertionError
```

### Logging

For better error handling and debugging, consider using the `logging` module instead of or in addition to `print()` statements.

```python
import logging

logging.basicConfig(level=logging.DEBUG, format='%(asctime)s - %(levelname)s - %(message)s')

def divide(a, b):
    try:
        result = a / b
    except ZeroDivisionError:
        logging.error("Attempted to divide by zero")
    else:
        return result

divide(10, 0)
```
In Python, scopes and namespaces are fundamental concepts that help to keep track of variables and their visibility within different parts of the code. Understanding how these concepts work is crucial for writing effective and bug-free Python programs.

### Namespaces

A namespace is a container that holds a set of identifiers (variable names) and their corresponding objects. Think of it as a mapping from names to objects. Python uses namespaces to keep track of all the variables, functions, and classes in a program.

#### Types of Namespaces

1. **Built-in Namespace**: Contains built-in functions and exceptions, such as `print()`, `len()`, and `Exception`.
2. **Global Namespace**: Contains global variables, typically defined at the module level.
3. **Local Namespace**: Contains local variables within a function or method.
4. **Enclosing Namespace**: Contains variables in the scope of any enclosing functions, used in nested functions.

### Scopes

A scope is the textual region of a Python program where a namespace is directly accessible. There are four types of scopes in Python:

1. **Local Scope**: The innermost scope, where local variables are defined. This is the scope within a function or method.
2. **Enclosing Scope**: The scope of any enclosing functions, which comes into play for nested functions.
3. **Global Scope**: The scope at the level of the module, where global variables are defined.
4. **Built-in Scope**: The outermost scope, which contains built-in names.

### LEGB Rule

Python follows the LEGB (Local, Enclosing, Global, Built-in) rule to resolve the scope of a variable:

1. **Local**: Look for the name in the local scope (inside the current function).
2. **Enclosing**: Look for the name in any enclosing function scopes (outer functions).
3. **Global**: Look for the name in the global scope (at the module level).
4. **Built-in**: Look for the name in the built-in scope (built-in functions).

### Examples

#### Local and Global Scope

```python
x = "global"

def foo():
    x = "local"
    print(x)

foo()       # Output: local
print(x)    # Output: global
```

#### Enclosing Scope

```python
def outer():
    x = "outer"
    
    def inner():
        x = "inner"
        print(x)
    
    inner()         # Output: inner
    print(x)        # Output: outer

outer()
```

#### Global Keyword

To modify a global variable inside a function, use the `global` keyword.

```python
x = "global"

def foo():
    global x
    x = "local"
    print(x)

foo()       # Output: local
print(x)    # Output: local
```

#### Nonlocal Keyword

To modify a variable in an enclosing scope, use the `nonlocal` keyword.

```python
def outer():
    x = "outer"
    
    def inner():
        nonlocal x
        x = "inner"
        print(x)
    
    inner()         # Output: inner
    print(x)        # Output: inner

outer()
```

### Built-in Scope

Python’s built-in scope contains functions and exceptions that are always available.

```python
print(len("hello"))  # Output: 5
```

### Practical Example

Let's consider a more comprehensive example to demonstrate the scopes and namespaces:

```python
def outer_function():
    x = "outer"

    def inner_function():
        nonlocal x
        x = "inner"
        print("Inner:", x)

    inner_function()
    print("Outer:", x)

x = "global"
outer_function()
print("Global:", x)
```

Output:

```
Inner: inner
Outer: inner
Global: global
```

### The `globals()` and `locals()` Functions

- **`globals()`**: Returns a dictionary of the current global symbol table.
- **`locals()`**: Returns a dictionary of the current local symbol table.

```python
x = "global"

def foo():
    y = "local"
    print(globals())
    print(locals())

foo()
```

### Summary

Understanding scopes and namespaces is essential for writing well-structured and error-free Python programs. Here are the key points:

1. **Namespaces** are containers that map names to objects.
2. **Scopes** are the regions of a program where a namespace is directly accessible.
3. Python resolves variable names using the **LEGB** rule.
4. Use the `global` keyword to modify global variables within functions.
5. Use the `nonlocal` keyword to modify variables in an enclosing scope.
6. The `globals()` and `locals()` functions can be used to inspect the current global and local namespaces, respectively.

## Class in Python

Classes in Python are a fundamental concept in object-oriented programming (OOP). They provide a means of bundling data and functionality together. Creating a new class creates a new type of object, allowing new instances of that type to be made. Python classes provide all the standard features of OOP, such as inheritance, encapsulation, and polymorphism.

### Defining a Class

You define a class using the `class` keyword, followed by the class name and a colon. Inside the class, you define methods (functions that belong to the class) and attributes (variables that belong to the class).

```python
class MyClass:
    # Class attribute
    class_attribute = "I am a class attribute"

    # Constructor
    def __init__(self, value):
        # Instance attribute
        self.instance_attribute = value

    # Method
    def method(self):
        return f"I am a method and my value is {self.instance_attribute}"
```

### Creating an Instance

To create an instance of a class, you call the class using its name and pass any required arguments to the `__init__` method.

```python
# Creating an instance of MyClass
obj = MyClass("Hello, World!")

# Accessing instance attribute
print(obj.instance_attribute)  # Output: Hello, World!

# Calling a method
print(obj.method())  # Output: I am a method and my value is Hello, World!

# Accessing class attribute
print(MyClass.class_attribute)  # Output: I am a class attribute
```

### The __init__ method 

The `__init__` method is a special method called a constructor. It is automatically invoked when a new instance of the class is created. It is used to initialize the instance attributes.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."

# Creating an instance of Person
person = Person("Alice", 30)
print(person.greet())  # Output: Hello, my name is Alice and I am 30 years old.
```

### Instance Methods

Instance methods are functions defined inside a class that operate on instances of the class. They take `self` as their first parameter, which is a reference to the instance calling the method.

```python
class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14159 * self.radius * self.radius

    def circumference(self):
        return 2 * 3.14159 * self.radius

# Creating an instance of Circle
circle = Circle(5)
print(circle.area())  # Output: 78.53975
print(circle.circumference())  # Output: 31.4159
```

### Class Methods and Static Methods

Class methods are methods that are bound to the class and not the instance. They take `cls` as their first parameter, which is a reference to the class. Static methods do not take any special first parameter and behave like plain functions but belong to the class's namespace.

```python
class MyClass:
    # Class method
    @classmethod
    def class_method(cls):
        return f"This is a class method. Class: {cls}"

    # Static method
    @staticmethod
    def static_method():
        return "This is a static method."

# Calling class method
print(MyClass.class_method())  # Output: This is a class method. Class: <class '__main__.MyClass'>

# Calling static method
print(MyClass.static_method())  # Output: This is a static method.
```

### Inheritance

Inheritance allows you to define a class that inherits all the methods and attributes from another class. The class being inherited from is called the parent class, and the class that inherits is called the child class.

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        raise NotImplementedError("Subclasses must implement this method")

class Dog(Animal):
    def speak(self):
        return f"{self.name} says Woof!"

class Cat(Animal):
    def speak(self):
        return f"{self.name} says Meow!"

# Creating instances of Dog and Cat
dog = Dog("Buddy")
cat = Cat("Whiskers")

print(dog.speak())  # Output: Buddy says Woof!
print(cat.speak())  # Output: Whiskers says Meow!
```

### Encapsulation

Encapsulation is the mechanism of restricting access to some of an object's components. This is usually done to prevent the accidental modification of data. In Python, you can denote private attributes and methods by prefixing their names with an underscore (`_`).

```python
class EncapsulatedClass:
    def __init__(self, value):
        self._value = value  # Private attribute

    def get_value(self):
        return self._value

    def set_value(self, new_value):
        self._value = new_value

# Creating an instance
obj = EncapsulatedClass(42)
print(obj.get_value())  # Output: 42
obj.set_value(100)
print(obj.get_value())  # Output: 100
```

### Polymorphism

Polymorphism allows methods to do different things based on the object it is acting upon. This is typically achieved by method overriding.

```python
class Shape:
    def area(self):
        raise NotImplementedError("Subclasses must implement this method")

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14159 * self.radius * self.radius

# List of shapes
shapes = [Rectangle(10, 5), Circle(7)]

for shape in shapes:
    print(shape.area())
```

Output:
```
50
153.93791
```

### Special Methods

Python classes can implement special methods that allow instances of the class to interact with Python’s built-in functions and operators. These methods are often referred to as “dunder” (double underscore) methods.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __repr__(self):
        return f"Point({self.x}, {self.y})"

    def __add__(self, other):
        return Point(self.x + other.x, self.y + other.y)

    def __eq__(self, other):
        return self.x == other.x and self.y == other.y

p1 = Point(1, 2)
p2 = Point(3, 4)

print(p1)          # Output: Point(1, 2)
print(p2)          # Output: Point(3, 4)
print(p1 + p2)     # Output: Point(4, 6)
print(p1 == p2)    # Output: False
```

### Summary

Classes in Python provide a powerful way to structure and organize your code. By understanding and utilizing OOP principles such as inheritance, encapsulation, and polymorphism, you can create complex and maintainable applications. Here's a recap of what we've covered:

1. **Defining a Class**: Use the `class` keyword to define a class and its methods and attributes.
2. **Creating an Instance**: Instantiate a class by calling it with required arguments.
3. **Instance Methods**: Functions that operate on instances of the class.
4. **Class Methods and Static Methods**: Methods bound to the class rather than instances.
5. **Inheritance**: Create new classes that inherit attributes and methods from existing classes.
6. **Encapsulation**: Restrict access to certain parts of an object.
7. **Polymorphism**: Methods that do different things based on the object.
8. **Special Methods**: Implement special methods to interact with Python’s built-in functions and operators.

## Iterators 

An iterator in Python is an object that contains a countable number of values and can be iterated upon, meaning you can traverse through all the values. Iterators are a fundamental concept in Python and are used extensively in various aspects of the language, such as loops, comprehensions, and generator functions.

### The Iterator Protocol

The iterator protocol in Python consists of two key methods:

1. **`__iter__()`**: This method returns the iterator object itself and is required to make an object iterable.
2. **`__next__()`**: This method returns the next value from the iterator. If there are no more items to return, it should raise the `StopIteration` exception.

### Creating an Iterator

Any object that implements these two methods (`__iter__()` and `__next__()`) is considered an iterator. Let's see a basic example of how to create an iterator:

```python
class MyIterator:
    def __init__(self, start, end):
        self.current = start
        self.end = end

    def __iter__(self):
        return self

    def __next__(self):
        if self.current >= self.end:
            raise StopIteration
        else:
            self.current += 1
            return self.current - 1

# Creating an instance of MyIterator
iterator = MyIterator(0, 5)

# Using the iterator
for value in iterator:
    print(value)
```

Output:
```
0
1
2
3
4
```

### Using Iterators

Iterators are used in various Python constructs, such as loops and comprehensions. The most common way to consume an iterator is with a `for` loop.

```python
# Using a for loop with an iterator
iterator = iter([1, 2, 3, 4, 5])
for value in iterator:
    print(value)
```

### The `iter()` Function

The `iter()` function is used to obtain an iterator from an iterable. An iterable is any Python object that implements the `__iter__()` method or has a `__getitem__()` method that takes sequential indexes starting from zero.

```python
# Creating an iterator from a list
my_list = [1, 2, 3, 4, 5]
iterator = iter(my_list)

# Using the iterator
print(next(iterator))  # Output: 1
print(next(iterator))  # Output: 2
print(next(iterator))  # Output: 3
```

### The `next()` Function

The `next()` function is used to manually iterate through the items of an iterator. It calls the iterator’s `__next__()` method.

```python
iterator = iter([1, 2, 3])
print(next(iterator))  # Output: 1
print(next(iterator))  # Output: 2
print(next(iterator))  # Output: 3
# print(next(iterator))  # Raises StopIteration
```

### Infinite Iterators

Iterators can be designed to produce an infinite sequence of values. For example, using the `itertools` module, you can create infinite iterators like `count`, `cycle`, and `repeat`.

```python
import itertools

# Infinite iterator using count
counter = itertools.count(start=0, step=2)
print(next(counter))  # Output: 0
print(next(counter))  # Output: 2
print(next(counter))  # Output: 4

# Infinite iterator using cycle
cycler = itertools.cycle(['A', 'B', 'C'])
print(next(cycler))  # Output: A
print(next(cycler))  # Output: B
print(next(cycler))  # Output: C
print(next(cycler))  # Output: A

# Infinite iterator using repeat
repeater = itertools.repeat('Hello', times=3)
print(next(repeater))  # Output: Hello
print(next(repeater))  # Output: Hello
print(next(repeater))  # Output: Hello
# print(next(repeater))  # Raises StopIteration
```

### Generators

Generators are a simpler way to create iterators using a function rather than creating a class. A generator function uses the `yield` keyword to produce a series of values.

```python
def my_generator(start, end):
    current = start
    while current < end:
        yield current
        current += 1

# Using the generator
for value in my_generator(0, 5):
    print(value)
```

Output:
```
0
1
2
3
4
```

### Summary

Iterators are a core concept in Python that allow you to traverse through all the values of a collection or sequence one at a time. By implementing the iterator protocol (`__iter__()` and `__next__()` methods), you can create your own custom iterators. Built-in functions like `iter()` and `next()`, along with constructs like generators, provide powerful and flexible ways to work with sequences in Python.

Key points to remember:
1. **Iterator Protocol**: Implement `__iter__()` and `__next__()` methods.
2. **`iter()` Function**: Obtain an iterator from an iterable.
3. **`next()` Function**: Retrieve the next item from an iterator.
4. **Generators**: Simplify the creation of iterators using `yield`.
5. **Infinite Iterators**: Create infinite sequences using `itertools`.

## Generators

Generators in Python are a special kind of iterator, defined using functions and the `yield` statement. They allow you to iterate over a sequence of values lazily, producing items only when they are needed rather than all at once. This can be very memory efficient and useful when working with large data sets or streams of data.

### Creating a Generator

Generators are created using functions that utilize the `yield` keyword. When a function contains a `yield` statement, it becomes a generator function and returns a generator object.

```python
def simple_generator():
    yield 1
    yield 2
    yield 3

# Creating a generator object
gen = simple_generator()

# Iterating over the generator
for value in gen:
    print(value)
```

Output:
```
1
2
3
```

### Generator Expression

A generator expression is a compact way to create a generator without the need for a separate function. It is similar to a list comprehension, but with parentheses instead of square brackets.

```python
# List comprehension
squares_list = [x * x for x in range(5)]
print(squares_list)  # Output: [0, 1, 4, 9, 16]

# Generator expression
squares_gen = (x * x for x in range(5))
print(squares_gen)  # Output: <generator object <genexpr> at 0x...>

# Iterating over the generator
for square in squares_gen:
    print(square)
```

Output:
```
0
1
4
9
16
```

### Advantages of Generators

1. **Memory Efficiency**: Generators produce items one at a time and only when needed, making them much more memory efficient than lists, especially for large data sets.
2. **Lazy Evaluation**: Items are computed on-the-fly, allowing for efficient processing of large or infinite sequences.
3. **Simpler Code**: Generators can lead to cleaner and more readable code compared to traditional iterator-based approaches.

### Using `yield` in Generators

The `yield` statement is used to produce a value and pause the generator function, saving its state for the next time it is called. When `next()` is called on the generator, it resumes execution from where it left off.

```python
def countdown(n):
    print("Starting countdown")
    while n > 0:
        yield n
        n -= 1

# Creating a generator object
gen = countdown(3)

# Iterating over the generator
for value in gen:
    print(value)
```

Output:
```
Starting countdown
3
2
1
```

### `yield` vs. `return`

The `yield` statement can be used multiple times in a generator function to produce a series of values, whereas `return` is used to exit the function and optionally provide a single value. When `return` is encountered in a generator function, it raises a `StopIteration` exception, signaling that the generator is exhausted.

```python
def my_generator():
    yield 1
    yield 2
    return  # This will raise StopIteration
    yield 3  # This will never be executed

gen = my_generator()
print(next(gen))  # Output: 1
print(next(gen))  # Output: 2
# print(next(gen))  # Raises StopIteration
```

### Generator Methods

Generators have several methods that can be used to control their execution:

1. **`next()`**: Retrieve the next item from the generator.
2. **`send(value)`**: Resume the generator and "send" a value that becomes the result of the current `yield` expression.
3. **`throw(type, value=None, traceback=None)`**: Raise an exception at the point where the generator was paused.
4. **`close()`**: Stop the generator and raise a `GeneratorExit` exception inside it.

```python
def my_generator():
    try:
        yield 1
        yield 2
        yield 3
    except GeneratorExit:
        print("Generator closed")

gen = my_generator()
print(next(gen))  # Output: 1
gen.close()       # Output: Generator closed
```

### Example: Fibonacci Sequence

Here’s an example of a generator function that produces an infinite sequence of Fibonacci numbers:

```python
def fibonacci():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

# Creating a generator object
fib = fibonacci()

# Generating the first 10 Fibonacci numbers
for _ in range(10):
    print(next(fib))
```

Output:
```
0
1
1
2
3
5
8
13
21
34
```

### Summary

Generators in Python provide a powerful and memory-efficient way to work with sequences of data. By using the `yield` keyword, you can create generator functions that produce values on-the-fly, allowing for lazy evaluation and efficient processing of large or infinite data sets. Generator expressions offer a compact syntax for creating generators, and the `yield` statement enables you to write clean and readable code for iterative processes.

Key points to remember:
1. **Generators**: Created using functions with the `yield` keyword.
2. **Generator Expression**: A concise way to create generators using parentheses.
3. **Memory Efficiency**: Generators are more memory efficient than lists.
4. **Lazy Evaluation**: Values are produced on-the-fly as needed.
5. **Generator Methods**: `next()`, `send()`, `throw()`, and `close()` control generator execution.

Multiprocessing in Python allows you to run multiple processes concurrently, leveraging multiple CPU cores for parallel execution. This is particularly useful for CPU-bound tasks, which can benefit significantly from parallel execution. The `multiprocessing` module provides a straightforward interface for creating and managing processes.

### Key Concepts and Components

1. **Process**: A separate instance of the Python interpreter with its own memory space.
2. **Queue**: A thread- and process-safe data structure used for inter-process communication.
3. **Pipe**: A simpler form of inter-process communication that establishes a connection between two processes.
4. **Pool**: A pool of worker processes that can be used to execute tasks in parallel.

### Creating a Process

You can create a new process by creating an instance of the `Process` class and passing a target function to it. Here's an example:

```python
import multiprocessing
import time

def worker_function(name):
    print(f"Worker {name} is starting")
    time.sleep(2)
    print(f"Worker {name} is done")

if __name__ == "__main__":
    # Creating processes
    process1 = multiprocessing.Process(target=worker_function, args=("One",))
    process2 = multiprocessing.Process(target=worker_function, args=("Two",))

    # Starting processes
    process1.start()
    process2.start()

    # Waiting for processes to finish
    process1.join()
    process2.join()

    print("Both processes are finished")
```

### Using a Queue

A `Queue` is useful for passing messages or data between processes. It is safe to use in a multiprocessing environment.

```python
import multiprocessing

def worker_function(queue):
    queue.put("Hello from worker")

if __name__ == "__main__":
    queue = multiprocessing.Queue()
    process = multiprocessing.Process(target=worker_function, args=(queue,))

    process.start()
    process.join()

    # Getting data from the queue
    message = queue.get()
    print(message)  # Output: Hello from worker
```

### Using a Pool

A `Pool` allows you to manage a pool of worker processes to which you can submit tasks. This is useful for distributing tasks among multiple worker processes.

```python
import multiprocessing

def square(x):
    return x * x

if __name__ == "__main__":
    with multiprocessing.Pool(processes=4) as pool:
        results = pool.map(square, [1, 2, 3, 4, 5])
        print(results)  # Output: [1, 4, 9, 16, 25]
```

### Using a Pipe

A `Pipe` allows two processes to communicate with each other. It provides two endpoints that can be used to send and receive data.

```python
import multiprocessing

def worker_function(conn):
    conn.send("Hello from worker")
    conn.close()

if __name__ == "__main__":
    parent_conn, child_conn = multiprocessing.Pipe()
    process = multiprocessing.Process(target=worker_function, args=(child_conn,))

    process.start()
    process.join()

    # Receiving data from the pipe
    message = parent_conn.recv()
    print(message)  # Output: Hello from worker
```

### Synchronization Primitives

The `multiprocessing` module provides several synchronization primitives such as `Lock`, `Event`, `Condition`, `Semaphore`, and `Barrier`.

#### Using a Lock

A `Lock` ensures that only one process at a time can access a shared resource.

```python
import multiprocessing
import time

def worker_function(lock, name):
    lock.acquire()
    try:
        print(f"Worker {name} is starting")
        time.sleep(2)
        print(f"Worker {name} is done")
    finally:
        lock.release()

if __name__ == "__main__":
    lock = multiprocessing.Lock()
    processes = [multiprocessing.Process(target=worker_function, args=(lock, i)) for i in range(4)]

    for process in processes:
        process.start()

    for process in processes:
        process.join()

    print("All processes are finished")
```

### Example: Parallel Computation of a Sum

Here's a more comprehensive example that uses multiple processes to compute the sum of a large list of numbers in parallel.

```python
import multiprocessing

def compute_sum(numbers, result, index):
    result[index] = sum(numbers)

if __name__ == "__main__":
    numbers = list(range(1, 1000001))
    num_processes = 4
    chunk_size = len(numbers) // num_processes

    processes = []
    result = multiprocessing.Array('i', num_processes)
    for i in range(num_processes):
        chunk = numbers[i * chunk_size:(i + 1) * chunk_size]
        process = multiprocessing.Process(target=compute_sum, args=(chunk, result, i))
        processes.append(process)
        process.start()

    for process in processes:
        process.join()

    total_sum = sum(result)
    print(f"Total sum: {total_sum}")
```

### Summary

Multiprocessing in Python is a powerful tool for parallel execution of tasks, leveraging multiple CPU cores to improve performance, especially for CPU-bound tasks. The `multiprocessing` module provides various components and synchronization primitives to facilitate inter-process communication and coordination.

Key points to remember:
1. **Process**: Create and manage separate instances of the Python interpreter.
2. **Queue**: Thread- and process-safe data structure for inter-process communication.
3. **Pipe**: Establish a connection between two processes.
4. **Pool**: Manage a pool of worker processes for parallel task execution.
5. **Synchronization Primitives**: Use `Lock`, `Event`, `Condition`, `Semaphore`, and `Barrier` for process synchronization.

## MultiThreading

Multithreading in Python allows you to run multiple threads concurrently within a single process, enabling you to perform multiple tasks simultaneously. However, due to Python's Global Interpreter Lock (GIL), true parallel execution of threads is limited, making threading most beneficial for I/O-bound tasks rather than CPU-bound tasks.

### Key Concepts and Components

1. **Thread**: A separate flow of execution within a process. Each thread shares the same memory space.
2. **GIL (Global Interpreter Lock)**: A mutex that protects access to Python objects, preventing multiple native threads from executing Python bytecodes simultaneously.
3. **Threading Module**: The `threading` module provides a high-level interface for creating and managing threads.

### Creating a Thread

You can create a new thread by creating an instance of the `Thread` class and passing a target function to it. Here's an example:

```python
import threading

def worker_function(name):
    print(f"Worker {name} is starting")
    print(f"Worker {name} is done")

# Creating and starting threads
thread1 = threading.Thread(target=worker_function, args=("One",))
thread2 = threading.Thread(target=worker_function, args=("Two",))

thread1.start()
thread2.start()

# Waiting for threads to finish
thread1.join()
thread2.join()

print("Both threads are finished")
```

### Using the `Thread` Class

You can also create a thread by subclassing the `Thread` class and overriding the `run` method.

```python
import threading

class MyThread(threading.Thread):
    def __init__(self, name):
        super().__init__()
        self.name = name

    def run(self):
        print(f"Worker {self.name} is starting")
        print(f"Worker {self.name} is done")

# Creating and starting threads
thread1 = MyThread("One")
thread2 = MyThread("Two")

thread1.start()
thread2.start()

# Waiting for threads to finish
thread1.join()
thread2.join()

print("Both threads are finished")
```

### Thread Synchronization

Python provides several synchronization primitives in the `threading` module to coordinate threads and prevent race conditions.

#### Lock

A `Lock` is a basic synchronization primitive that can be used to ensure that only one thread accesses a shared resource at a time.

```python
import threading
import time

def worker_function(lock, name):
    with lock:
        print(f"Worker {name} is starting")
        time.sleep(2)
        print(f"Worker {name} is done")

lock = threading.Lock()
threads = [threading.Thread(target=worker_function, args=(lock, i)) for i in range(4)]

for thread in threads:
    thread.start()

for thread in threads:
    thread.join()

print("All threads are finished")
```

#### RLock

A `RLock` (reentrant lock) allows a thread to acquire the same lock multiple times. This is useful in situations where the same thread needs to re-acquire a lock that it already holds.

```python
import threading

lock = threading.RLock()

def worker_function():
    with lock:
        print(f"{threading.current_thread().name} acquired lock")
        with lock:
            print(f"{threading.current_thread().name} acquired lock again")

thread = threading.Thread(target=worker_function)
thread.start()
thread.join()
```

#### Condition

A `Condition` allows threads to wait for some condition to be met before continuing execution.

```python
import threading

condition = threading.Condition()

def worker_function():
    with condition:
        print(f"{threading.current_thread().name} waiting for condition")
        condition.wait()
        print(f"{threading.current_thread().name} condition met, proceeding")

def signaler_function():
    with condition:
        print("Signaling all waiting threads")
        condition.notify_all()

# Creating threads
threads = [threading.Thread(target=worker_function) for _ in range(3)]
signaler = threading.Thread(target=signaler_function)

# Starting threads
for thread in threads:
    thread.start()

# Give workers time to start and wait
import time
time.sleep(1)

# Signaling threads to proceed
signaler.start()

# Waiting for all threads to finish
for thread in threads:
    thread.join()
signaler.join()
```

#### Semaphore

A `Semaphore` limits the number of threads that can access a resource concurrently.

```python
import threading
import time

semaphore = threading.Semaphore(2)

def worker_function(name):
    with semaphore:
        print(f"Worker {name} is starting")
        time.sleep(2)
        print(f"Worker {name} is done")

threads = [threading.Thread(target=worker_function, args=(i,)) for i in range(4)]

for thread in threads:
    thread.start()

for thread in threads:
    thread.join()

print("All threads are finished")
```

### Thread-Local Data

Thread-local data is data that is unique to each thread. The `local()` function creates a thread-local storage object.

```python
import threading

thread_local = threading.local()

def worker_function(name):
    thread_local.name = name
    print(f"Worker {thread_local.name} is running")

threads = [threading.Thread(target=worker_function, args=(i,)) for i in range(4)]

for thread in threads:
    thread.start()

for thread in threads:
    thread.join()
```

### Summary

Multithreading in Python allows for concurrent execution of threads within a single process, making it useful for I/O-bound tasks. The `threading` module provides tools for creating and managing threads, as well as synchronization primitives to coordinate their execution.

Key points to remember:
1. **Thread**: A separate flow of execution within a process.
2. **GIL**: Limits true parallel execution of threads in CPU-bound tasks.
3. **Threading Module**: Provides a high-level interface for thread management.
4. **Synchronization Primitives**: `Lock`, `RLock`, `Condition`, `Semaphore`, and thread-local data for coordinating thread execution.

## Some questions in Python (Interview Worthy)

**Q: What is the differnece between append and extend in python?**

In Python, both `append()` and `extend()` are methods used to add elements to a list, but they do so in different ways. Understanding the difference between these two methods is crucial for effective list manipulation.

###### `append()`

The `append()` method adds its argument as a single element to the end of the list. The argument can be any object, including another list. This method modifies the original list in place.

###### Example:

```python
my_list = [1, 2, 3]
my_list.append(4)
print(my_list)  # Output: [1, 2, 3, 4]

my_list.append([5, 6])
print(my_list)  # Output: [1, 2, 3, 4, [5, 6]]
```

In this example, `4` is added as a single element, and `[5, 6]` is added as a single list element.

###### `extend()`

The `extend()` method iterates over its argument, adding each element to the list, extending the list. The argument must be an iterable (like a list, tuple, set, or string). This method also modifies the original list in place.

###### Example:

```python
my_list = [1, 2, 3]
my_list.extend([4, 5, 6])
print(my_list)  # Output: [1, 2, 3, 4, 5, 6]

my_list.extend("abc")
print(my_list)  # Output: [1, 2, 3, 4, 5, 6, 'a', 'b', 'c']
```

In this example, each element of `[4, 5, 6]` and `"abc"` is added individually to the list.

###### Key Differences

1. **Argument Type**:
   - `append()`: Takes a single element (can be any object, including a list).
   - `extend()`: Takes an iterable (list, tuple, string, etc.).

2. **Modification**:
   - `append()`: Adds the argument as a single element at the end of the list.
   - `extend()`: Iterates over its argument and adds each element to the list.

3. **Resulting List**:
   - `append()`: The length of the list increases by 1, regardless of the argument's content.
   - `extend()`: The length of the list increases by the number of elements in the iterable.

###### When to Use Which

- Use `append()` when you want to add a single element to the list.
- Use `extend()` when you want to add multiple elements to the list and you have them in an iterable form.

###### Examples to Illustrate the Difference

###### Using `append()`:

```python
numbers = [1, 2, 3]
numbers.append(4)
print(numbers)  # Output: [1, 2, 3, 4]

numbers.append([5, 6])
print(numbers)  # Output: [1, 2, 3, 4, [5, 6]]
```

###### Using `extend()`:

```python
numbers = [1, 2, 3]
numbers.extend([4, 5, 6])
print(numbers)  # Output: [1, 2, 3, 4, 5, 6]

numbers.extend('abc')
print(numbers)  # Output: [1, 2, 3, 4, 5, 6, 'a', 'b', 'c']
```



