# Must Learn Module 4: Matplotlib

Matplotlib is a Python package for plotting 2D chart. Several types of chart can be generated, such as plots, histograms, power spectra, bar charts, error charts, scatterplots, etc., with just a few lines of codes.


## Module Installation
```
pip install matplotlib
```

## Import Module
```python
import matplotlib.pyplot as plt
```

## A Simple Example
```python
import matplotlib.pyplot as plt

x = [1,2,3]
y = [4,5,10]

# Create a figure containing a single axes.
fig, ax = plt.subplots()  

# Plot some data on the axes.
ax.plot(x, y, linestyle = 'solid', color = 'black', marker = 'o') 

# Display the figure
plt.show() 
```
![image](https://user-images.githubusercontent.com/51909547/177478703-270efb9f-8073-455a-af65-af034c1a3a2a.png)

## Parts of a Figure

Here are some components of a Matplotlib Figure.<br/>
![matplotlib_component](https://github.com/weegary/PythonBasic/assets/51909547/250fff61-c167-48f9-91b2-f028176f3707)

### Figure
The **whole** figure. The Figure keeps track of all the child ```Axes```, a group of 'special' Artists (titles, figure legends, colorbars, etc), and even nested subfigures.<br/>

The easiest way to create a new Figure is with pyplot:
```python
fig = plt.figure()  # an empty figure with no Axes
fig, ax = plt.subplots()  # a figure with a single Axes
fig, axs = plt.subplots(2, 2)  # a figure with a 2x2 grid of Axes
# a figure with one axes on the left, and two on the right:
fig, axs = plt.subplot_mosaic([['left', 'right-top'],
                               ['left', 'right_bottom]])
```
It is often convenient to create the Axes together with the Figure, but you can also manually add Axes later on. <br/>

### Axes

An Axes is an Artist attached to a Figure that contains a region for plotting data, and usually includes two (or three in the case of 3D) ```Axis``` objects (be aware of the difference between **Axes** and **Axis**) that provide ticks and tick labels to provide scales for the data in the Axes. Each ```Axes``` also has a title (set via ```set_title()```), an x-label (set via ```set_xlabel()```), and a y-label set via ```set_ylabel()```).<br/>

The ```Axes``` class and its member functions are the primary entry point to working with the OOP interface, and have most of the plotting methods defined on them (e.g. ```ax.plot()```, shown above, uses the ```plot``` method)

### Axis

These objects set the scale and limits and generate ticks (the marks on the Axis) and ticklabels (strings labeling the ticks). The location of the ticks is determined by a ```Locator``` object and the ticklabel strings are formatted by a ```Formatter```. The combination of the correct ```Locator``` and ```Formatter``` gives very fine control over the tick locations and labels.

## Example 01: Setting titles 

```python
import matplotlib.pyplot as plt

x = [0,1,2]
y1 = [0,2,4]
y2 = [4,2,0]

# Create a figure containing a single axes.
fig, ax = plt.subplots()  

# Plot some data on the axes.
ax.plot(x, y1, label='y1')  # Plot x-y1, label the line as y1 
ax.plot(x, y2, label='y2')  # Plot x-y2, label the line as y2
ax.legend()                 # Set the Legend
plt.xlabel('X')             # Set the title of x-axis to 'X'
plt.ylabel('Y')             # Set the title of y-axis to 'Y'
plt.title('X-Y Diagram')    # Set the title of Axes

# Display the figure
plt.show()
```

The size of the figure can be set, by changing the code ```fig, ax = plt.subplots()``` to ```fig, ax = plt.subplots(figsize=(5,5))```, the number (5,5) represents the width and height in inches.<br/>

If you want to change the font properties of title, you can change the code ```plt.title('X-Y Diagram')``` to ```plt.title('X-Y Diagram', fontsize=14, fontweight='bold')```.

![image](https://github.com/weegary/PythonBasic/assets/51909547/78d2d61d-16bb-490b-9f7c-05349e21584a)

## Example 02: Subplots

```python
x = [0,1,2,3,4]
y1 = [0,2,4,6,8]
y2 = [8,6,4,2,0]
y3 = [4,2,0,2,4]
y4 = [0,2,4,2,0]

import matplotlib.pyplot as plt
ax = plt.subplot(2,2,1) # Create a 2x2 subplots, the first diagram (top left)
ax.plot(x,y1, color='green') # Set the color of line to green
plt.xlabel('X')
plt.ylabel('Y1')
plt.title('X-Y1 Diagram')

ax2 = plt.subplot(2,2,2) # Create a 2x2 subplots, the second diagram (top right)
ax2.plot(x,y2, color='blue', linestyle='--') # Setting the linestyle to dashed
plt.xlabel('X')
plt.ylabel('Y2')
plt.title('X-Y2 Diagram')

ax3 = plt.subplot(2,2,3)
ax3.plot(x,y3, color='red', marker='o') # Set the marker to rounded shape
plt.xlabel('X')
plt.ylabel('Y3')
plt.title('X-Y3 Diagram')

ax4 = plt.subplot(2,2,4)
ax4.plot(x,y4, color='orange')
plt.xlabel('X')
plt.ylabel('Y4')
plt.title('X-Y4 Diagram')

plt.subplots_adjust(wspace = 0.3) # The width of the padding between subplots, as a fraction of the average Axes width.
plt.subplots_adjust(hspace = 0.8) # The height of the padding between subplots, as a fraction of the average Axes height.
```

Beware that ```plt.subplot()``` will return two values: ```fig, ax```. <br/>
But ```plt.subplot(2,2,1)``` will return only one value: ```ax```.

![image](https://github.com/weegary/PythonBasic/assets/51909547/949acdfd-6b50-497c-89ed-48836dd8d3ea)

## Examples 03: Different types of chart

It is easy to learn matplotlib from examples, you can [find more examples from the official site](https://matplotlib.org/stable/gallery/index.html).

```python
x = [0,1,2,3,4]
y1 = [0,2,4,6,8]
y2 = [0.7,1.5,4.5,5.7,7.3]

import matplotlib.pyplot as plt

fig1, ax1 = plt.subplots()
ax1.plot(x,y1)       # Line plot
ax1.scatter(x,y2)    # Scatter plot

fig2, ax2 = plt.subplots()
ax2.boxplot((y1,y2)) # Box plot
```

![image](https://github.com/weegary/PythonBasic/assets/51909547/467339e8-8b60-4a6e-83ab-d7ab4f503fbb)
![image](https://github.com/weegary/PythonBasic/assets/51909547/d07e24f0-1be6-4084-ac6d-23dae276c6d8)

## Examples 04: Saving the figure

```pyhon
plt.savefig('Figure.png')     # The figure will be saved at where the code locates
plt.savefig(r'D:\Figure.png')  # The figure will be saved at specific location
```

## More Details

For more details of Figures and backends, see [Creating, viewing, and saving Matplotlib Figures](https://matplotlib.org/stable/users/explain/figures.html#figure-explanation). <br/>
Note that many [Matplotlib backends](https://matplotlib.org/stable/users/explain/backends.html) support zooming and panning on figure windows.

## Reference:
1. https://matplotlib.org/stable/
2. https://realpython.com/python-matplotlib-guide/
