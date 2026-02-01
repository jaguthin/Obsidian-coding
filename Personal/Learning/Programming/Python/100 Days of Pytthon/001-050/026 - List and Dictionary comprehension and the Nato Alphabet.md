---
tags:
  - Education
  - Education/Programming
  - Education/Programming/Python
---

---

List comprehension - create a list from a previous list.

new_list = [ new_item for item in list]

Conditional list comprehension:
new_list = [ new_item for item in list if test]

###### Dictionary comprehension
new_dict = { new_key:new_value for item in list }
new_dict = { new_key:new_value for (key,value) in dict.items() }
new_dict = { new_key:new_value for (key,value) in dict.items() if test}

###### How to iterate over a pandas dataframe.

dataframe = pandas.dataframe(dictionary)
for (key, value ) in dictionary.items():
 
for (index, row) in dataframe.iterrrows():
	print row.column




	
to use iterrows() it is already in dataframe if a csv has been imported.

