# Must Learn Module 3: JSON

JSON, stands for JavaScript Object Notation, is a lightweight data-interchange format. <br/>
It is often used for exchanging data online.<br/>
The json library can parse JSON from strings or files.<br/>
A json object can be parsed into python dictionary, while a json list can be parsed into python list.<br/>

## Numpy Installation
```json``` is a built-in module in Python, you don't need to install it with pip.

## Import Module
```python
import json
```

## Import from string
```python
import json
json_string = '{ "name":"Gary", "scores":[94,86,74], "color":"Green"}'
parsed_json = json.loads(json_string)  # parse json object into python object
print(parsed_json['name'])

Output:
Gary
```

```python
import json
json_string2 = '[{"name":"Gary","color":"Green"},{"name":"Mary","color":"Pink"}]'
parsed_json = json.loads(json_string2)  # parse json list into python list
print(parsed_json[1])

Output:
{'name': 'Mary', 'color': 'Pink'}
```

## Load from json file
```python
import json
file_name = r'Gary.json' 
with open(file_name,"r",encoding="utf-8") as f: 
  parsed_json = json.load(f)
```

## Export json into file
Export python object (here dictionary is used as example) into 'Person.json'.<br/>

```python
dict_person ={
    "Person1": {
        "name": "Barry",
        "designation": "detective",
        "age": "34",
        "salary": "54000"
    },
    "Person2": {
        "name": "Gary",
        "designation": "programmer",
        "age": "28",
        "salary": "20000"
    },
}

with open("Person.json","w",encoding='utf-8') as f: 
    json.dump(dict_person,f,ensure_ascii=False,sort_keys=True, indent=4); 
```
