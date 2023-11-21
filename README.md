# Define the available pizzas, toppings, and their prices
available_pizzas = {
    'margarita': 5,
    'pollo': 7,
    '4cheese': 6,
    'bolognese': 8,
    'vegetarian': 6.5
}

available_toppings = {
    'mushroom': 1,
    'onions': 2,
    'green pepper': 3,
    'extra cheese': 4
}

# Initialize variables
order = []

# Welcome message
print("Welcome to the Good Pizza Game!")

# Ordering process
while True:
    print("\nAvailable Pizzas:")
    for pizza, price in available_pizzas.items():
        print(f"{pizza} - ${price}")

    pizza_choice = input("Choose a pizza or type 'done' to finish your order: ").lower()

    if pizza_choice == 'done':
        break

    if pizza_choice in available_pizzas:
        order.append(pizza_choice)
        print(f"You've added {pizza_choice} to your order.")

        while True:
            print("\nAvailable Toppings:")
            for topping, price in available_toppings.items():
                print(f"{topping} - ${price}")

            topping_choice = input("Add a topping or type 'done' to finish this pizza: ").lower()

            if topping_choice == 'done':
                break

            if topping_choice in available_toppings:
                order.append(topping_choice)
                print(f"You've added {topping_choice} to your pizza.")

    else:
        print(f"Sorry, we don't have {pizza_choice} on the menu.")

# Calculate the total price
total_price = sum([available_pizzas[item] if item in available_pizzas else available_toppings[item] for item in order])

# Display the order and total price
print("\nYour order:")
for item in order:
    print(item)

print(f"Total Price: ${total_price}")

print("Thank you for playing the Good Pizza Game!")

