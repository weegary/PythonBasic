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

A list can contain different type of data, it could be string, integer, boolean, or even another list.
```python
str_list = ["Kevin","Gary","Daniel"]
int_list = [32,28,27]
list_list = [[1,3],[2,4],[5,8]]
```

List items are indexed, the first item has index [0], the second item has index [1] ...
the last item has index [-1], the last second item has index [-2] ...
```python
name_list = ["Kevin","Gary","Daniel"]
print(name_list[0])  # Kevin
print(name_list[-1]) # Daniel
```

Slicing is indexing syntax that extracts a portion from a list.
[m:n] returns the portion of the list:
- m<=x<n
- starting with position m
- up to but not including n
- negative indexing can also be used
```python
name_list = ["Kevin","Gary","Daniel"]
print(name_list[0:2])    # ['Kevin', 'Gary']
print(name_list[-2:-1])  # ['Gary']
print(name_list[-2:])    # ['Gary','Daniel']
print(name_list[:2])     # ['Kevin','Gary']

List items are ordered, changeable, and allow duplicate values.
- The items have a defined order, and that order will not change. If a new item is added to the list, it will be placed at the end of the list.
- The items can be changed, added, or removed after a list has been created.
- Since lists are indexed, lists can have items with same value.

The number of items in a list can be obtained by using the len() function.
```python
name_list = ["Kevin","Gary","Daniel"]
print(len(name_list))

output:
3
```

## Tuple

## Dict
