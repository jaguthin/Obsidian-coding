---
tags:
  - Education
  - Education/Programming
  - Education/Programming/Python
---
--- 
01/02/25

---
dictionary = {key: value}

Convention = 

dictionary = {
	k:v,
	k:v,
	k:v,
}

To get data:
dictionary[k]

Add data:

dictionary[k] = v

Above is also how one changes an entry. 

empty dictionary:
dictionary = {}
Above is also a way to wipe a dictionary. 

To loop through a dictionary:
for key in dictionary:
	print(key)

Will print keys.

for key in dictionary:
    print(dictionary[key])
will print values

#### Nesting
dictionary = {
    key1: [List],
    key2: Value,
}
travel_log = {
    "France": ["Paris", "Lille", "Dijon"],
    "Germany": ["Stuttgart", "Berlin"],
}
```python
print(["France"][1])
```
To get Lille


