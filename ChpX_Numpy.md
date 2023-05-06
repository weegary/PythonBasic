# Must Learn Module 1: Numpy

## Numpy Installation
```python
pip install numpy
```

## Import Module
```python
import numpy as np
```

## Array Creation
```python

# Set an array directly
np.array([1,2,3,4])              # create a 1-D array [1,2,3,4]
np.array([[1,2,3,4],[5,6,7,8]])  # create a 2-D array [[1,2,3,4],
                                 #                     [5,6,7,8]]

# Create an array from 0 to 10, the interval is 2
np.arange(0,11,2)     # create array [0,2,4,6,8,10], not include 11

# Create an array from 1 to 15, with 3 values only (the interval is evenly divided into 3)
np.linspace(1,15,3)   # create array [1,8,15]

# Create an array with all zeros, the dimension is 3 x 2
np.zeros((3,2))

# Create an array with all ones, the dimension is 4 x 2
np.ones((4,2))
```

## Array Properties
```python
import numpy as np
list_data = [[1,2,3,4,5],[6,7,8,9,10]]
na = np.array(list_data)
print(na)
print(na.ndim)
print(na.shape)
print(na.size)

Output:
[[ 1  2  3  4  5]
 [ 6  7  8  9 10]]
2
(2,5)
10
```

## Reshape Array
```python
import numpy as np
adata = np.arange(1,17)
print(adata)
bdata = adata.reshape(4,4)
print(bdata)

Output:
[ 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16]
[[ 1  2  3  4]
 [ 5  6  7  8]
 [ 9 10 11 12]
 [13 14 15 16]]
```

## Transpose
```python
import numpy as np
z = np.array([(1,2,3,4),(8,16,24,32)])
print(z)

Output:
[[ 1 2 3 4]
 [ 8 16 24 32]]
 
 print(z.transpose())  # or z.T
 [[ 1  8]
  [ 2 16]
  [ 3 24]
  [ 4 32]] 
```

## Getting The Values From Numpy Array
Sliding index are used to get the values from a numpy array.
To illustrate, we create a numpy arange and named it as 'data'.
```python
import numpy as np
data = np.arange(0,10)
```

You can type an index to get the item from an array, e.g., ```array[index]``` .<br/>

```data[0]``` index 0 to get the first item, which is 0.<br/>
```data[4]``` index 4 to get the fifth item, which is 4.<br/>
```data[-1]``` index -1 to get the last item, which is 9.<br/>
```data[-2]``` index -2 to get the second last item, which is 8.<br/>

You can type two index to get multiple values from an array, e.g., ```array[start_index:end_index]```. <br/>

```data[0:2]``` index 0:2 to get the first 2 item (index 0 and index 1 only), which are 0,1.<br/>
```data[4:8]``` index 4:8 to get the item from index 4 to index 7 (index 8 is excluded), which are 4,5,6,7.<br/>
```data[-3:-1]``` index -3:-1 to get the item from index -3 (last 3rd) to index -2 (last 2nd), which are 7,8.<br/>
```data[:5]``` index :5 to get the item from the beginning to index 4, which are 0,1,2,3,4.<br/>
```data[5:]``` index 5: to get the item from index 5 to the end, which are 5,6,7,8,9.<br/>

You can type two index with one interval to get multiple values with different step from an array, e.g., ```array[start_index:end_index:interval]```. <br/>

```data[0:5:2]``` to get the items 0,2,4.<br/>
```data[4:9:3]``` to get the item 4,7.<br/>
```data[5:1:-1]``` to get the item 5,4,3,2. (descending order)<br/>
```data[:1:-2]``` to get the item 9,7,5,3. (descending order)<br/>

Similary, to get the values from two-dimensional array, just use comma ',' to separate the index.
```python
data[0,2]
data[1:5,0:]
data[0:5:2,9:2:-1]
```

## Generate Random Numbers

|Code|Functions|
|---|---|
|```rand(d0,d1,...,dn)```|According to the dimensions, generate random floating numbers between 0 to 1.|
|```randn(d0,d1,...,dn)```|According to the dimensions, generate random floating numbers based on normal distribution.|
|```randint(min,max,[d0,d1,...,dn])```|According to the dimensions, generate random integer numbers between min and max (not included max).|

## Frequent used functions

To be continued...

Trigonometric functions
Matrix
