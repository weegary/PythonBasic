# Chapter 6: Control Flow - For Loops

- syntax: ```for item in sequence:```
- remember to add ":" colon symbol at the end of the for statement.
- the codes inside the for loop cannot be aligned with the first line of the for statement, it should be one indentation different from the first line.
- To escape the for loop, just simply align the code with the first line of for statement.

## Example 1: Use index to call the item.

```python
names = ["Gary","Kevin","Daniel"]
for i in range(0,len(names)):
    print(names[i])
```

## Example 2: Directly call the item
```python
names = ["Gary","Kevin","Daniel"]
for n in names:
    print(n)
```
