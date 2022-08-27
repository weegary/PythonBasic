Install Module
- ```requests``` is used to send request and read returned data.
- ```beautifulsoup4``` is used to parse html ([link](https://pypi.org/project/beautifulsoup4/)).

```python
pip install requests
pip install beautifulsoup4
```

Example 1: Getting Realtime Rainfall Data from Taipei City Government.

This example will send a request to Data.Taipei (Open Data Website developed by the Taipei City Government) to get realtime rainfall data, the request will return a json object.

```python
import requests
from bs4 import BeautifulSoup

url = 'https://wic.heo.taipei/OpenData/API/Rain/Get?stationNo=&loginId=open_rain&dataKey=85452C1D'
r = requests.get(url)

print(r.text)   # print the returned value, which is a json object
```

To manipulate the json object, we can import json module, to parse the json object into a python dictionary or list.
```python
import json
realtime_data = json.loads(r.text)
```
![image](https://user-images.githubusercontent.com/51909547/187031078-ce25ca02-8878-479d-b539-3260ef10a19d.png)

URL: https://wic.heo.taipei/OpenData/API/Rain/Get?stationNo=&loginId=open_rain&dataKey=85452C1D <br/>
Reference: https://data.taipei/dataset/detail?id=6f03a0b8-7b98-4eea-8bb9-ba6bfcdc2b8b
