# CodeAlpha_HangmanGame
Python Hangman Game project for CodeAlpha Internship.
import random

words = ["apple", "mango", "python", "school", "laptop"]

word = random.choice(words)
guessed = []
attempts = 6

print("Welcome to Hangman Game!")

while attempts > 0:
    display = ""

    for letter in word:
        if letter in guessed:
            display += letter + " "
        else:
            display += "_ "

    print("\nWord:", display)

output:Welcome to Hangman Game!

Word: _ _ _ _ _ _
Enter a letter: p

Correct Guess!

Word: p _ _ _ _ _
Enter a letter: y

Correct Guess!

Word: p y _ _ _ _
Enter a letter: t

Correct Guess!

Word: p y t _ _ _
Enter a letter: h

Correct Guess!

Word: p y t h _ _
Enter a letter: o

Correct Guess!

Word: p y t h o _
Enter a letter: n

Correct Guess!

Congratulations! You guessed the word: python
    if "_" not in display:
        print("🎉 You Won!")
        break

    guess = input("Enter a letter: ").lower()

    if guess in word:
        guessed.append(guess)
        print("Correct!")
    else:
        attempts -= 1
        print("Wrong Guess!")
        print("Attempts Left:", attempts)

if attempts == 0:
    print("💀 Game Over!")
    print("The word was:", word)
