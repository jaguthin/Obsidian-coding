---
tags:
  - Education
  - Education/Programming
  - Education/Programming/Python
---

---

```python
import tkinter 

window = tkinter.Tk()
window.title("GUI")
window.minsize(width=200, height=200)

 
my_label = tkinter.Label(text="I am a label", font=("Arial", 24, "bold"))
my_label.pack()
  
  
  
  
window.mainloop()
```
tkinter.Tk() is how you start the gui.
The mainloop keeps the program running and needs to be at the end. 
.pack() is needed to show the item. 
font info is a tuple. - Last item can be left out. - I do not know how to make it two things. Like bold and underlined.
packer options can be changed to change the look of what it packs.

functions with default values:
def function(arg1=whatever, arg2=whatever, ...):

unlimited arguments: def function(*args)
	for n in args:
		do stuff
	
	
###### kwargs
keyword arguments
``` 
(**kwargs)
```
```python
def calc(**kwargs):  
    print(kwargs)  
    for key, value in kwargs.items():  
  
        print(f"{key}: {value}")  
        print(kwargs["multiply"])  
        n += kwargs["add]
        n *= kwargs["multiply"]
  
  
calc(2, add=3, multiply=5)
```

```python
def button_clicked():  
    print("I got clicked")  
button = tkinter.Button(text="Click Me", command=button_clicked)  
button.pack()
```

pack is hard to be precise.
.place(x=0, y=0) can accept an x and a y. 

place is very specific.
.grid(column=0, row=0)
Relative to any other widgets.

grid and pack can't be used simultaneously. 

```python
from tkinter import *  
  
def button_clicked():  
    my_label["text"] = "Clicked"  
  
def get_input():  
    my_label["text"] = input.get()  
  
window = Tk()  
window.title("GUI")  
window.minsize(width=500, height=300)  
window.config(padx=20, pady=20)  
  
#Label  
my_label = Label(text="I am a label", font=("Arial", 24, "bold"))  
my_label.config(text="New Text 2")  
my_label.grid(column=0, row=0)  
my_label.config(padx=50, pady=50)  
  
# Button  
button = Button(text="Button", command=get_input)  
button.grid(column=1, row=1)  
  
new_button = Button(text="New Button")  
new_button.grid(column=2, row=0)  
  
# Entry  
input = Entry(width=10)  
print(input.get())  
input.grid(column=3, row=2)  
  
window.mainloop()
```

