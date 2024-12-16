# Expense Tracker Program

# Function to display the menu
def show_menu():
    print("\nExpense Tracker")
    print("1. Add an expense")
    print("2. View all expenses")
    print("3. Calculate total expenses")
    print("4. Exit")

# Function to add an expense
def add_expense(expenses):
    date = input("Enter the date (YYYY-MM-DD): ")
    description = input("Enter the description of the expense: ")
    amount = float(input("Enter the amount: "))
    expenses.append({"date": date, "description": description, "amount": amount})
    print("Expense added successfully!")

# Function to view all expenses
def view_expenses(expenses):
    if not expenses:
        print("No expenses recorded.")
    else:
        print("\nExpenses:")
        print("{:<15} {:<20} {:<10}".format("Date", "Description", "Amount"))
        print("-" * 45)
        for expense in expenses:
            print("{:<15} {:<20} {:<10.2f}".format(expense["date"], expense["description"], expense["amount"]))

# Function to calculate total expenses
def calculate_total(expenses):
    if not expenses:
        print("No expenses recorded.")
    else:
        total = sum(expense["amount"] for expense in expenses)
        print(f"Total Expenses: ₹{total:.2f}")

# Main program
def main():
    expenses = []  # List to store expenses
    while True:
        show_menu()
        choice = input("Choose an option: ")
        
        if choice == '1':
            add_expense(expenses)
        elif choice == '2':
            view_expenses(expenses)
        elif choice == '3':
            calculate_total(expenses)
        elif choice == '4':
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

# Run the program
if _name_ == "_main_":
    main()
