# Retail Billing with Multiple Discount Rules

n = int(input("Enter number of products: "))

if n <= 0:
    print("Invalid number of products.")
else:
    subtotal = 0
    total_tax = 0
    total_discount = 0

    print("\nCategories: Electronics, Clothing, Grocery")

    for i in range(1, n + 1):
        print(f"\nProduct {i}")
        name = input("Enter product name: ")
        category = input("Enter category: ").strip().lower()
        price = float(input("Enter price: Rs. "))
        quantity = int(input("Enter quantity: "))

        if price < 0 or quantity <= 0:
            print("Invalid price or quantity. Product skipped.")
            continue

        amount = price * quantity

        # Category-specific tax
        if category == "electronics":
            tax_rate = 18
        elif category == "clothing":
            tax_rate = 5
        elif category == "grocery":
            tax_rate = 0
        else:
            print("Unknown category. Product skipped.")
            continue

        # Threshold discount
        if amount >= 5000:
            discount_rate = 10
        elif amount >= 2000:
            discount_rate = 5
        else:
            discount_rate = 0

        discount = amount * discount_rate / 100

        # Maximum discount per product: Rs. 1000
        discount = min(discount, 1000)

        taxable_amount = amount - discount
        tax = taxable_amount * tax_rate / 100
        final_amount = taxable_amount + tax

        subtotal += amount
        total_discount += discount
        total_tax += tax

        # Itemized invoice
        print("\n--- Item Details ---")
        print("Product:", name)
        print("Category:", category.title())
        print("Quantity:", quantity)
        print("Price per item: Rs.", round(price, 2))
        print("Amount: Rs.", round(amount, 2))
        print("Discount: Rs.", round(discount, 2))
        print("Tax: Rs.", round(tax, 2))
        print("Final Amount: Rs.", round(final_amount, 2))

    # Final bill summary
    print("\n========== RETAIL INVOICE ==========")
    print("Subtotal: Rs.", round(subtotal, 2))
    print("Total Discount: Rs.", round(total_discount, 2))
    print("Total Tax: Rs.", round(total_tax, 2))
    print("Final Bill: Rs.",
          round(subtotal - total_discount + total_tax, 2))
    print("====================================")

    Sample Output
    Enter number of products: 2

Categories: Electronics, Clothing, Grocery

Product 1
Enter product name: Headphones
Enter category: electronics
Enter price: Rs. 3000
Enter quantity: 2

--- Item Details ---
Product: Headphones
Category: Electronics
Quantity: 2
Price per item: Rs. 3000.0
Amount: Rs. 6000.0
Discount: Rs. 600.0
Tax: Rs. 972.0
Final Amount: Rs. 6372.0

Product 2
Enter product name: Shirt
Enter category: clothing
Enter price: Rs. 1000
Enter quantity: 1

--- Item Details ---
Product: Shirt
Category: Clothing
Quantity: 1
Price per item: Rs. 1000.0
Amount: Rs. 1000.0
Discount: Rs. 0.0
Tax: Rs. 50.0
Final Amount: Rs. 1050.0

========== RETAIL INVOICE ==========
Subtotal: Rs. 7000.0
Total Discount: Rs. 600.0
Total Tax: Rs. 1022.0
Final Bill: Rs. 7422.0
====================================

1. Problem Statement
To write a Python program for Retail Billing with Multiple Discount Rules that processes multiple products by accepting product names, categories, prices, and quantities. The program calculates item amounts, applies category-specific taxes and threshold-based discounts, enforces maximum concession limits, and generates an itemized invoice showing the subtotal, total discount, total tax, and final bill.

2. Algorithm
1. Start the program.
2. Input the number of products.
3. If the number of products is invalid, display an error message.
4. Initialize subtotal, total tax, and total discount to zero.
5. For each product, input its name, category, price, and quantity.
6. Validate the price and quantity.
7. Calculate the product amount using price × quantity.
8. Apply category-specific tax rates:
   - Electronics: 18%
   - Clothing: 5%
   - Grocery: 0%
9. Apply threshold discounts:
   - Amount ₹5,000 or above: 10%
   - Amount ₹2,000 or above: 5%
   - Below ₹2,000: No discount.
10. Limit the discount to a maximum of ₹1,000 per product.
11. Calculate the taxable amount by subtracting the discount from the product amount.
12. Calculate tax and final amount for each product.
13. Update subtotal, total discount, and total tax.
14. Display the itemized invoice for each product.
15. Display the final bill summary.
16. Stop the program.

3. Mermaid Flowchart
   
flowchart TD
    A([Start]) --> B[/Input number of products/]
    B --> C{Number greater than zero?}
    C -- No --> D[/Display invalid input/]
    D --> Z([Stop])
    C -- Yes --> E[Initialize totals]
    E --> F[/Input product details/]
    F --> G{Price and quantity valid?}
    G -- No --> H[Skip product]
    G -- Yes --> I[Calculate amount = price x quantity]
    I --> J{Identify product category}
    J -- Electronics --> K[Tax rate = 18%]
    J -- Clothing --> L[Tax rate = 5%]
    J -- Grocery --> M[Tax rate = 0%]
    J -- Unknown --> H
    K --> N[Calculate threshold discount]
    L --> N
    M --> N
    N --> O[Apply maximum discount limit]
    O --> P[Calculate taxable amount and tax]
    P --> Q[Calculate final product amount]
    Q --> R[Update invoice totals]
    H --> S{More products?}
    R --> S
    S -- Yes --> F
    S -- No --> T[/Display final invoice summary/]
    T --> Z

4. Input
Example input values:
Enter number of products: 2

Product 1
Enter product name: Headphones
Enter category: electronics
Enter price: Rs. 3000
Enter quantity: 2

Product 2
Enter product name: Shirt
Enter category: clothing
Enter price: Rs. 1000
Enter quantity: 1

Input Table
Product	Category	Price	Quantity
Headphones	Electronics	₹3,000	2
Shirt	Clothing	₹1,000	1

5. Expected Output
   ========== RETAIL INVOICE ==========
Subtotal: Rs. 7000.0
Total Discount: Rs. 600.0
Total Tax: Rs. 1022.0
Final Bill: Rs. 7422.0
====================================

Result: The program processes multiple products, applies discounts and category-specific taxes, enforces the maximum concession limit, and generates an itemized retail invoice.
