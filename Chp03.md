# Chapter 03: DateTime / TimeDelta / Date / Time

There are several data type for representing date and time, 
- DateTime
- Date
- Time
- TimeDelta

## DateTime

Get current datetime. <br/>

```python
from datetime import datetime
 
# Calling now() function
today = datetime.now()
 
print("Current date and time is", today)

Output:
Current date and time is 2023-03-05 04:35:16.816744
```

Set a certain datetime.<br/>

```python
from datetime import datetime

dt = datetime(2020, 10, 1, 12, 52, 24)
print(dt)
print("year =", dt.year)
print("month =", dt.month)
print("hour =", dt.hour)
print("minute =", dt.minute)
print("second =", dt.second)
print("timestamp =", dt.timestamp())

Output:
2020-10-01 12:52:24
year = 2020
month = 10
hour = 12
minute = 52
second = 24
timestamp = 1601527944.0
```

Format DateTime object to string. (strftime) 
```python
# Python program to demonstrate
# strftime() function
 
from datetime import datetime as dt
 
# Getting current date and time
now = dt.now()
print("Without formatting", now)
 
# Example 1
s = now.strftime("%A %m %Y")
print('\nExample 1:', s)
 
# Example 2
s = now.strftime("%a %m %y")
print('\nExample 2:', s)
 
# Example 3
s = now.strftime("%I %p %S")
print('\nExample 3:', s)
 
# Example 4
s = now.strftime("%H:%M:%S")
print('\nExample 4:', s)

Output:
Without formatting 2023-03-05 04:51:41.698399

Example 1: Sunday 03 2023

Example 2: Sun 03 23

Example 3: 04 AM 41

Example 4: 04:51:41
```

Parse string into DateTime object. (strptime)
```python
from datetime import datetime
  
# consider the time stamps from a list  in string
# format DD/MM/YY H:M:S.micros
time_data = ["03/01/22 02:35:8.023", "26/02/22 12:45:0.003",
             "10/05/22 07:35:5.523", "14/07/22 05:15:55.523"]
  
# format the string in the given format : day/month/year 
# hours/minutes/seconds-micro seconds
format_data = "%d/%m/%y %H:%M:%S.%f"
  
# Using strptime with datetime we will format string
# into datetime
datetime_data = []
for i in time_data:
    datetime_data.append(datetime.strptime(i, format_data))
```

## TimeDelta

To add or minus a day to datetime object
```python
# Timedelta function demonstration
from datetime import datetime, timedelta
 
# Using current time
initial_time_for_now = datetime.now()
 
# printing initial_date
print("initial_date", str(initial_time_for_now))
 
# Calculating future dates
future_date_after_2days = initial_time_for_now + timedelta(days=2)

# Calculating previous dates
previous_date_before_5days2hours =  initial_time_for_now + timedelta(days=-5, hours==2)

# printing results
print('future_date_after_2days:', str(future_date_after_2days))
print('future_date_before_5day:', str(previous_date_before_5days))

Output:
initial_date 2023-03-05 04:42:35.780822
future_date_after_2days: 2023-03-07 04:42:35.780822
future_date_before_5day: 2023-02-28 02:42:35.780822
```

## Date

In some cases, you may use date only without time.
```python
# import the date class
from datetime import date
 
# initializing constructor
# and passing arguments in the
# format year, month, date
my_date = date(2019, 3, 11)
 
print("Date passed as argument is", my_date)

Output:
Date passed as argument is 2019-03-11
```

## Time

Or in other cases, you may use time only.
```python
# import the time class
from datetime import time
 
# calling the constructor
my_time = time(13, 24, 56)
 
print("Entered time", my_time)

Output:
Entered time 13:24:56
```
