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
