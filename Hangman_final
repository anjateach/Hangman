import getpass

username1 = input("Player 1, please enter your name: ")
username2 = input("Player 2, please enter your name: ")

# f infront takes away + from combining strings
print(f"Hello, {username1} and {username2}! Welcome to Hangman!")
print("Let's begin!")

# To make the word appear invisible use getpass
secretword = getpass.getpass(f"{username1}, enter your word: ").lower()

# Replace: s = ""
# for i in range(len(secretword)):
#     s+="_"
s = '_' * len(secretword)
print(f"{username2} the word to guess is {s}")

# List to store guessed letters
guessedletters = []
guessesleft = 10

# While loop to check completeness of word guesses
while ("_" in s):
    # To ensure the number of guesses is not surpassed:
    if guessesleft <= 10:
        letter = input(f"{username2}, what is your letter guess? ").lower()
        
        # Error checking: ensure letter entered is a letter and not a character; checks for more than one character entry
        if (not letter.isalpha() or len(letter) != 1):
            print("\nNot a valid entry. Please enter a valid single letter.\n")

        # Error checking: make sure letter has not been guessed already
        elif (letter in guessedletters):
            print("\nYou have already guessed this letter. Please pick a new letter.\n")

        else:
            if (letter in secretword):
                print(f"\nYou guessed the correct letter {letter}! You still have {guessesleft} guesses left.")
                
                for i in range(len(secretword)):
                    if (letter == secretword[i]):
                        s = s[:i] + letter + s[i+1:]
                        
            else:
                guessesleft -= 1
                print(f"\nSorry, {letter} is not in the word. You have {guessesleft} guesses left.")
            
            print(f"The word so far is: {s}\n")

            # To insert into specific location in list:
            # guessedletters.insert(k, letter)
            # k = k + 1

            # To insert into list at the end:
            guessedletters.append(letter)
    else:
        print("Sorry you have no more guesses left. Game Over.")
        break

if guessesleft <= 10:  
    print(f"\nCONGRATULATIONS! You guess the secret word {secretword}!")
