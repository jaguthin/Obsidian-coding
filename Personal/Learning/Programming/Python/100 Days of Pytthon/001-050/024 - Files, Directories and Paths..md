
--- 

with  open("my_file.txt") as file:  
	contents = file.read()  
	print(contents)


with open("my_file.txt", mode="w") as file:  
    file.write("New text.")
###### Above will overwrite, not append.

mode="a" to append.

If file does not exist it will create. 

Python can use forward slash regardless of operating system. 