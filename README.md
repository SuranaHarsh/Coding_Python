# Coding_Python
Coding on the go as learning python



# Creating a calculator for practicing Python coding


# Function for Addition of 2 variables
def add(num1, num2):
	return num1 + num2


# Function for Subtraction of 2 variables
def sub(num1, num2):
	return num1 - num2

	
# Function for Multiplication of 2 variables
def mul(num1, num2):
	return num1 * num2
	

# Function for Division of 2 variables
def div(num1, num2):
	try:
		return num1 / num2
	except ZeroDivisionError:
		print("Handled div by zero. Returning Zero.")
		return 0
		

# Function for Squaring of a variables
def sq(num1):
	return num1 * num1


def runOperation(operation, num1, num2):
	"""Determines the operation to run based on the operation argument which should be passed in as an integer"""
	# Determine operation
	if (operation == 1):
		print("Adding...")
		print(add(num1, num2))
	elif (operation == 2):
		print("Subtracting...")
		print(sub(num1, num2))
	elif (operation == 3):
		print("Multiplying...")
		print(mul(num1, num2))
	elif (operation == 4):
		print("Dividing...")
		print(div(num1, num2))
	elif (operation == 5):
		print("Squaring...")
		print(sq(num1))	
	else:
		print("I don't understand. Please try again.")


# Main Function for calculator
def main():
	"""Allows user to run basic calculator operation with two numbers"""
	user_continue = True
	while user_continue:
		# Run calculator operation again
		validInput = False
		while not validInput:
			# Get user Input
			try:
				num1 = float(input("What is number 1? "))
				num2 = float(input("What is number 2? "))
				operation = int(input("What you want to do? 1.Add, 2.Subtract, 3.Multiply, 4.Divide, 5.Square. Enter a number: "))
				validInput = True
			except ValueError:
				print("Invalid Input. Please try again")
			except:
				print("Unknown Error")
			runOperation(operation, num1, num2)
			if (operation >= 6):
				continue
			confirmation = True
			while confirmation:
				# Ask user if wants to continue
				user_yn = int(input("Do you want to continue using calculator? 1. Yes, 2. No. Enter a number: "))
				if (user_yn == 1):
					user_continue = True
					confirmation = False
				elif (user_yn == 2):
					user_continue = False
					confirmation = False
				else:
					print("I don't understand. Please try again.")


main()



