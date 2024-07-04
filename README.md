# RestaurantMenu2
import time

menu = {
    "Burger": 199,
    "Pizza": 299,
    "Salad": 399,
    "Soda": 169,
    "Coffee": 119
}

def menu2():
    print("-" * 50)
    print("MENU")
    print("-" * 50)
    for key, item in menu.items():
        print("{}\t{}".format(key, item))

def user_input():
    while True:
        print("-" * 50)
        print("HOME")
        print("-" * 50)
        print("\n1. View Menu")
        print("2. Add Items to Cart")
        print("3. Reset Cart")
        print("4. View Items and Bill")
        print("5. EXIT")
        choose = int(input("Enter your choice: "))
        
        if choose == 1:
            print("Loading Menu...")
            time.sleep(2)
            menu2()
        elif choose == 2:
            cart1()
        elif choose == 3:
            cart.clear()
            print("Cart is Reset")
        elif choose == 4:
            print("Billing the Items:", cart)
            time.sleep(1.5)
            billing()
        elif choose == 5:
            break
        else:
            print("Invalid choice. Please try again.")

cart = []

def cart1():
    while True:
        item = input("Enter the Item to add to cart: ")
        if item.lower() == "done":
            print("{} are Added to the cart".format(cart))
            break
        if item in menu:
            cart.append(item)
            print("{} is Added to the Cart".format(item))
        else:
            print("{} is unavailable".format(item))

def billing():
    if not cart:
        print("Cart is empty")
        return
    total = 0
    print("-" * 50)
    print("CART ITEMS AND BILL")
    print("-" * 50)
    for item in cart:
        if item in menu:
            price = menu[item]
            print("{}\t{}".format(item, price))
            total += price
    print("-" * 50)
    print("Total Bill: {}".format(total))

user_input()
