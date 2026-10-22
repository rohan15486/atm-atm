# ATM Withdrawal Program
# A simple ATM simulation using exception handling.

balance = 5000.0
correct_pin = "1234"

print("===== WELCOME TO MINI ATM =====")

pin = input("Enter your 4-digit PIN: ")

if pin == correct_pin:
    print("\n1. Check Balance")
    print("2. Withdraw Money")
    choice = input("Enter your choice: ")

    if choice == "1":
        print("Your current balance is Rs.", balance)
    elif choice == "2":
        try:
            amount = float(input("Enter withdrawal amount: Rs. "))

            if amount <= 0:
                print("Please enter an amount greater than zero.")
            elif amount > balance:
                print("Insufficient balance.")
            else:
                balance = balance - amount
                print("Please collect your cash.")
                print("Remaining balance: Rs.", balance)

        except ValueError:
            print("Invalid amount. Please enter numbers only.")
    else:
        print("Invalid choice. Please select 1 or 2.")
else:
    print("Incorrect PIN. Access denied.")

print("\nThank you for using Mini ATM.")
