# Function

A function is a block of codes performs specific task which can be used repeatly. <br/>
Instead of writing the codes multiple time, we use functions. <br/>
To use a function, we need to first define it, and later call it.<br/>

To define a function in python, ```def``` is required, followed by the name of the function and the input parameters. <br/>
For example, function below adds the total of x, y and z, and returns the sum. <br/>

After defining a function, it needs to be called in order to execute. <br/>
In the last line of the example, three arguments a, b and c are passed into the function ```Total()```, after the function finishes calculating and returns a value, it passes the value to the ```number``` variable.

```python
def Total(x,y,z):

    sum = x+y+z
    return sum

a = 1
b = 3
c = 7
number = Total(a,b,c)
```
![image](https://user-images.githubusercontent.com/51909547/195002836-8f77ae52-7de2-463c-a85a-777b567acce3.png)
![image](https://user-images.githubusercontent.com/51909547/195002899-2dee16c5-487a-4971-95cb-ff59334d4f6e.png)
![image](https://user-images.githubusercontent.com/51909547/195003000-48126514-f93e-4290-9265-88ce295491c3.png)

