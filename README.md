# calculator-cli-app
def add(x, y):
    """Return the sum of x and y"""
    return x + y

def subtract(x, y):
    """Return the difference of x and y"""
    return x - y

def multiply(x, y):
    """Return the product of x and y"""
    return x * y

def divide(x, y):
    """Return the division of x by y, handle division by zero"""
    if y == 0:
        return "Error: Division by zero!"
    return x / y

def get_numbers():
    """Prompt user to enter two numbers and return them as floats"""
    try:
        num1 = float(input("Enter the first number: "))
        num2 = float(input("Enter the second number: "))
        return num1, num2
    except ValueError:
        print("Invalid input. Please enter numeric values.")
        return None, None

def main():
    print(" Welcome to the Command-Line Calculator ")

    while True:
        print("\nChoose an operation:")
        print("1. Addition (+)")
        print("2. Subtraction (-)")
        print("3. Multiplication (*)")
        print("4. Division (/)")
        print("5. Exit")

        choice = input("Enter your choice (1/2/3/4/5): ")

        if choice == '5':
            print("👋 Exiting the calculator. Thank you!")
            break

        if choice in ['1', '2', '3', '4']:
            num1, num2 = get_numbers()
            if num1 is None or num2 is None:
                continue

            if choice == '1':
                print(f"Result: {num1} + {num2} = {add(num1, num2)}")
            elif choice == '2':
                print(f"Result: {num1} - {num2} = {subtract(num1, num2)}")
            elif choice == '3':
                print(f"Result: {num1} * {num2} = {multiply(num1, num2)}")
            elif choice == '4':
                result = divide(num1, num2)
                print(f"Result: {num1} / {num2} = {result}")
        else:
            print(" Invalid choice. Please select a number from 1 to 5.")

if __name__ == "__main__":
    main()

