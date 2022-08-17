# Chapter 1

## Basic coding introduction

Here is your first code:

```python
import matplotlib.pyplot as plt

x = [1,2,3]
y = [4,5,10]

plt.plot(x, y, linestyle = 'solid', color = 'black', marker = 'o')
```
![image](https://user-images.githubusercontent.com/51909547/177478703-270efb9f-8073-455a-af65-af034c1a3a2a.png)

First, we are going to introduce the variable.
There are 2 variables in this code, which are x and y.

```python
x = [1,2,3]
y = [4,5,10]
```

x is __a list__ contains __three integer numbers__ 1,2 and 3, and
y is __a list__ contains __three integer numbers__ 4,5 and 10.

We can change the code, and rerun the program.
```python
y = [6,8,3]
```
![image](https://user-images.githubusercontent.com/51909547/177485370-4b4dad4a-3211-43d2-b9b7-0b9ae571edb8.png)

We can add more number into the x and y lists, and rerun the program. <br/>
Note that the length of the x and y should be identical.
```python
x = [1,2,3,4,5,6]
y = [6,8,3,1,5,10]
```
![image](https://user-images.githubusercontent.com/51909547/177485784-1a698ceb-1c1c-4e7e-87d9-44470b7be590.png)

In the first code, we notice that there are some code written in the quotation marks
```python
linestyle = 'solid' 
color = 'black'
marker = 'o'
```
In python, these are the string variable. <br/>
Strings in pthon are surrounded by either single quotation marks, or double quotation marks. <br/>
<br/>
You can rewrite the first code like this, and you will still get the same result.
```python
import matplotlib.pyplot as plt

x = [1,2,3,4,5,6]
y = [6,8,3,1,5,10]

linestyle_variable = 'solid' 
color_variable = 'black'
marker_variable = 'o'
plt.plot(x, y, linestyle = linestyle_variable, color = color_variable, marker = marker_variable)
```

Matplotlib is a python library for creating visualizations.
There are different line styles can be used, including solid('-'), dashed('--'), dashdot('-.') and dotted(':').

You can change the linestyle_variable to get a new plot.
```python
linestyle_variable = 'dashed' 
```
![image](https://user-images.githubusercontent.com/51909547/177489313-2f4f3d9b-f105-48f6-8cca-e9acff616385.png)

Or you can use the short form of the type, showing in the bracker. <br/>
For example, using '-.' to represent dashdot line.
```python
linestyle_variable = '-.' 
```
![image](https://user-images.githubusercontent.com/51909547/177489597-165f476c-8b5b-4da6-b3ad-852eade4a5b1.png)
