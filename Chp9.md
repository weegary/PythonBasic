# Chapter 9: Control Flow - Break and Continue

```break``` and ```continue``` are usually used in for or while loops.

## Break
```break``` statement is used to stop the iteration, and totally escape from the loop.

E.g., if the item is not zero then print it, when the item is 0 then execute the break statement.

```python
foo = [5, -11, 14, 0, -6, 0, 8]
for item in foo:
    if item==0:
        print('zero is found in the list, stopping iteration')
        break
    print(item)

output:
5
-11
14
zero is found in the list, stopping iteration
```

## Continue
```continue``` statement is used to stop the current iteration, and continue the next iteration.

E.g., if the item is not zero then print it, when the item is 0 then execute the continue statement.

```python
foo = [5, -11, 14, 0, -6, 0, 8]
for item in foo:
    if item==0:
        print('zero is found in the list, not printing the number')
        continue
    print(item)

output:
5
-11
14
zero is found in the list,  not printing the number
-6
zero is found in the list,  not printing the number
8
```
