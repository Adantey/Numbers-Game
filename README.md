# Numbers-Game
in this game, computer selects a random number and it is the users duty guess that number


#code
import art
import random
print(art.logo)

print("Welcome to the Number Guessing Game")
print("im thinking of a number between 1 and 100")
continue_play = True
computers_random_choice = random.randint(1,100)
def compare(random_number):
    """this function compares the random number chosen my the computer and the guess of the User"""
    global computers_random_choice
    global continue_play
    if random_number > computers_random_choice:
        return "Too high \n guess again"
    elif random_number < computers_random_choice:
        return "Too low \n guess again"
    else:
        continue_play = False
        return f"you got it! the answer was {computers_random_choice}"

def easy():
    """This function is selected when the user chooses the level of difficulty as easy"""
    for attempts in range(10, 0, -1):
        print(f"you have {attempts} attempts remaining")
        users_guess = int(input("make a guess :\n"))
        print(compare(users_guess))
        if "got it" in (compare(users_guess)):
            break
        if attempts == 1:
            print("You're out of guesses, you lose!! ")

def hard():
    """This function is selected when the user chooses the level of difficulty as hard"""
    for attempts in range(5, 0, -1):
        print(f"you have {attempts} attempts remaining")
        users_guess = int(input("make a guess :\n"))
        print(compare(users_guess))
        if "got it" in (compare(users_guess)):
            break
        if attempts == 1:
            print("You're out of guesses, you lose!! ")


def play_game():
    """this function is called to stat=rt the game"""
    another_game = False
    while not another_game:
        difficulty= input("choose difficulty, Type 'hard' or 'easy' : \n").lower()
        if difficulty == "easy":
            easy()
        elif difficulty == "hard":
            hard()
        else:
            print("choose between easy and hard")
            continue
        another = input("would you like to play another game 'y' or  'n': \n")
        if another == 'y':
            print("\n" *20)
            print(art.logo)
            continue
        else:
            return


play_game()
