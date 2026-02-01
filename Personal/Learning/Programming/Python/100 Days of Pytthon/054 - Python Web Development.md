
---

Command Line
Python Decorators
Flask

Flask better for small projects and beginners.
Django better for larger projects.


Full Stack
---
Front End - What user sees
Backup end - What presents the front end. Behind the scenes stuff. 

```
__name__
```
Creates the main class that is not imported as a module.


```python
from flask import Flask  
app = Flask(__name__)  
  
@app.route('/')  
def hello_world():  
    return "Howdy"  
  
@app.route('/test')  
def test():  
    return "This is the test directory."  
  
if __name__== "__main__":  
    app.run()  
  
    ## ip:port/directory
```

You can call a function from another function. 

You can also nest functions

```python
 Python Decorator Function  
def decorator_function(function):  
    def wrapper_function():  
        function()  
    return wrapper_function  
  
# A decorator is a function that wraps another function.  
  
#A decorator function is placed before a regualar function and will get called first.  
# Use the @ sign
```

## I do not really understand this. 

```python
1. import time

2. def speed_calc_decorator(func):
3. def wrapper(*args, **kwargs):
4. start_time = time.time()
5. result = func(*args, **kwargs)
6. end_time = time.time()
7. print(f"{func.__name__} run speed: {end_time - start_time}s")
8. return result
9. return wrapper

10. @speed_calc_decorator
11. def fast_function():
12. for i in range(1000000):
13. i * i

14. @speed_calc_decorator
15. def slow_function():
16. for i in range(10000000):
17. i * i

18. fast_function()
19. slow_function()
```