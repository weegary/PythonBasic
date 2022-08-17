# File Handling

## Text Files (e.g., txt, csv)

### Write Files 
data = open('data.txt','w')  # w : writing mode (overwrite)
data.writelines('1\t10\n')  # \t is tab, \n is new lines (enter key)
data.writelines('2\t20\n')
data.writelines('3\t50\n')
data.writelines('4\t100\n')
data.writelines('5\t250\n')
data.writelines('6\t600\n')
data.close()

# data = open('data.txt','a')  # a : appending mode (don't overwrite)
# data.writelines('1\t10\n')
# data.writelines('2\t20\n')
# data.writelines('3\t50\n')
# data.writelines('4\t100\n')
# data.writelines('5\t250\n')
# data.writelines('6\t600\n')
# data.close()

### Read Files
```python
data = open('data.txt','r')	        #  r : reading mode
lines_list = data.readlines()	# 將Data.txt檔中每一行存入串列中 
data.close
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
