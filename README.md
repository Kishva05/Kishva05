# Initialize variables
income = 0
expenses = 0

# Input income and expenses
try:
    income_input = input("Enter your monthly income in Myr: ")
    expenses_input = input("Enter your total monthly expenses in Myr: ")

    # Remove currency symbols and any non-numeric characters
    income = float(''.join(filter(str.isdigit, income_input)))
    expenses = float(''.join(filter(str.isdigit, expenses_input)))
except ValueError:
    print("Invalid input. Please enter valid numbers for income and expenses.")
    exit()

# Calculate the budget surplus or deficit
budget = income - expenses

# Determine financial status
if budget > 0:
    financial_status = "You have a budget surplus of Myr {:.2f}.".format(budget)
elif budget == 0:
    financial_status = "You have a balanced budget."
else:
    financial_status = "You have a budget deficit of Myr {:.2f}.".format(abs(budget))

# Display the financial status
print("\nFinancial Status:")
print(financial_status)

