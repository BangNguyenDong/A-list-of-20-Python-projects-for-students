# A-list-of-20-Python-projects-for-students

### Project 1: Simple Calculator
**Description:** Create a simple calculator program that can perform basic arithmetic operations like addition, subtraction, multiplication, and division.
**Instructions:**
1. Create a function for each arithmetic operation.
2. Take user input for the two numbers and the operation.
3. Call the respective function and display the result.

#Code

def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error! Division by zero."
    return x / y

print("Select operation:")
print("1.Add")
print("2.Subtract")
print("3.Multiply")
print("4.Divide")

choice = input("Enter choice(1/2/3/4): ")

num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))

if choice == '1':
    print(num1, "+", num2, "=", add(num1, num2))
elif choice == '2':
    print(num1, "-", num2, "=", subtract(num1, num2))
elif choice == '3':
    print(num1, "*", num2, "=", multiply(num1, num2))
elif choice == '4':
    print(num1, "/", num2, "=", divide(num1, num2))
else:
    print("Invalid input")


### Project 2: Number Guessing Game
**Description:** Create a game where the computer randomly selects a number between 1 and 100, and the player has to guess it.
**Instructions:**
1. Generate a random number.
2. Take user input for the guess.
3. Compare the guess with the generated number and provide feedback.

#Code

import random

number_to_guess = random.randint(1, 100)
guess = None

print("Guess the number between 1 and 100")

while guess != number_to_guess:
    guess = int(input("Enter your guess: "))
    
    if guess < number_to_guess:
        print("Higher")
    elif guess > number_to_guess:
        print("Lower")
    else:
        print("Correct! You guessed the number.")


### Project 3: Contact Book
**Description:** Create a program to manage a contact book where users can add, delete, and display contacts.
**Instructions:**
1. Create functions to add, delete, and display contacts.
2. Use a dictionary to store contacts.
3. Provide a menu for user interaction.

#Code

contacts = {}

def add_contact(name, number):
    contacts[name] = number
    print(f"Contact {name} added.")

def delete_contact(name):
    if name in contacts:
        del contacts[name]
        print(f"Contact {name} deleted.")
    else:
        print(f"Contact {name} not found.")

def display_contacts():
    if contacts:
        for name, number in contacts.items():
            print(f"{name}: {number}")
    else:
        print("No contacts available.")

