# 📘 Assignment: Hangman Game

## 🎯 Objective

Build a word-guessing game using Python strings, loops, conditionals, random selection, and user input. Practice tracking game state as players reveal a hidden word before running out of attempts.

## 📝 Tasks

### 🛠️	Select a Word and Display Guessing Progress

#### Description
Create a predefined list of words and randomly select one for each game. Accept letter guesses from the player and display their progress without revealing unguessed letters.

#### Requirements
Completed program should:

- Randomly select a secret word from a predefined list.
- Display an underscore for each unguessed letter, separated by spaces.
- Accept letter guesses through user input.
- Reveal every occurrence of a correctly guessed letter while keeping other letters hidden. For example, guessing `p` in `apple` should display `_ p p _ _`.

### 🛠️	Track Attempts and Finish the Game

#### Description
Use a loop to keep the game running while the player has attempts remaining and the word is incomplete. Track incorrect guesses and tell the player whether they won or lost.

#### Requirements
Completed program should:

- Start each game with a fixed, positive number of allowed incorrect guesses.
- Reduce the remaining attempts by one for an incorrect letter guess, leaving the count unchanged for a correct guess.
- Display the number of incorrect guesses remaining after each guess.
- End the game when all letters are revealed or no attempts remain.
- Display a win message when the player guesses the word, or a lose message when attempts run out.
