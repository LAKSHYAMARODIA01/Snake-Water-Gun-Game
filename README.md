# Author : Lakshya Marodia(18_Sep_24)
# 🐍 Snake-Water-Gun Game

A Python implementation of the popular **Snake-Water-Gun** game, similar to Rock-Paper-Scissors, where:
- Snake drinks Water 🐍 > 💧
- Gun shoots Snake 🔫 > 🐍
- Water douses Gun 💧 > 🔫

This repository includes **two methods** for determining the winner between the player and the computer.

## Rules of the Game:
- **Snake** (represented as `1`) beats Water.
- **Water** (represented as `-1`) beats Gun.
- **Gun** (represented as `0`) beats Snake.
- If both the player and the computer choose the same, it's a draw.

## How to Play
1. The computer randomly selects **Snake**, **Water**, or **Gun**.
2. The player chooses one of the following:
   - `s` for Snake
   - `w` for Water
   - `g` for Gun
3. The game evaluates the winner based on predefined rules.

## Method 1: Conditional Logic
This method uses explicit conditional statements to compare the player's and the computer's choices.

### Code Snippet:

```python
import random

computer = random.choice([-1, 0, 1])
youstr = input("Enter your choice: ")
youDict = {"s": 1, "w": -1, "g": 0}
reverseDict = {1: "Snake", -1: "Water", 0: "Gun"}

you = youDict[youstr]

print(f"You chose {reverseDict[you]}\nComputer chose {reverseDict[computer]}")

if computer == you:
    print("It's a draw")
else:
    if computer == -1 and you == 1:  # Snake drinks Water
        print("You win!")
    elif computer == -1 and you == 0:  # Water douses Gun
        print("You Lose!")
    elif computer == 1 and you == -1:  # Snake drinks Water
        print("You lose!")
    elif computer == 1 and you == 0:  # Gun shoots Snake
        print("You Win!")
    elif computer == 0 and you == -1:  # Water douses Gun
        print("You Win!")
    elif computer == 0 and you == 1:  # Gun shoots Snake
        print("You Lose!")
    else:
        print("Something went wrong!")
```

### Explanation:
- The program checks all possible combinations of player and computer choices.
- It prints the winner based on the results of those comparisons.

---

## Method 2: Subtraction Logic
This method simplifies the logic by calculating the difference between the player's and the computer's choices.

### Code Snippet:

```python
import random

computer = random.choice([-1, 0, 1])
youstr = input("Enter your choice: ")
youDict = {"s": 1, "w": -1, "g": 0}
reverseDict = {1: "Snake", -1: "Water", 0: "Gun"}

you = youDict[youstr]

print(f"You chose {reverseDict[you]}\nComputer chose {reverseDict[computer]}")

if computer == you:
    print("It's a draw")
else:
    if (computer - you) == -1 or (computer - you) == 2:
        print("You lose!")
    else:
        print("You win!")
```

### Explanation:
- The game computes the difference between the computer's and the player's choices.
- Based on the result of `computer - you`, the game determines if the player wins or loses.

---

## How to Run the Code:
1. Clone this repository.
2. Run the Python file in a terminal:
   ```bash
   python snake_water_gun.py
   ```
3. Follow the prompts to input your choice.

Enjoy the game and may the best player win!
