
---

When an error happens the program stops. 

Errors get raised and can use those names to catch them. 

```python
try:  # Something that might cause an exception.
      
except:  # Do if there is an exception.
      
else:  # do if there were no exceptions.
      
finally: # Do no matter what. 
```

Best not to use a bare except. 

except FileExistsError  
  
except KeyError as error_message
	print(f"The key { errror_message } does not exist." )

etc. as and after is not needed. 

raise KeyError -- Arbitrary.  Can be called if needed for whatever reason. 

raise Error("message")

Raising own error can be useful to find input that is crazy. 
