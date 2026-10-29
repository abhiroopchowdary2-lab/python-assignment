# Employee Payroll and Deduction Analysis

# Input employee details
name = input("Enter employee name: ")
basic = float(input("Enter basic salary: "))
allowances = float(input("Enter allowances: "))
overtime = float(input("Enter overtime amount: "))
incentives = float(input("Enter incentives: "))

# Validate inputs
if basic < 0 or allowances < 0 or overtime < 0 or incentives < 0:
    print("Invalid input! Salary values cannot be negative.")
else:
    # Calculate gross salary
    gross = basic + allowances + overtime + incentives

    # Apply progressive deductions
    if gross <= 20000:
        deduction = gross * 0.05
    elif gross <= 50000:
        deduction = (20000 * 0.05) + ((gross - 20000) * 0.10)
    else:
        deduction = (20000 * 0.05) + (30000 * 0.10) + ((gross - 50000) * 0.15)

    # Calculate net salary
    net_salary = gross - deduction

    # Display salary statement
    print("\n======= SALARY STATEMENT =======")
    print("Employee Name     :", name)
    print("Basic Salary      : Rs.", round(basic, 2))
    print("Allowances        : Rs.", round(allowances, 2))
    print("Overtime          : Rs.", round(overtime, 2))
    print("Incentives        : Rs.", round(incentives, 2))
    print("--------------------------------")
    print("Gross Salary      : Rs.", round(gross, 2))
    print("Total Deductions  : Rs.", round(deduction, 2))
    print("Net Salary        : Rs.", round(net_salary, 2))
    print("================================")

    Sample Output
    Enter employee name: Ravi
Enter basic salary: 25000
Enter allowances: 5000
Enter overtime amount: 2000
Enter incentives: 3000

======= SALARY STATEMENT =======
Employee Name     : Ravi
Basic Salary      : Rs. 25000.0
Allowances        : Rs. 5000.0
Overtime          : Rs. 2000.0
Incentives        : Rs. 3000.0
--------------------------------
Gross Salary      : Rs. 35000.0
Total Deductions  : Rs. 2500.0
Net Salary        : Rs. 32500.0
================================

1. Problem Statement
To write a Python program for Employee Payroll and Deduction Analysis that calculates an employee’s gross salary using basic pay, allowances, overtime, and incentives. The program validates salary inputs, applies progressive deductions based on gross salary, calculates net salary, and generates a formatted salary statement.

2. Algorithm
1. Start the program.
2. Input the employee name.
3. Input basic salary, allowances, overtime, and incentives.
4. Check whether all salary values are non-negative.
5. If any value is negative, display an invalid input message.
6. Otherwise, calculate gross salary:
Gross Salary = Basic Salary + Allowances + Overtime + Incentives
7. Apply progressive deductions:
- Up to ₹20,000: 5%.
- ₹20,001 to ₹50,000: 5% on the first ₹20,000 and 10% on the remaining amount.
- Above ₹50,000: 5% on the first ₹20,000, 10% on the next ₹30,000, and 15% on the remaining amount.
8. Calculate net salary:

Net Salary = Gross Salary − Total Deductions
9. Display the employee details, gross salary, deductions, and net salary.
10. Stop the program.

3. Mermaid Flowchart
flowchart TD
    A([Start]) --> B[/Input employee name and salary details/]
    B --> C{Any salary value negative?}
    C -- Yes --> D[/Display Invalid Input/]
    D --> Z([Stop])
    C -- No --> E[Calculate Gross Salary]
    E --> F{Gross Salary <= 20000?}
    F -- Yes --> G[Deduction = 5% of Gross]
    F -- No --> H{Gross Salary <= 50000?}
    H -- Yes --> I[Apply 5% and 10% slabs]
    H -- No --> J[Apply 5%, 10% and 15% slabs]
    G --> K[Calculate Net Salary]
    I --> K
    J --> K
    K --> L[/Display Formatted Salary Statement/]
    L --> Z

4. Input
Example input values:
Enter employee name: Ravi
Enter basic salary: 25000
Enter allowances: 5000
Enter overtime amount: 2000
Enter incentives: 3000

Input Table
Input	Value
Employee name	Ravi
Basic salary	₹25,000
Allowances	₹5,000
Overtime	₹2,000
Incentives	₹3,000

5. Expected Output
   ======= SALARY STATEMENT =======
Employee Name     : Ravi
Basic Salary      : Rs. 25000.0
Allowances        : Rs. 5000.0
Overtime          : Rs. 2000.0
Incentives        : Rs. 3000.0
--------------------------------
Gross Salary      : Rs. 35000.0
Total Deductions  : Rs. 2500.0
Net Salary        : Rs. 32500.0
================================

Result: The program calculates gross salary, applies progressive deductions, determines net salary, and displays a formatted salary statement.
