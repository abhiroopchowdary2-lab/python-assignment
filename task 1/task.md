# python-assignment
python
# Hospital Billing and Patient Classification

# Input patient details
name = input("Enter patient name: ")
age = int(input("Enter patient age: "))

# Input hospital charges
consultation = float(input("Enter consultation charges: "))
diagnostic = float(input("Enter diagnostic charges: "))
treatment = float(input("Enter treatment charges: "))

# Validate billing constraints
if age <= 0 or consultation < 0 or diagnostic < 0 or treatment < 0:
    print("Invalid input! Enter valid age and charges.")
else:
    # Calculate total bill
    total = consultation + diagnostic + treatment

    # Apply concession
    if age >= 60:
        discount = total * 0.10
    elif total >= 10000:
        discount = total * 0.05
    else:
        discount = 0

    # Calculate final bill
    final_bill = total - discount

    # Classify patient
    if final_bill >= 20000:
        category = "Premium Patient"
    elif final_bill >= 10000:
        category = "Regular Patient"
    else:
        category = "Basic Patient"

    # Display bill details
    print("\n--- Hospital Bill ---")
    print("Patient Name:", name)
    print("Patient Age:", age)
    print("Consultation Charges: Rs.", consultation)
    print("Diagnostic Charges: Rs.", diagnostic)
    print("Treatment Charges: Rs.", treatment)
    print("Total Bill: Rs.", total)
    print("Concession: Rs.", discount)
    print("Final Bill: Rs.", final_bill)
    print("Patient Classification:", category)
    
   1. Problem Statement
To write a Python program for Hospital Billing and Patient Classification that calculates consultation, diagnostic, and treatment charges. The program applies conditional concessions based on patient age and total bill amount, validates the age and charges, calculates the final bill, and classifies the patient as Basic, Regular, or Premium according to the billing policy.

2. Algorithm
1. Start the program.
2. Read the patient's name and age.
3. Read consultation, diagnostic, and treatment charges.
4. Check whether the age is valid and all charges are non-negative.
5. If the inputs are invalid, display an error message.
6. Otherwise, calculate the total bill by adding all three charges.
7. Apply a 10% concession if the patient is aged 60 or above.
8. Otherwise, apply a 5% concession if the total bill is ₹10,000 or more.
9. If neither condition is satisfied, apply no concession.
10. Calculate the final bill by subtracting the concession from the total bill.
11. Classify the patient:
    - Final bill ₹20,000 or more: Premium Patient.
    - Final bill ₹10,000 or more but below ₹20,000: Regular Patient.
    - Final bill below ₹10,000: Basic Patient.
12. Display the billing details, concession, final bill, and patient classification.
13. Stop the program.

3.Mermaid Flowchart    
flowchart TD
    A([Start]) --> B[/Input name, age and charges/]
    B --> C{Age > 0 and charges >= 0?}
    C -- No --> D[/Display Invalid Input/]
    D --> Z([Stop])
    C -- Yes --> E[Calculate Total Bill]
    E --> F{Age >= 60?}
    F -- Yes --> G[Apply 10% Concession]
    F -- No --> H{Total Bill >= 10000?}
    H -- Yes --> I[Apply 5% Concession]
    H -- No --> J[No Concession]
    G --> K[Calculate Final Bill]
    I --> K
    J --> K
    K --> L{Final Bill >= 20000?}
    L -- Yes --> M[Premium Patient]
    L -- No --> N{Final Bill >= 10000?}
    N -- Yes --> O[Regular Patient]
    N -- No --> P[Basic Patient]
    M --> Q[/Display Bill and Classification/]
    O --> Q
    P --> Q
    Q --> Z

4. Input
Example input values:
Enter patient name: Ch.Samyuktha
Enter patient age: 38
Enter consultation charges: 5000
Enter diagnostic charges: 5000
Enter treatment charges: 10000

Input values:
Variable	Value
Patient name	Ravi
Patient age	65
Consultation charges	₹5,000
Diagnostic charges	₹5,000
Treatment charges	₹10,000

5. Expected Output
   --- Hospital Bill ---
Patient Name: Ravi
Patient Age: 65
Consultation Charges: Rs. 5000.0
Diagnostic Charges: Rs. 5000.0
Treatment Charges: Rs. 10000.0
Total Bill: Rs. 12000.0
Concession: Rs. 1200.0
Final Bill: Rs. 10800.0
Patient Classification: Regular Patient

Result: The program calculates the total hospital bill, applies the applicable concession, validates the inputs, and classifies the patient according to the specified billing policy.

