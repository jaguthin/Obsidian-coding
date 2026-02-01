---
tags:
  - Education
  - Programming
  - Python
---

--- 
01/07/25

---

I did not get this. I did write some code and was on the right track but I got stuck on some logic and could not figure out how to make it work. 

I think I can make this happen. After talking to Drew we figured out how to do the logic so if a random pick is the same twice it will loop through until it is not. 


```python
import random  
import game_data  
import art  
  
def random_select():  
    person = random.choice(game_data.data)  
    return person  
  
person_a = (random_select())  
person_b = (random_select())  
  
score = 0  
run = True  
  
print(art.logo)  
  
while run:  
    while person_a == person_b:  
        person_b = random_select()  
          
    print(f"Compare A: { person_a["name"]},a {person_a["description"]}, from  {person_a["country"]}.")  
    print(art.vs)  
    print(f"Compare B: {person_b["name"]},a {person_b["description"]}, from  {person_b["country"]}.")  
    guess = input("Who has more followers. Type 'A' or 'B' :")  
    if guess.lower() == "a" and int(person_a["follower_count"]) > int(person_b["follower_count"]):  
        score += 1  
        print("\n" * 20)  
        print(art.logo)  
        print (f"You got it! Current score: {score}.")  
        person_a = person_b  
    elif guess.lower() == "b" and int(person_b["follower_count"]) > int(person_a["follower_count"]):  
        score += 1  
        print("\n" * 20)  
        print(art.logo)  
        print(f"You got it! Current score: {score}.")  
        person_a = person_b  
    else:  
        print("\n" * 20)  
        print(art.logo)  
        print(f"Sorry, that is wrong. Final score: {score}")  
        run = False
```
