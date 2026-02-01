---
tags:
  - Education
  - Programming
  - Python
---

---
12/31/24

---

Had to write a hangman game:
```python
import random  

from hangman_words import word_list  
from hangman_art import stages,logo  
lives = 6  
  
print(logo)  
chosen_word = random.choice(word_list)  
print(chosen_word)  
  
placeholder = ""  
word_length = len(chosen_word)  
for position in range(word_length):  
    placeholder += "_"  
print("Word to guess: " + placeholder)  
  
game_over = False  
correct_letters = []  
chosen_letters = []  
  
while not game_over:  
  
    print(f"****************************{lives}/6 LIVES LEFT****************************")  
    guess = input("Guess a letter: ").lower()  
  

    if guess in chosen_letters:  
        print("You have already guessed that letter.")  
    else:  
        chosen_letters.append(guess)  
  
    display = ""  
  
    for letter in chosen_word:  
        if letter == guess:  
            display += letter  
            correct_letters.append(guess)  
        elif letter in correct_letters:  
            display += letter  
        else:  
            display += "_"  
  
  
    print("Word to guess: " + display)  
  
 
    if guess not in chosen_word:  
        lives -= 1  
        print(f"{guess} is not in the chosen word. You lose a life.")  
  
        if lives == 0:  
            game_over = True  
  

            print(f"***********************YOU LOSE**********************\n\nThe correct word was {chosen_word}")  
  
    if "_" not in display:  
        game_over = True  
        print("****************************YOU WIN****************************")  
  

    print(stages[lives])
```