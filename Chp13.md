# File Handling

## Text Files (e.g., txt, csv)

```open(file_name,mode)``` is used to manipulate the file. The mode can be set to ```'r'``` to read file, ```'w'``` to write file (create a new file or overwrite existed file), and ```'a'``` to append file (don't overwrite existed file, continue at the end of the existed file).

### Write Files 

1. To write file (create a new file or overwrite existed file)
``` python
data = open('data.txt','w')  # w : writing mode (overwrite)
data.writelines('1\t10\n')  # \t is tab, \n is new lines (enter key)
data.writelines('2\t20\n')
data.writelines('3\t50\n')
data.writelines('4\t100\n')
data.writelines('5\t250\n')
data.writelines('6\t600\n')
data.close()
```

2. To append file (don't overwrite existed file, continue at the end of the existed file).
```python
data = open('data.txt','a')  # a : appending mode (don't overwrite)
data.writelines('1\t10\n')
data.writelines('2\t20\n')
data.writelines('3\t50\n')
data.writelines('4\t100\n')
data.writelines('5\t250\n')
data.writelines('6\t600\n')
data.close()
```

### Read Files
```python
data = open('data.txt','r')	        # r : reading mode
lines_list = data.readlines()	      # Open 'data.txt' and save all lines into a list. 
data.close()
```

### Create Files

### Delete Files

## Special Format: JSON

```python
import json
file_name = r'example.json' 
# load json file
with open(file_name,'r',encoding="utf-8") as f: 
  dataAll = json.load(f)
```

## Module: os, glob, sys, shutil

## Getting Files in Directory

## Getting Directories in Directory
