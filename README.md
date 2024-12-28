# word__guessing__game
1. Function Definitions:

`read_words`
- **Purpose**: Reads a list of words from a file named `words.txt`.
- **Logic**:
  - Tries to open the file `words.txt` in read mode.
  - Splits the file's content into lines to form a list of words.
  - If the file does not exist, it handles the `FileNotFoundError` and returns an empty list.
  
`display_word`
- **Purpose**: Displays the current state of the guessed word to the player.
- **Logic**:
  - Iterates over each letter in the secret word.
  - If the letter has been guessed, it is displayed.
  - Otherwise, it is replaced with an underscore `_` to indicate an unguessed letter.
  - The final string representation of the word is printed.

`get_guess`
- **Purpose**: Handles user input for guessing letters.
- **Logic**:
  - Continuously prompts the user until a valid letter is entered.
  - Checks that:
    - The input is a single character.
    - It is a lowercase English alphabet letter (`a-z`).
    - It has not already been guessed.
  - Returns the valid guess.

`is_word_guessed`
- Purpose: Checks if the player has guessed all letters in the secret word.
- Logic:
  - Iterates over each letter in the secret word.
  - If any letter is not in the list of guessed letters, it returns `False`.
  - Otherwise, it returns `True`.

2. The `main` Function:

Initial Setup:
- Reads the list of words using `read_words`. If no words are loaded, the game ends.
- Chooses a random word (`secret_word`) from the list using `random.choice`.

Game Loop:
- The game allows a maximum of 6 incorrect attempts (`attempts`).
- Continuously:
  - Displays the current state of the word using `display_word`.
  - Gets a valid letter guess from the player using `get_guess`.
  - Adds the guessed letter to the list of `guessed_letters`.

Handling Guesses:
- If the guessed letter is in the secret word:
  - Prints "Good guess."
  - Checks if the word is completely guessed using `is_word_guessed`. If so, the player wins, and the game ends.
- If the guessed letter is incorrect:
  - Prints "Wrong guess."
  - Decrements the remaining attempts by 1.
  - If no attempts are left, the game ends with a "Game over!" message, revealing the secret word.


3. Program Execution:
- The `main` function is executed when the script is run directly.
- The game starts and follows the logic described above.


Key Concepts:
- File Handling: To load words from a file (`read_words`).
- String Manipulation: To display the guessed and unguessed parts of the word (`display_word`).
- Input Validation: To ensure user guesses are valid (`get_guess`).
- Game Logic: Maintains player progress, checks guesses, and determines win/loss conditions.
