# Railway Fare and Reservation Calculator

# Distance-based fare per km
def get_fare_rate(distance):
    if distance <= 100:
        return 1.0
    elif distance <= 500:
        return 1.5
    else:
        return 2.0

# Travel class multiplier
def get_class_multiplier(travel_class):
    if travel_class == "Sleeper":
        return 1.0
    elif travel_class == "AC3":
        return 2.0
    elif travel_class == "AC2":
        return 3.0
    else:
        return 0

# Input journey details
distance = float(input("Enter journey distance (km): "))
travel_class = input("Enter class (Sleeper/AC3/AC2): ")
travel_class = travel_class.strip().upper()

# Normalize class names
if travel_class == "SLEEPER":
    travel_class = "Sleeper"
elif travel_class == "AC3":
    travel_class = "AC3"
elif travel_class == "AC2":
    travel_class = "AC2"

passengers = int(input("Enter number of passengers: "))
reservation_fee = 40
cancellation_rate = 0.25

# Validate inputs
if distance <= 0 or passengers <= 0:
    print("Invalid distance or passenger count.")
elif get_class_multiplier(travel_class) == 0:
    print("Invalid travel class.")
else:
    total_fare = 0

    for i in range(1, passengers + 1):
        print(f"\nPassenger {i}")
        age = int(input("Enter passenger age: "))

        if age <= 0:
            print("Invalid age. Skipping passenger.")
            continue

        rate = get_fare_rate(distance)
        multiplier = get_class_multiplier(travel_class)

        base_fare = distance * rate * multiplier

        # Age-based concessions
        if age < 5:
            concession = base_fare
        elif age >= 60:
            concession = base_fare * 0.40
        else:
            concession = 0

        fare_after_concession = base_fare - concession

        # Reservation fee is added after concession
        ticket_fare = fare_after_concession + reservation_fee

        # Cancellation penalty
        cancellation_penalty = ticket_fare * cancellation_rate

        print("Base Fare: Rs.", round(base_fare, 2))
        print("Age Concession: Rs.", round(concession, 2))
        print("Reservation Fee: Rs.", reservation_fee)
        print("Final Ticket Fare: Rs.", round(ticket_fare, 2))
        print("Cancellation Penalty: Rs.",
              round(cancellation_penalty, 2))

        total_fare += ticket_fare

    print("\n======= RESERVATION SUMMARY =======")
    print("Number of Passengers:", passengers)
    print("Total Reservation Fare: Rs.", round(total_fare, 2))
    print("===================================")

    Sample Output
    Enter journey distance (km): 200
Enter class (Sleeper/AC3/AC2): Sleeper
Enter number of passengers: 2

Passenger 1
Enter passenger age: 30
Base Fare: Rs. 300.0
Age Concession: Rs. 0
Reservation Fee: Rs. 40
Final Ticket Fare: Rs. 340.0
Cancellation Penalty: Rs. 85.0

Passenger 2
Enter passenger age: 65
Base Fare: Rs. 300.0
Age Concession: Rs. 120.0
Reservation Fee: Rs. 40
Final Ticket Fare: Rs. 220.0
Cancellation Penalty: Rs. 55.0

======= RESERVATION SUMMARY =======
Number of Passengers: 2
Total Reservation Fare: Rs. 560.0
===================================

1. Problem Statement
To write a Python program for a Railway Fare and Reservation Calculator that calculates ticket fares for multiple passengers based on journey distance, travel class, age-based concessions, reservation fees, and cancellation penalties. The program displays each passenger's fare details and the total reservation cost.

2. Algorithm
1. Start the program.
2. Input journey distance and travel class.
3. Input the number of passengers.
4. Validate the distance, passenger count, and travel class.
5. Determine the fare rate based on distance:
   - Up to 100 km: ₹1 per km.
   - 101–500 km: ₹1.50 per km.
   - Above 500 km: ₹2 per km.
6. Apply the travel class multiplier:
   - Sleeper: 1
   - AC3: 2
   - AC2: 3
7. For each passenger, input age and validate it.
8. Calculate the base fare using distance, fare rate, and class multiplier.
9. Apply age-based concessions:
   - Below 5 years: 100% base-fare concession.
   - Age 60 or above: 40% concession.
   - Other ages: no concession.
10. Add the reservation fee of ₹40.
11. Calculate the cancellation penalty as 25% of the ticket fare.
12. Display the fare details for each passenger.
13. Calculate and display the total reservation fare.
14. Stop the program.

    3. Mermaid Flowchart
       
flowchart TD
    A([Start]) --> B[/Input distance, class and passenger count/]
    B --> C{Inputs valid?}
    C -- No --> D[/Display error message/]
    D --> Z([Stop])
    C -- Yes --> E[Determine distance rate and class multiplier]
    E --> F[Initialize total fare and passenger counter]
    F --> G{More passengers?}
    G -- Yes --> H[/Input passenger age/]
    H --> I{Age valid?}
    I -- No --> J[Skip passenger]
    I -- Yes --> K[Calculate base fare]
    K --> L{Age below 5?}
    L -- Yes --> M[Apply 100% concession]
    L -- No --> N{Age 60 or above?}
    N -- Yes --> O[Apply 40% concession]
    N -- No --> P[No concession]
    M --> Q[Add reservation fee]
    O --> Q
    P --> Q
    Q --> R[Calculate cancellation penalty]
    R --> S[Display passenger fare details]
    S --> T[Add ticket fare to total]
    T --> U[Increase passenger counter]
    U --> G
    J --> U
    G -- No --> V[/Display total reservation fare/]
    V --> Z

4. Input
Example input values:
Enter journey distance (km): 200
Enter class (Sleeper/AC3/AC2): Sleeper
Enter number of passengers: 2

Passenger 1
Enter passenger age: 30

Passenger 2
Enter passenger age: 65

Input Table
Input	Value
Journey distance	200 km
Travel class	Sleeper
Number of passengers	2
Passenger 1 age	30 years
Passenger 2 age	65 years

5. Expected Output
   ======= RESERVATION SUMMARY =======
Number of Passengers: 2
Total Reservation Fare: Rs. 560.0
===================================

Result: The program calculates passenger fares, applies age-based concessions, adds reservation fees, calculates cancellation penalties, and displays the total reservation cost.
