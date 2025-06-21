import random

# List of predefined words
word_list = ['python', 'code', 'hangman', 'program', 'alpha']
chosen_word = random.choice(word_list)
word_length = len(chosen_word)
guessed_letters = []
tries = 6

# Create a display with underscores
display = ['_'] * word_length

print("Welcome to Hangman Game!\n")

while tries > 0 and '_' in display:
    print("\nWord: " + ' '.join(display))
    guess = input("Guess a letter: ").lower()

    if guess in guessed_letters:
        print("You already guessed that letter.")
        continue

    guessed_letters.append(guess)

    if guess in chosen_word:
        print("Good guess!")
        for i in range(word_length):
            if chosen_word[i] == guess:
                display[i] = guess
    else:
        tries -= 1
        print(f"Wrong guess. You have {tries} tries left.")

# Check win/lose
if '_' not in display:
    print("\nCongratulations! You guessed the word:", chosen_word)
else:
    print("\nGame over! The word was:", chosen_word)
