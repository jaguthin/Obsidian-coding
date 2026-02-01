
---
```python
from bs4 import BeautifulSoup  
import requests  
import smtplib  
import os  
#from dotenv import load_dotenv  
  
#load_dotenv()  
MY_EMAIL  = "findinglavondyss@gmail.com"  
MY_PASSWORD = 'qlwq oido vpmy biwd'  
SMTP_SERVER = "smtp.gmail.com"  
  
  
test_url = "https://appbrewery.github.io/instant_pot/"  
response = requests.get(test_url)  
  
soup = BeautifulSoup(response.text, "html.parser")  
#amazon_price_whole = soup.select("span + .a-price-whole").get  
amazon_price_whole = soup.find("span", class_="a-price-whole").getText()  
amazon_price_fraction = soup.find("span", class_="a-price-fraction").getText()  
price = float(f"{amazon_price_whole}{amazon_price_fraction}")  
  
  
if price < 100:  
    with smtplib.SMTP(SMTP_SERVER, port=587) as connection:  
        connection.starttls()  
        connection.login(user=MY_EMAIL, password=MY_PASSWORD)  
        connection.sendmail(  
            from_addr=MY_EMAIL,  
            to_addrs='jaguthin@gmail.com',  
            msg=f"Subject: The price of your item is in your threshold.\n\nThe price is now ${price}."  
        )
```

I could not get dotenv to work so I just hard coded the vars. 

I did not do this on the live Amazon site, though. Just the practice site. the live site would need headers and other stuff. 