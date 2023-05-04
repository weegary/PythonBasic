# Must Learn Module 2: Pandas

Pandas is a Python package designed to work with tabular data easily and intuitively.<br/>

Table of Content: 
[Module Installation](#Module-Installation) <br/>
[Import Module](#Import-Module)  <br/>
[Data Structures](#Data-Structure) (DataFrame, Series)  <br/>
[Read and Write](#Read-and-Write) <br/>
[Selection](#Selection) <br/>
[Viewing Data](#Viewing-Data) <br/>
[Math Operations](#Math-Operations) <br/>
[Statistics](#Statistics) <br/>
[DataFrame Manipulation](#DataFrame-Manipulation) <br/>
[Query](#Query) <br/>
[Grouping](#Grouping) <br/>
[Handling Missing Data](#Handling-Missing-Data) <br/>
[Plot](#Plot) <br/>

## Module Installation

```
pip install pandas
```

## Import Module
```python
import pandas as pd
```

## Data Structures
|Dimensions|Name|Description|
|---|---|---|
|1|Series|1D labeled homogeneously-typed array|
|2|DataFrame|General 2D labeled, size-mutable tabular structure with potentially heterogeneously-typed column|

### DataFrame

I want to store passenger data of the Titanic. For a number of passengers, I know the name (characters), age (integers) and sex (male/female) data.

```python
df = pd.DataFrame(
    {
        "Name": [
            "Braund, Mr. Owen Harris",
            "Allen, Mr. William Henry",
            "Bonnell, Miss. Elizabeth",
        ],
        "Age": [22, 35, 58],
        "Sex": ["male", "male", "female"],
    }
)
```

### Series

Each column in a DataFrame is a Series
```python
df["Age"]

Output:
0    22
1    35
2    58
Name: Age, dtype: int64
```

You can create a Series from scratch as well:
```python
ages = pd.Series([22, 35, 58], name="Age")
```

### DateRange
```python
dates = pd.date_range("20130101", periods=6)

Output:
DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
               '2013-01-05', '2013-01-06'],
              dtype='datetime64[ns]', freq='D')
```

## Read and Write

DataFrame can be read from and written to several file formats, including .csv, .xlsx (Excel), .json, etc.

```python
# Read From Files
df_csv = pd.read_csv("file.csv")
df_xlsx = pd.read_excel("file.xlsx")
df_json = pd.read_json("file.json")
```

```python
# Write To Files
df.to_csv("file.csv")
df.to_excel("file.xlsx")
df.to_json("file.json")
```

## Selection

Use ```df.loc[r,c]``` and ```df.iloc[r,c]``` to select only rows, only columns or both.<br/>
Use ```df.at[r,c]``` and ```df.iat[r,c]``` to access a single value by row and column. <br/>
```r``` selects rows and ```c``` select columns.

```python
df = pd.DataFrame(
{"a" : [ 1,  2,  3,  4,  5], 
 "b" : [ 6,  7,  8,  9, 10], 
 "c" : [11, 12, 13, 14, 15],
 "d" : [16, 17, 18, 19, 20],
 "e" : [21, 22, 23, 24, 25]}, 
index = [0, 1, 2, 3, 4])

Output:
   a   b   c   d   e
0  1   6  11  16  21
1  2   7  12  17  22
2  3   8  13  18  23
3  4   9  14  19  24
4  5  10  15  20  25
```

Select rows 2 to 4
```python
df.iloc[2:5]

Output:
   a   b   c   d   e
2  3   8  13  18  23
3  4   9  14  19  24
4  5  10  15  20  25
```

Select all rows, with columns in position 0,2 and 4
```python
df.iloc[:,[1,2,4]]

Output:
    b   c   e
0   6  11  21
1   7  12  22
2   8  13  23
3   9  14  24
4  10  15  25
```

Select all columns between "b" and "d" (inclusive).
```python
df.loc[:, 'b':'d']

Output:
    b   c   d
0   6  11  16
1   7  12  17
2   8  13  18
3   9  14  19
4  10  15  20
```

Select rows meeting logical condition, and only the specific columns.
```python
df.loc[df['a'] > 3, ['a', 'c']]

Output:
   a   c
3  4  14
4  5  15
```

Select single value by index [row, column]
```python
df.iat[1, 2]

Output:
12
```

Select single value by label
```python
df.at[4, 'd'] 

Output:
20
```

## Viewing data

To view a specified number of rows from the top.
```python
df.head(2)

Output:
   a  b   c   d   e
0  1  6  11  16  21
1  2  7  12  17  22
```

To view a specified number of rows from the bottom.
```python
df.tail(2)

Output:
   a   b   c   d   e
3  4   9  14  19  24
4  5  10  15  20  25
```

To view the index of DataFrame.
```python
df.index

Output:
Int64Index([0, 1, 2, 3, 4], dtype='int64')
```

To view the columns of DataFrame.
```python
df.columns

Output:
ndex(['a', 'b', 'c', 'd', 'e'], dtype='object')
```

To view the basic statistics of DataFrame.
```python
df.describe()

Output:
              a          b          c          d          e
count  5.000000   5.000000   5.000000   5.000000   5.000000
mean   3.000000   8.000000  13.000000  18.000000  23.000000
std    1.581139   1.581139   1.581139   1.581139   1.581139
min    1.000000   6.000000  11.000000  16.000000  21.000000
25%    2.000000   7.000000  12.000000  17.000000  22.000000
50%    3.000000   8.000000  13.000000  18.000000  23.000000
75%    4.000000   9.000000  14.000000  19.000000  24.000000
max    5.000000  10.000000  15.000000  20.000000  25.000000
```

To view the technical information about DataFrame.
```python
df.info()

Output:
<class 'pandas.core.frame.DataFrame'>
Int64Index: 5 entries, 0 to 4
Data columns (total 5 columns):
 #   Column  Non-Null Count  Dtype
---  ------  --------------  -----
 0   a       5 non-null      int64
 1   b       5 non-null      int64
 2   c       5 non-null      int64
 3   d       5 non-null      int64
 4   e       5 non-null      int64
dtypes: int64(5)
memory usage: 412.0 bytes
```

To view the number of rows and columns in DataFrame.
```python
df.shape

Output:
(5,5)
```

## Math Operations

Adding one value to every element of DataFrame.
```python
df = pd.DataFrame(
{"a" : [ 1,  2,  3,  4,  5], 
 "b" : [ 6,  7,  8,  9, 10], 
 "c" : [11, 12, 13, 14, 15],
 "d" : [16, 17, 18, 19, 20],
 "e" : [21, 22, 23, 24, 25]})
 
df+1  # Add 1 to every element

Output: 
   a   b   c   d   e
0  2   7  12  17  22
1  3   8  13  18  23
2  4   9  14  19  24
3  5  10  15  20  25
4  6  11  16  21  26
```

Adding a dataframe to another dataframe.
```python
df_add = pd.DataFrame(
{"a" : [ 0,  0,  0,  0,  0], 
 "b" : [ 0,  0,  0,  0,  0], 
 "c" : [ 0,  0, 20,  0,  0],
 "d" : [ 0,  0,  0,  0,  0],
 "e" : [ 0,  0,  0,  0,  0]})

df+df_add # Adding two dataframes

Output: 
   a   b   c   d   e
0  1   6  11  16  21
1  2   7  12  17  22
2  3   8  33  18  23
3  4   9  14  19  24
4  5  10  15  20  25
```

Applying a function. <br/>
In this example, the (max value - min value) of every column is calculated.

```python
df.apply(lambda x: x.max() - x.min())

Output: 
a    4
b    4
c    4
d    4
e    4
dtype: int64
```

## Statistics

Most of the statistic functions can be used to calculate the value for either all row (x-axis) or all columns (y-axis).
The default is for all row. <br/>

To calculate sum of all row

```python
df.sum()  # or df.sum(0)

Output: 
a     15
b     40
c     65
d     90
e    115
dtype: int64
```

To calculate the sum of all columns
```python
df.sum(1)

Output:
0    55
1    60
2    65
3    70
4    75
dtype: int64
```

Besides ```df.sum()```, you can also use: <br/>
```df.min()``` to get the minimum value <br/>
```df.max()``` to get the maximum value <br/>
```df.mean()``` to get the mean value <br/>
```df.median()``` to get the median value <br/>
```df.var()``` to get the variance <br/>
```df.std()``` to get the standard deviation <br/>

The quantitles can be obtained by using ```df.quantile()```

```python
df.quantile()  # default 0.5

Output:
df.quantile()
Output: 
a     3.0
b     8.0
c    13.0
d    18.0
e    23.0
Name: 0.5, dtype: float64
```

You can assign 0.25 or 0.75 to get the corresponding quantile.

``` python
df.quantile(0.25)

Output:
a     2.0
b     7.0
c    12.0
d    17.0
e    22.0
Name: 0.25, dtype: float64
```

Or you can assign an array to get all the quantiles:
```python
df.quantile([0.25, 0.5, 0.75])

Output:
        a    b     c     d     e
0.25  2.0  7.0  12.0  17.0  22.0
0.50  3.0  8.0  13.0  18.0  23.0
0.75  4.0  9.0  14.0  19.0  24.0
```

## DataFrame Manipulation

### Change layout

Append rows of DataFrames
```python
df2 = pd.DataFrame(
{"a" : [ 31, 32, 33], 
 "b" : [ 34, 35, 36], 
 "c" : [ 37, 38, 39],
 "d" : [ 40, 41, 42],
 "e" : [ 43, 44, 45]}, 
 index=[5,6,7])

new_df = pd.concat([df,df2])

Output: 
    a   b   c   d   e
0   1   6  11  16  21
1   2   7  12  17  22
2   3   8  13  18  23
3   4   9  14  19  24
4   5  10  15  20  25
5  31  34  37  40  43
6  32  35  38  41  44
7  33  36  39  42  45
```

Append columns of DataFrames
```python
df3 = pd.DataFrame(
{"f" : [ 26,  27,  28,  29, 30], 
 "g" : [31, 32, 33, 34, 35]})
 
new_df = pd.concat([df,df3])

Output:
   a   b   c   d   e   f   g
0  1   6  11  16  21  26  31
1  2   7  12  17  22  27  32
2  3   8  13  18  23  28  33
3  4   9  14  19  24  29  34
4  5  10  15  20  25  30  35
```

Drop columns from DataFrame
```python
df.drop(columns=["b","d"])

Output: 
   a   c   e
0  1  11  21
1  2  12  22
2  3  13  23
3  4  14  24
4  5  15  25
```

Transpose
```python
df.T

Output:
    0   1   2   3   4
a   1   2   3   4   5
b   6   7   8   9  10
c  11  12  13  14  15
d  16  17  18  19  20
e  21  22  23  24  25
```

### Combine Data Sets
```python
df4 = pd.DataFrame(
{"X":["A","B","C"],
 "Y":[1,2,3]})
 
df5 = pd.DataFrame(
{"X":["A","B","D"],
 "Z":["T","F","T"]})
```

Join matching rows from df5 to df4.
```python
pd.merge(df4,df5,how='left', on='X')

Output: 
   X  Y    Z
0  A  1    T
1  B  2    F
2  C  3  NaN
```

Join matching rows from df4 to df5.
```python
pd.merge(df4,df5,how='right', on='X')

Output: 
   X    Y  Z
0  A  1.0  T
1  B  2.0  F
2  D  NaN  T
```

Join data. Reatain only rows in both sets.
```python
pd.merge(df4,df5,how='inner', on='X')

Output: 
   X  Y  Z
0  A  1  T
1  B  2  F
```

Join data. Retain all values, all rows.
```python
pd.merge(df4,df5,how='outer', on='X')

Output: 
   X    Y    Z
0  A  1.0    T
1  B  2.0    F
2  C  3.0  NaN
3  D  NaN    T
```

All rows in df4 that have a match in df5. (Union)
```python
df4[df4.X.isin(df5.X)]

Output: 
   X  Y
0  A  1
1  B  2
```

All rows in df4 that do not have a match in df5. (Difference)
```python
df4[~df4.X.isin(df5.X)]

Output: 
   X  Y
2  C  3
```

### Sorting

Sort by values
```python
df.sort_values("a", ascending=False)

Output:
   a   b   c   d   e
4  5  10  15  20  25
3  4   9  14  19  24
2  3   8  13  18  23
1  2   7  12  17  22
0  1   6  11  16  21
```

Sort by index
```python
df.sort_index(ascending=False)

Output:
   a   b   c   d   e
4  5  10  15  20  25
3  4   9  14  19  24
2  3   8  13  18  23
1  2   7  12  17  22
0  1   6  11  16  21
```

## Query

```python
expression = "a<5 and b>7"
df.query(expression)

Output: 
   a  b   c   d   e
2  3  8  13  18  23
3  4  9  14  19  24
```

## Grouping

Usually, you can calculate the sum, mean or size of grouping data.

```python
df_animal = pd.DataFrame(
{"type":["cat","cat","dog","dog"],
 "name":["hello","doraemon","louis","rocky"],
 "weight":[5,7,13,8]})
 
df_animal.groupby("type").mean()  # The mean of every numerical dimension of every type

Output: 
      weight
type        
cat      6.0
dog     10.5

df_animal.groupby("type").size()  # The count of every type

Output: 
type
cat    2
dog    2
dtype: int64
```

## Handling Missing Data
```python
import numpy as np
df = pd.DataFrame({
     "A": [5,2,4,6,np.nan],
     "B": [6,3,2,1,5],
     "C": [np.nan,3,5,6,1],
     "D": [2,1,1,4,3] })

Output:
     A  B    C  D
0  5.0  6  NaN  2
1  2.0  3  3.0  1
2  4.0  2  5.0  1
3  6.0  1  6.0  4
4  NaN  5  1.0  3
```

To remove the rows having NaN value
```python
df.dropna()

Output: 
     A  B    C  D
1  2.0  3  3.0  1
2  4.0  2  5.0  1
3  6.0  1  6.0  4
```

To replace the NaN with a value
```python
df.fillna(-1)

Output: 
     A  B    C  D
0  5.0  6 -1.0  2
1  2.0  3  3.0  1
2  4.0  2  5.0  1
3  6.0  1  6.0  4
4 -1.0  5  1.0  3
```

To get the boolean mask where valuea are NaN:
```python
df.isna()

Output: 
       A      B      C      D
0  False  False   True  False
1  False  False  False  False
2  False  False  False  False
3  False  False  False  False
4   True  False  False  False
```

## Plot

Together with ```matplotlib``` module, pandas' DataFrame can be visualized easily.

```python
import matplotlib.pyplot as plt
df.plot(kind="line") # Line Plot
```

Code above generates a line plot for A to D.
![image](https://user-images.githubusercontent.com/51909547/236201077-8a2a8a17-5fab-4a44-b1e9-12685a2c6d35.png)

```python
df.plot(kind="scatter",x="A",y="B")
```
Code above creates a scatter plot of A to B.
![image](https://user-images.githubusercontent.com/51909547/236201239-4107bc05-4e43-40a8-b11a-8dec12c8a064.png)

Different types of chart can be drawn from DataFrame, including bar chart, pie chart, histogram, etc.
