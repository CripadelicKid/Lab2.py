# Lab2.py
# IT1114/Section W01
# Dan Suero
# Lab 2
# Due Date: 01/26/2025
# Purpose: This program is able to calculate the total food cost for the KSU Hackathon, accounting for discount rates as well as the cost of delivery.
# Resources used: Notes from Lab as well as notes from zoom session

# Get input from user
num_pizza_orders = int(input("Number of pizza orders:"))
num_salad_orders = int(input("Number of salad orders:"))
"""
First the program takes inputs from the user: the number of pizza orders and number of salad orders.
"""
# Define the constants
pizza_cost_per_person = 15.99
salad_cost_per_person = 7.99
pizza_slices = 12
pizza_disc_threshold = 10
salad_disc_threshold = 10
disc_rate = 0.15
delivery_rate = 0.07
min_delivery_charge = 20
"""
Then the program lays out the constants needed to do the math to figure out the total cost.
"""
# Calculate the number of whole pizzas needed
total_slices_needed = num_pizza_orders * 3
num_whole_pizzas = (total_slices_needed + pizza_slices - 1) //  pizza_slices
"""
Then the program calculates the number of pizzas needed based on the number of pizza orders. Each person will get 3 slices, and each pizza has 12 slices.
"""
# Calculate the cost of pizza and salads before disc.
pizza_cost = num_whole_pizzas * pizza_cost_per_person
salad_cost = num_salad_orders * salad_cost_per_person
"""
Then the program calculates the total cost of pizzas and salads before discounts.
"""
# Calculate discounts
pizza_disc = 0
salad_disc = 0 
if num_pizza_orders > pizza_disc_threshold:
    pizza_disc = pizza_cost * disc_rate
if num_salad_orders > salad_disc_threshold:
    salad_disc = salad_cost * disc_rate
"""
Here the program determines whether or not the discount rate will be applied. If more than 10 pizzas or more than 10 salads are ordered, a 15% discount is applied.
"""
# Calculate the delivery cost
total_cost_before_disc = pizza_cost + salad_cost
delivery_cost = max(total_cost_before_disc * disc_rate, min_delivery_charge)
"""
Then the program calculates the delivery charge, 7% being applied to the total order before discounts, or the 20$ minimum charge; whichever is the greater value.
"""
# Calculate the total cost
total_cost = total_cost_before_disc - pizza_disc - salad_disc + delivery_cost
"""
Then the program calculates the total cost after discounts and adds the delivery cost.
"""
# Display the results
print(f"Pizzas ordered: {num_whole_pizzas}")
print(f"Pizza cost: ${pizza_cost}")
print(f"Salad cost: ${salad_cost}")
print(f"Pizza discount: ${pizza_disc}")
print(f"Salad discount: ${salad_disc}")
print(f"Delivery charge: ${delivery_rate}")
print(f"Total amount due: ${total_cost}")
"""
Finally, the program displays the results, being the number of pizzas, number of salads, costs, discounts and the total cost due for the KSU Hackathon.
"""
