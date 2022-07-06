# Chapter 2: Python Fundemental - Data Types

The basic data types used in Python are:
- String
- Number
- Boolean
- List
- Tuple
- Dictionary
- Set

## String

String represents word or character, a string can be made of letters, numbers or symbols. <br/>
Strings in python are surrounded by either single quotation marks, or double quotation marks. <br/>
Using a '+' operator can combine two strings. <br/>

```python
first_name = 'Gary'
last_name = 'Wee'
full_name = first_name +' ' + last_name
print(full_name)

output:
Gary Wee
```
// Learn More: String Processing

## Number

Number are used to save numerical value. There are int (integer), float (floating point number) and complex (complex number). <br/>

```python
x = 10       # int
y = 3.1415   # float
z = 6j       # complex
```
## Boolean

Boolean is a data type that can only have two possible values: True or False.

```python
true_variable = True
false_variable = False
```

When two values are compared, the expression is evaluated and Python returns the Boolean answer.

```python
print(10>9)   # True
print(10==9)  # False
print(10<9)   # False
```

<hr>

There are 4 data types in Python used to store collections of data, which are List, Tuple, Dictionary, and Set.

## List

List is created using square braker [ ], it is a collection variable storing multiple items, the length and the items of a list can be modified.

```python
name_list = ["Kevin","Gary","Daniel"]
```

All of the items in a list, should be the same data types, it could be string, integer, or even another list.
```python
str_list = ["Kevin","Gary","Daniel"]
int_list = [32,28,27]
list_list = [[1,3],[2,4],[5,8]]
```

## Tuple

## Dict
