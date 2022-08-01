# Python - Excel

## Terminology
- Workbook: A Workbook (Spreadsheet) is the main file (excel file) you are creating or working with.
- Sheet: A Sheet (Worksheet) is used to split different kinds of content within the same workbook. A workbook can have one or more sheets.
- Column: A Column is a vertical line, and it is represented by an uppercase letter: A, B, C, etc..
- Row: A Row is a horizontal line, and it is represented by a number: 1, 2, 3, etc..
- Cell: A Cell is a combination of Column and Row, represented by both an uppercase letter and a number: A1, B3, C5, etc..

## Getting Started 
Install the ```openpyxl``` module.
```console
pip install openpyxl
```

Create a simple workbook
```python
from openpyxl import Workbook

workbook = Workbook()
sheet = workbook.active

sheet["A1"] = "First Name"
sheet["B1"] = "Last Name"
sheet["A2"] = "Gary"
sheet["B2"] = "Wee"

workbook.save(filename="name.xlsx")
```
![Screenshot_01](https://user-images.githubusercontent.com/51909547/182057199-70cfd4a8-f966-4fbc-9bbe-395c70a6383c.png)



## Reading Excel Spreadsheets

To Be Continued...

Reference: https://realpython.com/openpyxl-excel-spreadsheets-python/
