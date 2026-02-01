
----

Can be used to interact with an external system.

Connect to endpoint using requests.get(url="")

response code tells if it worked, etc. 

1xx - Something is going on
2xx - Good
3xx - Go away
4xx - You screwed up.
5xx - The server screwed up. 

```python
import requests  
  
response = requests.get(url="http://api.open-notify.org/iss-now.json")  
response.raise_for_status()  
  
data = response.json()  
print(data)  
  
data = response.json()["iss_position"]["longitude"]  
print(data)
```