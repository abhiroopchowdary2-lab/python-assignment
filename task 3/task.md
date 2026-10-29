# Multi-Plan Telecommunications Cost Optimization

# Input user requirements
data_usage = float(input("Enter data usage (GB): "))
call_minutes = int(input("Enter call minutes: "))
required_validity = int(input("Enter required validity (days): "))
budget = float(input("Enter your budget (Rs.): "))

# Validate inputs
if data_usage < 0 or call_minutes < 0 or required_validity <= 0 or budget < 0:
    print("Invalid input! Enter valid usage, validity and budget.")

else:
    # Mobile plans:
    # Name, Price, Data (GB), Calls (minutes), Validity (days)
    plans = [
        ["Plan A", 199, 2, 300, 28],
        ["Plan B", 299, 5, 600, 56],
        ["Plan C", 399, 10, 1000, 84],
        ["Plan D", 499, 15, 1500, 84]
    ]

    # Excess charges
    data_rate = 20       # Rs. per extra GB
    call_rate = 0.50     # Rs. per extra minute

    best_plan = None
    lowest_cost = float("inf")

    print("\n--- Mobile Plan Comparison ---")

    for plan in plans:
        name, price, data, calls, validity = plan

        extra_data = max(0, data_usage - data)
        extra_calls = max(0, call_minutes - calls)

        excess_charge = (
            extra_data * data_rate +
            extra_calls * call_rate
        )

        total_cost = price + excess_charge

        eligible = (
            validity >= required_validity
            and total_cost <= budget
        )

        print(f"\n{name}")
        print("Plan Price:", price)
        print("Excess Charges:", round(excess_charge, 2))
        print("Total Cost:", round(total_cost, 2))
        print("Validity:", validity, "days")
        print("Eligible:", "Yes" if eligible else "No")

        if eligible and total_cost < lowest_cost:
            lowest_cost = total_cost
            best_plan = name

    # Display most economical plan
    print("\n--- Best Plan ---")

    if best_plan is not None:
        print("Most Economical Plan:", best_plan)
        print("Total Cost: Rs.", round(lowest_cost, 2))
        print("Within budget and validity requirements.")
    else:
        print("No eligible plan found.")

        # Multi-Plan Telecommunications Cost Optimization

# Input user requirements
data_usage = float(input("Enter data usage (GB): "))
call_minutes = int(input("Enter call minutes: "))
required_validity = int(input("Enter required validity (days): "))
budget = float(input("Enter your budget (Rs.): "))

# Validate inputs
if data_usage < 0 or call_minutes < 0 or required_validity <= 0 or budget < 0:
    print("Invalid input! Enter valid usage, validity and budget.")

else:
    # Mobile plans:
    # Name, Price, Data (GB), Calls (minutes), Validity (days)
    plans = [
        ["Plan A", 199, 2, 300, 28],
        ["Plan B", 299, 5, 600, 56],
        ["Plan C", 399, 10, 1000, 84],
        ["Plan D", 499, 15, 1500, 84]
    ]

    # Excess charges
    data_rate = 20       # Rs. per extra GB
    call_rate = 0.50     # Rs. per extra minute

    best_plan = None
    lowest_cost = float("inf")

    print("\n--- Mobile Plan Comparison ---")

    for plan in plans:
        name, price, data, calls, validity = plan

        extra_data = max(0, data_usage - data)
        extra_calls = max(0, call_minutes - calls)

        excess_charge = (
            extra_data * data_rate +
            extra_calls * call_rate
        )

        total_cost = price + excess_charge

        eligible = (
            validity >= required_validity
            and total_cost <= budget
        )

        print(f"\n{name}")
        print("Plan Price:", price)
        print("Excess Charges:", round(excess_charge, 2))
        print("Total Cost:", round(total_cost, 2))
        print("Validity:", validity, "days")
        print("Eligible:", "Yes" if eligible else "No")

        if eligible and total_cost < lowest_cost:
            lowest_cost = total_cost
            best_plan = name

    # Display most economical plan
    print("\n--- Best Plan ---")

    if best_plan is not None:
        print("Most Economical Plan:", best_plan)
        print("Total Cost: Rs.", round(lowest_cost, 2))
        print("Within budget and validity requirements.")
    else:
        print("No eligible plan found.")

        # Multi-Plan Telecommunications Cost Optimization

# Input user requirements
data_usage = float(input("Enter data usage (GB): "))
call_minutes = int(input("Enter call minutes: "))
required_validity = int(input("Enter required validity (days): "))
budget = float(input("Enter your budget (Rs.): "))

# Validate inputs
if data_usage < 0 or call_minutes < 0 or required_validity <= 0 or budget < 0:
    print("Invalid input! Enter valid usage, validity and budget.")

else:
    # Mobile plans:
    # Name, Price, Data (GB), Calls (minutes), Validity (days)
    plans = [
        ["Plan A", 199, 2, 300, 28],
        ["Plan B", 299, 5, 600, 56],
        ["Plan C", 399, 10, 1000, 84],
        ["Plan D", 499, 15, 1500, 84]
    ]

    # Excess charges
    data_rate = 20       # Rs. per extra GB
    call_rate = 0.50     # Rs. per extra minute

    best_plan = None
    lowest_cost = float("inf")

    print("\n--- Mobile Plan Comparison ---")

    for plan in plans:
        name, price, data, calls, validity = plan

        extra_data = max(0, data_usage - data)
        extra_calls = max(0, call_minutes - calls)

        excess_charge = (
            extra_data * data_rate +
            extra_calls * call_rate
        )

        total_cost = price + excess_charge

        eligible = (
            validity >= required_validity
            and total_cost <= budget
        )

        print(f"\n{name}")
        print("Plan Price:", price)
        print("Excess Charges:", round(excess_charge, 2))
        print("Total Cost:", round(total_cost, 2))
        print("Validity:", validity, "days")
        print("Eligible:", "Yes" if eligible else "No")

        if eligible and total_cost < lowest_cost:
            lowest_cost = total_cost
            best_plan = name

    # Display most economical plan
    print("\n--- Best Plan ---")

    if best_plan is not None:
        print("Most Economical Plan:", best_plan)
        print("Total Cost: Rs.", round(lowest_cost, 2))
        print("Within budget and validity requirements.")
    else:
        print("No eligible plan found.")

        # Multi-Plan Telecommunications Cost Optimization

