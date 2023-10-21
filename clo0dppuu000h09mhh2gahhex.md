---
title: "A Python Implementation of The Hangman Game"
seoTitle: "Python Implementation of The Hangman Game"
datePublished: Sat Oct 21 2023 18:34:16 GMT+0000 (Coordinated Universal Time)
cuid: clo0dppuu000h09mhh2gahhex
slug: a-python-implementation-of-the-hangman-game
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697913150797/fde9840a-58f5-46e5-85ee-0b71a992c375.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1697913227033/a566b030-8a68-4ac7-a578-a83c514c5b0b.jpeg
tags: python, web-development, webdev, python3, game-development

---

### Build a Python Script for the Popular Hangman Game

In this project, you will create a Python project implementing the hangman game enabling the player to attempt to guess a hidden word. If you are unfamiliar with the game, check out [the graphical online game here](https://www.hangmanwords.com/play).

Here is a summary of how the game works; the user has attempts at guessing a word represented in a row of dashes and if a player guesses a letter that exists in the word, the program writes it in all correct positions, these attempts are reduced for every wrong character guess the player makes, once all are exhausted, without a matching word having been guessed, the monster eats up the player.

### Here are the steps to follow:

* Choose some good hangman words for your program. You can go to this [website](https://www.hangmanwords.com/words) and create a list of words for your game.
    
* At the start of the game, use the random library to choose a random word from your hangman words and display the word's letters as dashes rather than letters.
    
* Now, apply the input function to allow the user to make letter guesses. Use try... except and if statements to ensure that only valid inputs work with your script i.e. a user can only choose one letter at a time, and a user cannot choose letters that have been selected before.
    
* If the letter is in the word, it is printed in place of the corresponding dash. If the letter is not in the word, that is counted as a failed attempt, Limit the number of failed attempts for the user to 6 such that on the 6th fail, the game ends, and the script prints the actual word and "You Lost". Make sure to tell the user they won if they guess all the correct letters in under 6 failed attempts.
    
* If you want to take the project a notch higher, you can use the Python Turtle Library to visualize the hanging like on [this website](https://www.hangmanwords.com/play). This is optional!
    

### Here is a sample Python script for the hangman game:

```python
import random

# List of hangman words
hangman_words = ['python', 'programming', 'code', 'algorithm', 'development']

# Choose a random word from the list
word = random.choice(hangman_words)

# Create a list of dashes to represent the hidden word
hidden_word = ['_'] * len(word)

# Keep track of the number of failed attempts
failed_attempts = 0

# Keep track of the letters that have been guessed
guessed_letters = []

# Start the game
while '_' in hidden_word and failed_attempts < 6:
    print(' '.join(hidden_word))
    print('Guessed letters: ', guessed_letters)
    letter = input('Guess a letter: ')

    try:
        # Check if the input is a single letter
        if len(letter) != 1:
            raise ValueError
        # Check if the letter has already been guessed
        elif letter in guessed_letters:
            raise ValueError
    except ValueError:
        print('Invalid input. Please enter a single letter that has not been guessed before.')
        continue

    guessed_letters.append(letter)

    if letter in word:
        for i in range(len(word)):
            if word[i] == letter:
                hidden_word[i] = letter
    else:
        failed_attempts += 1
        print(f'Letter not in word. You have {6 - failed_attempts} attempts remaining.')

# Check if the player won or lost
if '_' not in hidden_word:
    print(' '.join(hidden_word))
    print('You won!')
else:
    print('You lost.')
    print('The word was:', word)
```

You can use the Python Turtle Library to visualize the hanging like in this website by adding the following code:

```python
import turtle

def draw_hangman(failed_attempts):
    # Create a turtle object
    t = turtle.Turtle()
    t.speed(10)

    # Draw the gallows
    t.penup()
    t.goto(-200, 0)
    t.pendown()
    t.forward(400)
    t.right(90)
    t.forward(200)
    t.right(90)
    t.forward(50)
    t.right(90)
    t.forward(50)

    # Draw the head
    if failed_attempts > 0:
        t.right(180)
        t.circle(25)

    # Draw the body
    if failed_attempts > 1:
        t.left(90)
        t.forward(100)

    # Draw the arms
    if failed_attempts > 2:
        t.right(90)
        t.forward(50)
        t.backward(100)
        t.forward(50)

    # Draw the legs
    if failed_attempts > 3:
        t.right(90)
        t.forward(50)
        t.backward(100)
        t.forward(50)
    
    # Draw the left
    if failed_attempts > 4:
    t.penup()
    t.goto(-20, 50)
    t.pendown()
    t.dot(10)

    # Draw the right eye
    if failed_attempts > 5:
        t.penup()
        t.goto(20, 50)
        t.pendown()
        t.dot(10)
    
    turtle.done()
    # Call the draw_hangman function inside the while loop
    while '_' in hidden_word and failed_attempts < 6:
    # Code for guessing letters and updating hidden_word
    draw_hangman(failed_attempts)
```

You can also add more features to the game, such as allowing the player to play again after losing or winning, keeping track of the score, etc.

### GitHub Repo

Check out [this GitHub repo](https://github.com/bonaventureogeto/Learn-Python/blob/main/hangman.py) for another implementation of the Hangman game.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!