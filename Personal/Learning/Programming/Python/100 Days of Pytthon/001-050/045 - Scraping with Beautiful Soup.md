
---

https://www.crummy.com/software/BeautifulSoup/bs4/doc/

100 movies project

```python
import requests  
from bs4 import BeautifulSoup  
  
URL = "https://web.archive.org/web/20200518073855/https://www.empireonline.com/movies/features/best-movies-2/"  
  
# Write your code below this line 👇  
  
response = requests.get(URL)  
top100_webpage = response.text  
soup = BeautifulSoup(top100_webpage, "html.parser")  
  
all_titles =  soup.find_all(name="h3", class_="title")  
title_list = []  
for title in all_titles:  
    title_list.append(title.text)  
reversed_movie_list = reversed(title_list)  
  
  
for title in reversed_movie_list:  
    with open("movies.txt", mode="a") as file:  
        file.write(f"{title}\n")  
          
# I Got it.  It may be able to be refined with list comprehension but it works./
```

