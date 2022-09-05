# File Handling

## Text Files (e.g., txt, csv)

```open(file_name,mode)``` is used to manipulate the file. The mode can be set to ```'r'``` to read file, ```'w'``` to write file (create a new file or overwrite existed file), and ```'a'``` to append file (don't overwrite existed file, continue at the end of the existed file).

### Write File (and Create File)

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

### Read File
```python
data = open('data.txt','r')	        # r : reading mode
lines_list = data.readlines()	      # Open 'data.txt' and save all lines into a list. 
data.close()
```

### Delete File
```python
import os
os.remove("data.txt")
```

### Check If The File Is Existed
```python
import os
print(os.path.exists("data.txt"))  # Return True or False
```

## Special Format: JSON
```python
import json
file_name = r'example.json' 
# load json file
with open(file_name,'r',encoding="utf-8") as f: 
  dataAll = json.load(f)
```

## Module: os, glob, sys, shutil

1. os
```python
import os
```

2. glob
```python
import glob
```

3. sys
```python
import sys
```

4. shutil
```python
import shutil
```

## Getting Files in Folder (Directory)

1. List all files
```python 
import glob

path_name = r'C:\Users\user\Desktop\\'
files = glob.glob(path_name+"*")  # List all files
print(files)
```

2. List files with specific format 
```glob.glob(path_name+"*")``` would list all the files, to specify the format of file, we can change the code to ```glob.glob(path_name+"*.txt")```, this would list all the ".txt" format files.

```python 
import glob

path_name = r'C:\Users\user\Desktop\\'
files = glob.glob(path_name+"*.txt")  # List all files with ".txt" format
print(files)
```

3. List files with specific name

```python
import glob
glob.glob('./[0-9].*')                   # file named with number 0~1, no matter what format
glob.glob('*.gif')                       # file named with ".gif" format
glob.glob('?.gif')                       # file named with ".gif" format, the file name is just one character
glob.glob('**/*.txt', recursive=True)    # file named with ".txt" format, including the files located in first level folder
glob.glob('./**/', recursive=True)       # folder located in parent folder

Possible output:
['./1.gif', './2.txt']
['1.gif', 'card.gif']
['1.gif']
['2.txt', 'sub/3.txt']
['./', './sub/']
```

## Getting Folders (Directories) in Folder(Directory)
```python
import glob

path_name = r'C:\Users\user\Desktop\\'
files = glob.glob(path_name+"*\\")  # List all folders
print(files)
```

## Delete Folder (Directory)
```python
import os
os.rmdir("folder_path")  # rmdir : remove directory
