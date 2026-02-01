
---

```python
import smtplib  
  
my_email = "findinglavondyss@gmail.com"  
password = 'qlwq oido vpmy biwd'  
  
  
with smtplib.SMTP("smtp.gmail.com", port=587) as connection:  
    connection.starttls()  
    connection.login(user=my_email, password=password)  
    connection.sendmail(  
        from_addr=my_email,  
        to_addrs='jaguthin@gmail.com',  
        msg="Subject: Hello\n\nThis is the contents of the email."  
    )
```
```python
import datetime as dt  
now = dt.datetime.now()  
print(now.weekday())  
  
date_of_birth = dt.datetime(year=1967, month=8, day=12, hour=10, minute=12)  
print(date_of_birth)
```

###### Send quote on certain day of week. 
```python
import random  
import datetime as dt  
import smtplib  
  
now = dt.datetime.now()  
  
if now.weekday() == 5:  
    with  open("quotes.txt") as quote:  
        qotd = random.choice(quote.readlines())  
  
    my_email = "findinglavondyss@gmail.com"  
    password = 'qlwq oido vpmy biwd'  
  
    with smtplib.SMTP("smtp.gmail.com", port=587) as connection:  
        connection.starttls()  
        connection.login(user=my_email, password=password)  
        connection.sendmail(  
            from_addr=my_email,  
            to_addrs='jaguthin@gmail.com',  
            msg=f"Subject: Quote of the Day\n\n{ qotd }."  
        )
```
###### Birthday wisher
```python
import random  
import pandas  
import datetime as dt  
import smtplib  
  
MY_EMAIL  = "findinglavondyss@gmail.com"  
MY_PASSWORD = 'qlwq oido vpmy biwd'  
  
bdays = pandas.read_csv("birthdays.csv")  
bdays_dict = bdays.to_dict(orient="records")  
  
  
now = dt.datetime.now()  
cur_month = now.month  
cur_day = now.day  
random_num = random.randint(1, 3)  
new_bday_letter = []  
with open(f"letter_templates/letter_{random_num}.txt") as letter:  
    bday_letter = letter.readlines()  
    new_bday_letter = ''.join(str(x) for x in bday_letter)  
   
for day in bdays_dict:  
     bday_month = day["month"]  
     bday_day = day["day"]  
     if cur_month == bday_month and cur_day == bday_day:  
         bday_name = day["name"]  
         with open(f"letter_templates/letter_{random_num}.txt") as letter:  
             bday_letter = letter.readlines()  
             new_bday_letter = ''.join(str(x) for x in bday_letter)  
         new_bday_letter = new_bday_letter.replace("[NAME]", bday_name)  
  
         with smtplib.SMTP("smtp.gmail.com", port=587) as connection:  
             connection.starttls()  
             connection.login(user=MY_EMAIL, password=MY_PASSWORD)  
             connection.sendmail(  
                 from_addr=MY_EMAIL,  
                 to_addrs='jaguthin@gmail.com',  
                 msg=f"Subject: Happy Birthday!\n\n{new_bday_letter}."  
             )
```

Above could be more elegant with functions and list comprehension, etc, but it work. 
