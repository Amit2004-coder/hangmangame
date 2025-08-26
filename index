import random

# Hangman ASCII stages
HANGMAN_PICS = [
    """
       +---+
       |   |
           |
           |
           |
           |
    =========
    """,
    """
       +---+
       |   |
       O   |
           |
           |
           |
    =========
    """,
    """
       +---+
       |   |
       O   |
       |   |
           |
           |
    =========
    """,
    """
       +---+
       |   |
       O   |
      /|   |
           |
           |
    =========
    """,
    """
       +---+
       |   |
       O   |
      /|\\  |
           |
           |
    =========
    """,
    """
       +---+
       |   |
       O   |
      /|\\  |
      /    |
           |
    =========
    """,
    """
       +---+
       |   |
       O   |
      /|\\  |
      / \\  |
           |
    =========
    """
]

def get_random_word():
    words = [
        'python', 'javascript', 'java', 'kotlin', 'hangman', 'computer',
        'programming', 'algorithm', 'data', 'function', 'variable'
    ]
    return random.choice(words)

def display_word(word, guessed_letters):
    displayed = ' '.join([letter if letter in guessed_letters else '_' for letter in word])
    return displayed

def hangman():
    print("🎮 Welcome to Hangman!")
    word = get_random_word()
    guessed_letters = set()
    attempts_remaining = len(HANGMAN_PICS) - 1  # 6 wrong guesses allowed

    while attempts_remaining > 0:
        print(HANGMAN_PICS[len(HANGMAN_PICS) - 1 - attempts_remaining])  # show hangman stage
        print(f"\nWord: {display_word(word, guessed_letters)}")
        print(f"Attempts remaining: {attempts_remaining}")
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1 or not guess.isalpha():
            print("⚠️ Please enter a single alphabetic character.")
            continue

        if guess in guessed_letters:
            print(f"⚠️ You already guessed '{guess}'. Try a different letter.")
            continue

        guessed_letters.add(guess)

        if guess in word:
            print(f"✅ Good job! '{guess}' is in the word.")
        else:
            print(f"❌ Sorry, '{guess}' is not in the word.")
            attempts_remaining -= 1

        if all(letter in guessed_letters for letter in word):
            print(f"\n🎉 Congratulations! You guessed the word: {word}")
            break
    else:
        print(HANGMAN_PICS[-1])  # final stage
        print(f"\n💀 Game Over! The word was: {word}")

if __name__ == "__main__":
    hangman()