# Input user requirements
data_usage = float(input("Enter data usage (GB): "))
call_minutes = int(input("Enter call minutes: "))
required_validity = int(input("Enter required validity (days): "))
budget = float(input("Enter your budget (Rs.): "))

# Validate inputs
if data_usage < 0 or call_minutes < 0 or required_validity <= 0 or budget < 0:
    print("Invalid input! Enter valid usage, validity and budget.")

else:
    # Mobile plans:
    # Name, Price, Data (GB), Calls (minutes), Validity (days)
    plans = [
        ["Plan A", 199, 2, 300, 28],
        ["Plan B", 299, 5, 600, 56],
        ["Plan C", 399, 10, 1000, 84],
        ["Plan D", 499, 15, 1500, 84]
    ]

    # Excess charges
    data_rate = 20       # Rs. per extra GB
    call_rate = 0.50     # Rs. per extra minute

    best_plan = None
    lowest_cost = float("inf")

    print("\n--- Mobile Plan Comparison ---")

    for plan in plans:
        name, price, data, calls, validity = plan

        extra_data = max(0, data_usage - data)
        extra_calls = max(0, call_minutes - calls)

        excess_charge = (
            extra_data * data_rate +
            extra_calls * call_rate
        )

        total_cost = price + excess_charge

        eligible = (
            validity >= required_validity
            and total_cost <= budget
        )

        print(f"\n{name}")
        print("Plan Price:", price)
        print("Excess Charges:", round(excess_charge, 2))
        print("Total Cost:", round(total_cost, 2))
        print("Validity:", validity, "days")
        print("Eligible:", "Yes" if eligible else "No")

        if eligible and total_cost < lowest_cost:
            lowest_cost = total_cost
            best_plan = name

    # Display most economical plan
    print("\n--- Best Plan ---")

    if best_plan is not None:
        print("Most Economical Plan:", best_plan)
        print("Total Cost: Rs.", round(lowest_cost, 2))
        print("Within budget and validity requirements.")
    else:
        print("No eligible plan found.")

        Sample Output
        Enter data usage (GB): 4
Enter call minutes: 500
Enter required validity (days): 28
Enter your budget (Rs.): 350

--- Mobile Plan Comparison ---

Plan A
Plan Price: 199
Excess Charges: 120.0
Total Cost: 319.0
Validity: 28 days
Eligible: Yes

Plan B
Plan Price: 299
Excess Charges: 0.0
Total Cost: 299.0
Validity: 56 days
Eligible: Yes

Plan C
Plan Price: 399
Excess Charges: 0.0
Total Cost: 399.0
Validity: 84 days
Eligible: No

Plan D
Plan Price: 499
Excess Charges: 0.0
Total Cost: 499.0
Validity: 84 days
Eligible: No

--- Best Plan ---
Most Economical Plan: Plan B
Total Cost: Rs. 299.0
Within budget and validity requirements.

1. Problem Statement
To write a Python program for Multi-Plan Telecommunications Cost Optimization that compares different mobile plans based on data usage, call minutes, validity, and budget. The program calculates excess data and call charges, checks eligibility constraints, and identifies the most economical eligible plan.

2. Algorithm
1. Start the program.
2. Input data usage, call minutes, required validity, and budget.
3. Validate the inputs. If any value is invalid, display an error message.
4. Define mobile plans with price, data limit, call limit, and validity.
5. Calculate excess data and call charges for each plan.
6. Calculate the total cost by adding plan price and excess charges.
7. Check whether the plan satisfies the validity and budget constraints.
8. Select the eligible plan with the lowest total cost.
9. Display each plan's details and eligibility.
10. Display the most economical plan or a message if no plan is eligible.
11. Stop the program.

    3. Mermaid Flowchart
       
flowchart TD
    A([Start]) --> B[/Input usage, calls, validity and budget/]
    B --> C{Inputs valid?}
    C -- No --> D[/Display Invalid Input/]
    D --> Z([Stop])
    C -- Yes --> E[Initialize mobile plans]
    E --> F[Select next plan]
    F --> G[Calculate excess data and call charges]
    G --> H[Calculate total cost]
    H --> I{Validity sufficient and cost within budget?}
    I -- Yes --> J{Cost lower than current best?}
    J -- Yes --> K[Update best plan and lowest cost]
    J -- No --> L{More plans?}
    K --> L
    I -- No --> L
    L -- Yes --> F
    L -- No --> M{Eligible plan found?}
    M -- Yes --> N[/Display most economical plan/]
    M -- No --> O[/Display No Eligible Plan/]
    N --> Z
    O --> Z

4. Input
Example input values:
Enter data usage (GB): 4
Enter call minutes: 500
Enter required validity (days): 28
Enter your budget (Rs.): 350

Input Table
Input	Value
Data usage	4 GB
Call minutes	500 minutes
Required validity	28 days
Budget	₹350

5. Expected Output
   --- Best Plan ---
Most Economical Plan: Plan B
Total Cost: Rs. 299.0
Within budget and validity requirements.

Result: The program compares mobile plans, calculates excess charges, validates budget and validity constraints, and selects the most economical eligible plan.
