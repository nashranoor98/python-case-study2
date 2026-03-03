# python-case-study2
import random

# List of words
words = ["python", "programming", "computer", "science", "keyboard",
         "developer", "algorithm", "function", "variable", "internet"]

def scramble_word(word):
    word_list = list(word)
    random.shuffle(word_list)
    return ''.join(word_list)

def play_game():
    print("Welcome to the Word Scrambling Game!")
    print("You have 3 attempts to guess each word.\n")

    score = 0
    attempts_allowed = 3

    while True:
        word = random.choice(words)
        scrambled = scramble_word(word)

        print("Scrambled word:", scrambled)

        attempts = attempts_allowed

        while attempts > 0:
            guess = input("Your guess: ").lower()

            if guess == word:
                print("Correct! You earned 10 points.\n")
                score += 10
                break
            else:
                attempts -= 1
                print(f"Wrong! Attempts left: {attempts}")

        if attempts == 0:
            print(f"The correct word was: {word}\n")

        print("Current Score:", score)

        choice = input("Do you want to play again? (yes/no): ").lower()
        if choice != "yes":
            print("\nFinal Score:", score)
            print("Thanks for playing!")
            break

# Start the game
play_game()
