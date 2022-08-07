# Chapter 8: Control Flow - If...Else

- syntax: ```if condition:```
- The condition must be something returns True or False.
- The codes inside the if statement cannot be aligned with the first line of the if statement, it should be one indentation different from the first line.
- To escape the for loop, just simply align the code with the first line of if statement.

## Example 1 - If

```python
num = [5, 11, 14, 0, 6, 0, 8] # define the array
for item in num:
    if item != 0:
        print(1.0/item)

output:
0.2
0.0909090909091
0.0714285714286
0.166666666667
0.125
```

## Example 2 - If ... Elif...

```python
scores = [23,60,41,69,85,70,94]
for score in scores:
    if score < 60:
        print("F")
    elif score <70:
        print("D")
    elif score <80:
        print("C")
    elif score <90:
        print("B")
    elif score <=100:
        print("A")

output:
F
D
F
D
B
C
A
```

## Example 3 - If ... Else...

```python
scores = [23,60,41,69,85,70,94]
for score in scores:
    if score < 60:
        print("Fail")
    else:
        print("Pass")

output:
Fail
Pass
Fail
Pass
Pass
Pass
Pass
```
