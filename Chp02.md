# Chapter 02: Data Types

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

```str(variable)``` can be used to convert number to string
```python
name = 'Gary' # String
age = 20      # Number
print(name + ' is ' + str(age))

Output:
Gary is 20
```

### String Process

|Function|Describe|Result|
|---|---|---|
|len(string)|Get the length of string|12|
|string.capitalize()|Capitalize the first character of string|Gary is cool|
|string.lower()|Lower case the whole string|gary is cool|
|string.split()|Split the string with specific character|>>>name.split('a')<br/>['G','ry is cool']|
|string.title()|Capitalize first character of every word|Gary Is Cool|
|string.upper()|Upper case the whole string|GARY IS COOL|

### Splitting the String

If you want to split the string by using "one character", you can just use the ```split``` function.
```python
names = "Gary Kevin Daniel"
x,y,z = names.split() # Split by blank

Output:
x = "Gary"
y = "Kevin"
z = "Daniel"
```

You can also split the string by using "escape character".
```python
names = "Gary\tKevin\tDaniel"
x,y,z = names.split('\t')

Output:
x = "Gary"
y = "Kevin"
z = "Daniel"
```

Here are some escape characters used in Python:
|Code|Describtion|
|---|---|
|\\'|Single Quote|
|\\ \ |Backslash|
|\n|New Line|
|\r|Carriage Return(Enter)|
|\t|Tab|
|\b|Backspace|
|\f|Form Feed|

## Number

Number are used to save numerical value. There are int (integer), float (floating point number) and complex (complex number). <br/>

```python
x = 10       # int
y = 3.1415   # float
z = 6j       # complex
```

```int(variable)``` can be used to convert string into integer
```python
age = '20'      # Variable with quotations is string, not number
print(int(age) + 5)

Output:
25
```

```float()``` and ```complex()``` can be used in similar way.

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

List is created using square brackets [ ], it is a collection variable storing multiple items, the length and the items of a list can be modified.

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
name_list = ['Kevin','Gary','Daniel']
print(name_list[0:2])    # ['Kevin', 'Gary']
print(name_list[-2:-1])  # ['Gary']
print(name_list[-2:])    # ['Gary','Daniel']
print(name_list[:2])     # ['Kevin','Gary']
```
         
List items are ordered, changeable, and allow duplicate values.
- The items have a defined order, and that order will not change. If a new item is added to the list, it will be placed at the end of the list.
- The items can be changed, added, or removed after a list has been created.
- Since lists are indexed, lists can have items with same value.

The number of items in a list can be obtained by using the len() function.
```python
name_list = ['Kevin','Gary','Daniel']
print(len(name_list))

output:
3
```

## Tuple

Tuple is created using round brackets ( ), it is a collection variable storing multiple items, the length and the items of a list is fixed and cannot be changed. You can call the item using index just like list.

```python
name_tuple = ('Kevin','Gary','Daniel')
name_tuple[0] = "Alex"   # error! 'tuple' object does not support item assignment
```         

## Dictionary

Dictionary is created using curly brackets { }, it stores data values in "key:value" pairs, therefore, it cannot have two items with the same key. The items of a dictionary are changeable, and ou can call the item using key.
* Since Python 3.7, dictionaries are ordered.

```python
person_dictionary = {
         'Name':'Gary',
         'Age':18,
         'Sex':'Male'}
print(person_dictionary['Name']) 

output:
'Gary'
```

<< Previous: [Basic Coding Introduction](Chp01.md)  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Next: [DateTime / TimeDelta / Date / Time](Chp03.md)>>
