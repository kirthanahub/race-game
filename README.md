import random
import time

def print_race(char_positions):
    for char, pos in char_positions.items():
        print(f"{char}: {' ' * pos}|")

def race():
    characters = {
        "A": 0,
        "B": 0,
        "C": 0
    }

    finish_line = 20

    print("Get ready for the race!")

    while True:
        # Clear the screen for better visibility (works in some consoles)
        print("\033c")

        for char in characters:
            # Characters randomly move 1 or 2 steps
            characters[char] += random.randint(1, 2)

            # Check if a character has reached the finish line
            if characters[char] >= finish_line:
                print(f"{char} wins!")
                return

        print_race(characters)
        time.sleep(0.5)  # Adjust the speed of the race

if __name__ == "__main__":
    race()
