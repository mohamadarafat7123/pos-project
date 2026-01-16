[# POS System - Console Application.py](https://github.com/user-attachments/files/24676675/POS.System.-.Console.Application.py)
# POS System - Console Application

users = {
    "cashier": "1234"
}

products = {
    "apple": {"price": 2, "quantity": 10},
    "banana": {"price": 1, "quantity": 20}
}

def login():
    print("=== Login ===")
    username = input("Username: ")
    password = input("Password: ")

    if username in users and users[username] == password:
        print("Login successful!\n")
        return True
    else:
        print("Login failed!")
        return False

def sell_product():
    print("=== Sell Product ===")
    product_name = input("Enter product name: ").lower()

    if product_name in products:
        qty = int(input("Enter quantity: "))

        if qty <= products[product_name]["quantity"]:
            total_price = qty * products[product_name]["price"]
            products[product_name]["quantity"] -= qty

            print("Product sold successfully!")
            print("Total price:", total_price)
        else:
            print("Not enough quantity!")
    else:
        print