while True:
    print("\n1. Add contact")
    print("2. Delete contact")
    print("3. Display contacts")
    print("4. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        name = input("Enter name: ")
        number = input("Enter number: ")
        add_contact(name, number)
    elif choice == '2':
        name = input("Enter name to delete: ")
        delete_contact(name)
    elif choice == '3':
        display_contacts()
    elif choice == '4':
        break
    else:
        print("Invalid choice")


### Project 4: Simple Chat History
**Description:** Create a program to store and display chat history.
**Instructions:**
1. Use a list to store chat messages.
2. Create functions to add and display messages.

#Code

chat_history = []

def add_message(message):
    chat_history.append(message)

def display_chat_history():
    for message in chat_history:
        print(message)

while True:
    print("\n1. Add message")
    print("2. Display chat history")
    print("3. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        message = input("Enter your message: ")
        add_message(message)
    elif choice == '2':
        display_chat_history()
    elif choice == '3':
        break
    else:
        print("Invalid choice")


### Project 5: Student Grade Manager
**Description:** Create a program to manage student grades.
**Instructions:**
1. Use a dictionary to store student names and their grades.
2. Create functions to add, delete, and display grades.
3. Calculate the average grade for each student.

#Code

grades = {}

def add_grade(student, grade):
    if student in grades:
        grades[student].append(grade)
    else:
        grades[student] = [grade]
    print(f"Grade {grade} added for {student}.")

def delete_grade(student):
    if student in grades:
        del grades[student]
        print(f"Grades for {student} deleted.")
    else:
        print(f"No grades found for {student}.")

def display_grades():
    for student, grades_list in grades.items():
        average = sum(grades_list) / len(grades_list)
        print(f"{student}: {grades_list} (Average: {average:.2f})")

while True:
    print("\n1. Add grade")
    print("2. Delete grade")
    print("3. Display grades")
    print("4. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        student = input("Enter student name: ")
        grade = float(input("Enter grade: "))
        add_grade(student, grade)
    elif choice == '2':
        student = input("Enter student name to delete: ")
        delete_grade(student)
    elif choice == '3':
        display_grades()
    elif choice == '4':
        break
    else:
        print("Invalid choice")


### Project 6: Rock-Paper-Scissors Game
**Description:** Create a Rock-Paper-Scissors game between a player and the computer.
**Instructions:**
1. Generate a random choice for the computer.
2. Take user input for their choice.
3. Compare the choices and determine the winner.

#Code

import random

def get_computer_choice():
    choices = ["rock", "paper", "scissors"]
    return random.choice(choices)

def determine_winner(player, computer):
    if player == computer:
        return "It's a tie!"
    elif (player == "rock" and computer == "scissors") or \
         (player == "scissors" and computer == "paper") or \
         (player == "paper" and computer == "rock"):
        return "You win!"
    else:
        return "You lose!"

while True:
    player_choice = input("Enter rock, paper, or scissors (or 'exit' to quit): ").lower()
    if player_choice == 'exit':
        break
    if player_choice not in ["rock", "paper", "scissors"]:
        print("Invalid choice, try again.")
        continue
    computer_choice = get_computer_choice()
    print(f"Computer chose: {computer_choice}")
    result = determine_winner(player_choice, computer_choice)
    print(result)


### Project 7: Random Password Generator
**Description:** Create a program to generate random passwords.
**Instructions:**
1. Take user input for the desired length of the password.
2. Generate a password with random characters.

#Code

import random
import string

def generate_password(length):
    characters = string.ascii_letters + string.digits + string.punctuation
    return ''.join(random.choice(characters) for i in range(length))

length = int(input("Enter the desired length of the password: "))
password = generate_password(length)
print(f"Generated password: {password}")


### Project 8: Library Management System
**Description:** Create a program to manage a library of books.
**Instructions:**
1. Use a list to store book details.
2. Create functions to add, delete, and display books.

#Code

library = []

def add_book(title, author):
    library.append({"title": title, "author": author})
    print(f"Book '{title}' by {author} added to the library.")

def delete_book(title):
    global library
    library = [book for book in library if book['title'] != title]
    print(f"Book '{title}' deleted from the library.")

def display_books():
    for book in library:
        print(f"{book['title']} by {book['author']}")

while True:
    print("\n1. Add book")
    print("2. Delete book")
    print("3. Display books")
    print("4. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        title = input("Enter book title: ")
        author = input("Enter book author: ")
        add_book(title, author)
    elif choice == '2':
        title = input("Enter book title to delete: ")
        delete_book(title)
    elif choice == '3':
        display_books()
    elif choice == '4':
        break
    else:
        print("Invalid choice")


### Project

 9: Weather Report Generator
**Description:** Create a program that generates a random weather report for a given city.
**Instructions:**
1. Take user input for the city name.
2. Generate a random weather condition.

#Code

import random

def get_weather():
    weather_conditions = ["Sunny", "Rainy", "Cloudy", "Windy", "Snowy"]
    return random.choice(weather_conditions)

city = input("Enter city name: ")
weather = get_weather()
print(f"Weather in {city}: {weather}")


### Project 10: Simple Quiz Game
**Description:** Create a quiz game with multiple questions.
**Instructions:**
1. Create a list of questions and answers.
2. Take user input for answers.
3. Calculate and display the score.

#Code

questions = [
    {"question": "What is the capital of France?", "answer": "Paris"},
    {"question": "What is 2 + 2?", "answer": "4"},
    {"question": "What is the color of the sky?", "answer": "Blue"}
]

score = 0

for q in questions:
    answer = input(q["question"] + " ")
    if answer.lower() == q["answer"].lower():
        score += 1

print(f"Your score is: {score}/{len(questions)}")


### Project 11: To-Do List Manager
**Description:** Create a program to manage a to-do list.
**Instructions:**
1. Use a list to store to-do items.
2. Create functions to add, delete, and display to-do items.

#Code

to_do_list = []

def add_task(task):
    to_do_list.append(task)
    print(f"Task '{task}' added.")

def delete_task(task):
    if task in to_do_list:
        to_do_list.remove(task)
        print(f"Task '{task}' deleted.")
    else:
        print(f"Task '{task}' not found.")

def display_tasks():
    print("To-Do List:")
    for task in to_do_list:
        print(f"- {task}")

while True:
    print("\n1. Add task")
    print("2. Delete task")
    print("3. Display tasks")
    print("4. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        task = input("Enter task: ")
        add_task(task)
    elif choice == '2':
        task = input("Enter task to delete: ")
        delete_task(task)
    elif choice == '3':
        display_tasks()
    elif choice == '4':
        break
    else:
        print("Invalid choice")


### Project 12: Currency Converter
**Description:** Create a program to convert currency from one unit to another.
**Instructions:**
1. Use a dictionary to store exchange rates.
2. Take user input for the amount and currency units.
3. Calculate and display the converted amount.

#Code

exchange_rates = {
    "USD": 1.0,
    "EUR": 0.85,
    "JPY": 110.53,
    "GBP": 0.74
}

def convert_currency(amount, from_currency, to_currency):
    if from_currency not in exchange_rates or to_currency not in exchange_rates:
        return "Invalid currency unit"
    return amount * exchange_rates[to_currency] / exchange_rates[from_currency]

amount = float(input("Enter amount: "))
from_currency = input("Enter from currency (USD, EUR, JPY, GBP): ").upper()
to_currency = input("Enter to currency (USD, EUR, JPY, GBP): ").upper()

converted_amount = convert_currency(amount, from_currency, to_currency)
print(f"{amount} {from_currency} is {converted_amount:.2f} {to_currency}")


### Project 13: BMI Calculator
**Description:** Create a program to calculate the Body Mass Index (BMI) from user input.
**Instructions:**
1. Take user input for weight and height.
2. Calculate BMI and provide feedback based on the value.

#Code

def calculate_bmi(weight, height):
    bmi = weight / (height ** 2)
    if bmi < 18.5:
        return bmi, "Underweight"
    elif 18.5 <= bmi < 24.9:
        return bmi, "Normal weight"
    elif 25 <= bmi < 29.9:
        return bmi, "Overweight"
    else:
        return bmi, "Obesity"

weight = float(input("Enter weight in kg: "))
height = float(input("Enter height in meters: "))

bmi, category = calculate_bmi(weight, height)
print(f"Your BMI is {bmi:.2f}, which is considered {category}")


### Project 14: Simple Text Editor
**Description:** Create a simple text editor program.
**Instructions:**
1. Use file handling to open, edit, and save text files.
2. Provide a menu for user interaction.

#Code

def open_file(filename):
    with open(filename, 'r') as file:
        return file.read()

def save_file(filename, content):
    with open(filename, 'w') as file:
        file.write(content)

while True:
    print("\n1. Open file")
    print("2. Save file")
    print("3. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        filename = input("Enter filename: ")
        content = open_file(filename)
        print(f"Content of {filename}:\n{content}")
    elif choice == '2':
        filename = input("Enter filename: ")
        content = input("Enter content to save: ")
        save_file(filename, content)
        print(f"Content saved to {filename}")
    elif choice == '3':
        break
    else:
        print("Invalid choice")


### Project 15: Tic-Tac-Toe Game
**Description:** Create a Tic-Tac-Toe game for two players.
**Instructions:**
1. Create a 3x3 grid.
2. Take turns for each player to mark 'X' or 'O'.
3. Determine the winner or if the game is a draw.

#Code

def print_board(board):
    for row in board:
        print(" | ".join(row))
        print("-" * 5)

def check_winner(board):
    for row in board:
        if row[0] == row[1] == row[2] and row[0] != " ":
            return row[0]
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] and board[0][col] != " ":
            return board[0][col]
    if board[0][0] == board[1][1] == board[2][2] and board[0][0] != " ":
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] and board[0][2] != " ":
        return board[0][2]
    return None

board = [[" " for _ in range(3)] for _ in range(3)]
current_player = "X"

while True:
    print_board(board)
    row = int(input(f"Player {current_player}, enter row (0, 1, 2): "))
    col = int(input(f"Player {current_player}, enter column (0, 1, 2): "))
    if board[row][col] == " ":
        board[row][col] = current_player
        winner = check_winner(board)
        if winner:
            print_board(board)
            print(f"Player {winner} wins!")
            break
        if all(board[row][col] != " " for row in range(3) for col in range(3)):
            print_board(board)
            print("The game is a draw!")
            break
        current_player = "O" if current_player == "X" else "X"
    else:
        print("Cell already taken, choose another.")


### Project 16: Hangman Game
**Description:** Create a Hangman game where the player guesses letters in a word.
**Instructions:**
1. Select a random word.
2. Take user input for guesses.
3. Display the word with guessed letters and track incorrect guesses.

#Code

import random

def display_word(word, guessed_letters):
    return " ".join([letter if letter in guessed_letters else "_" for letter in word])

words = ["python", "hangman", "programming", "computer"]
word_to_guess = random.choice(words)
guessed_letters = set()
incorrect_guesses = 0

while incorrect_guesses < 6:
    print(display_word(word_to_guess, guessed_letters))
    guess = input("Guess a letter: ").lower()
    if guess in word_to_guess:
        guessed_letters.add(guess)
        if all(letter in guessed_letters for letter in word_to_guess):
            print(f"Congratulations! You guessed the word: {word_to_guess}")
            break
    else:
        incorrect_guesses += 1
        print(f"Incorrect guess. You have {6 - incorrect_guesses} guesses left.")
else:
    print(f"Game over. The word was: {word_to_guess}")


### Project 17: Flashcard Quiz
**Description:** Create a flashcard quiz to help study vocabulary.
**Instructions:**
1. Use a dictionary to store questions and answers.
2. Take user input for answers.


3. Display the correct answers and score.

#Code

flashcards = {
    "What is the capital of France?": "Paris",
    "What is the largest ocean?": "Pacific",
    "What is 3 + 5?": "8"
}

score = 0

for question, answer in flashcards.items():
    user_answer = input(question + " ")
    if user_answer.lower() == answer.lower():
        score += 1

print(f"Your score is: {score}/{len(flashcards)}")


### Project 18: Countdown Timer
**Description:** Create a countdown timer that takes user input for the duration.
**Instructions:**
1. Take user input for the number of seconds.
2. Use a loop to countdown and display the remaining time.

#Code

import time

def countdown(seconds):
    while seconds:
        mins, secs = divmod(seconds, 60)
        time_format = '{:02d}:{:02d}'.format(mins, secs)
        print(time_format, end='\r')
        time.sleep(1)
        seconds -= 1
    print("Time's up!")

seconds = int(input("Enter the time in seconds: "))
countdown(seconds)


### Project 19: Email Slicer
**Description:** Create an email slicer to extract username and domain from an email address.
**Instructions:**
1. Take user input for the email address.
2. Split the email address to get the username and domain.

#Code

def email_slicer(email):
    username, domain = email.split("@")
    return username, domain

email = input("Enter your email address: ")
username, domain = email_slicer(email)
print(f"Username: {username}")
print(f"Domain: {domain}")


### Project 20: Mad Libs Generator
**Description:** Create a Mad Libs game where the user inputs words to complete a story.
**Instructions:**
1. Take user input for various parts of speech.
2. Insert the inputs into a predefined story template.

#Code

story_template = """
Once upon a time, there was a {adjective} {noun} who loved to {verb}. 
Every day, the {noun} would {verb} in the {place}. 
"""

adjective = input("Enter an adjective: ")
noun = input("Enter a noun: ")
verb = input("Enter a verb: ")
place = input("Enter a place: ")

story = story_template.format(adjective=adjective, noun=noun, verb=verb, place=place)
print(story)


These projects will help students practice their Python programming skills by applying what they have learned in practical and fun ways. Each project comes with clear instructions and code examples to get them started.
