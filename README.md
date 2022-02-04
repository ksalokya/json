<div align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/460/460989.png" width="300px"/>
</div>
<h1 align="center">json Cheatsheet</h1>

## What is json?
#### JSON stands for JavaScript Object Notation. It is a lightweight data-interchange format that is used to store and exchange data.

# Import json


```python
import json
```

# Basics


```python
# the JSON object must be str
json_data = '{"a" : 1,"b": 2, "c" : 3}'
json_data
```




    '{"a" : 1,"b": 2, "c" : 3}'




```python
x = json.loads(json_data)
x
```




    {'a': 1, 'b': 2, 'c': 3}




```python
x['b']
```




    2




```python
# json data

json_data1 = '''
{
  "params":
  {
    "local_server":"True",
    "local_uri": "mysql://root:@localhost/xyz",
    "prod_uri":"mysql://root:@localhost/xyz",
    "blog_name": "XYZ",
    "gmail-user":"your-email@gmail.com",
    "gmail-password":"gmailpassword",
    "login_image":"login.svg"
  }
}'''
```


```python
# json.loads() method can be used to parse a valid JSON string and convert it into a Python Dictionary.
y = json.loads(json_data1)
y
```




    {'params': {'local_server': 'True',
      'local_uri': 'mysql://root:@localhost/xyz',
      'prod_uri': 'mysql://root:@localhost/xyz',
      'blog_name': 'XYZ',
      'gmail-user': 'your-email@gmail.com',
      'gmail-password': 'gmailpassword',
      'login_image': 'login.svg'}}




```python
y['params']
```




    {'local_server': 'True',
     'local_uri': 'mysql://root:@localhost/xyz',
     'prod_uri': 'mysql://root:@localhost/xyz',
     'blog_name': 'XYZ',
     'gmail-user': 'your-email@gmail.com',
     'gmail-password': 'gmailpassword',
     'login_image': 'login.svg'}




```python
y['params']['local_uri']
```




    'mysql://root:@localhost/xyz'



# File


```python
# writing
with open('data.json','w') as f:
    json.dump(y,f)
```

# Repeated Names Within an Object


```python
weird_json = '{"x": 1, "x": 2, "x": 3}'
json.loads(weird_json)
```




    {'x': 3}


