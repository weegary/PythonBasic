# Chapter 10: Try...Except...Finally

- To handle errors during runtime, we uses ```try```, ```except``` and ```finally```.
- The codes inside the try / except / finally statement cannot be aligned with the first line of the statement, it should be one indentation different from the first line.
- To escape, just simply align the code with the first line of the statement.

## Example 1 - Try ... Except

For example, since there is no "Louis" in the names list, python will throw an error and stop running if you are looking for the index of "Louis".<br/>
![image](https://user-images.githubusercontent.com/51909547/193315048-44bb7fd1-5c3b-46f4-88b3-37ecd91a4c2f.png) <br/>
<br/>
We can rewrite the code to handle this error.<br/>

```python
names = ["Barry","Gary","Mary"] 
try:
    names.index("Louis")
except:
    print("You got an exception.")
print("continue...")

output:
You got an exception.
continue...
```

## Example 2 - Different exceptions

If we can foresee the type of exception that could happen during runtime, we can put the name of type after the except. <br/>
There are several types of [built-in error](https://docs.python.org/3/library/exceptions.html): ValueRror, ZeroDivisionError, OSError, etc.<br/>
We can write several excepts in a ```try...except``` blocks. <br/>

```python
names = ["Barry","Gary","Mary"] 
try:
    number = 14 / 0
    names.index("Louis")
except ValueError:
    print("You got an ValueError.")
except ZeroDivisionError:
    print("You got a ZeroDivisionError.")
except OSError:
    print("You got an OSError.")
print("continue...")

output:
You got a ZeroDivisionError.
continue...
```

In a except statement, we can set multiple types of error, if one of the types is matched, the code inside the block will be executed.

```python
names = ["Barry","Gary","Mary"] 
try:
    number = 14 / 0
    names.index("Louis")
except (ValueError, ZeroDivisionError):
    print("You got an error from A.")
except ZeroDivisionError:
    print("You got a ZeroDivisionError from B.")
except OSError:
    print("You got an OSError.")
print("continue...")

output:
You got an error from A.
continue...
```

## Example 3 - Try ... Except ... Finally

During program development, we often need to finish the process even some errors occur.<br/>
For instance, when we connect to database or open a file, we always need to disconnect the database or close the file.<br/>
We can put the code in ```finally``` block to prevent exceptions stopping the flow.

```python
names = ["Barry","Gary","Mary"] 
try:
    number = 14 / 0
    names.index("Louis")
except (ValueError, ZeroDivisionError):
    print("You got an error.")
finally:
    print("This code always run.")

print("continue...")

output:
You got an error.
This code always run.
continue...
```
