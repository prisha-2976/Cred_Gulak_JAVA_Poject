# Java_Project on master branch

Subscription-Based Loan Billing System(SAP BRIM CC Inspired Model)


--Project Overview--

This project allows users to:

Create customers (borrowers)

Assign a loan subscription (Home, Car, Education Loan)

Validate eligibility based on age, salary, credit score

Generate EMI using rating logic

Create monthly billable items (EMI bills)

Generate invoices

Perform full CRUD operations using Java + JDBC + MySQL

-- Why This Project Is Relevant for SAP BRIM CI--

Although developed in Java, the project mirrors SAP BRIM concepts:

Java Feature	SAP BRIM CI Equivalent
Customer details	Business Partner + Contract Account
Loan Type	Subscription Product
EMI Calculation	Rating Logic
Monthly EMI	Billable Item
Invoice	CI Invoicing
Exception Handling	Billing Rejections
CRUD Operations	Provider Contract Lifecycle



-- Features--
 1. Customer Management

CRUD operations for:

Borrower Name

Age

Salary

Credit Score

Includes strict validations.

 2. Loan Subscription Assignment

Loan types supported:

Home Loan

Car Loan

Education Loan

Each loan acts like a subscription product.

 3. Eligibility Validation (Exception Handling)

Age must be greater than 18

Salary must be between ₹25,000 – ₹25,00,000

Credit Score must be between 400 – 900

If validation fails → system throws a custom exception
(similar to BRIM CI rejection rules).

 4. Rating Logic (EMI Calculation)

The system calculates:

Interest Rate (based on salary & credit score)

Loan Tenure

EMI using standard P x R x (1+R)^N / ((1+R)^N – 1) formula

Equivalent to SAP CC Rating Engine.

 5. Monthly Billable Item Generation

For each customer, the system creates:

EMI Amount

Due Date

Outstanding Amount

This simulates billable items in BRIM CI.

 6. Invoice Creation

After billable items are generated, the system:

Aggregates EMI

Produces a simple invoice summary

Stores it in the database

Equivalent to CI Invoicing.

 Tech Stack
Component	Technology
Programming Language	Java
Database	MySQL
Connectivity	JDBC Driver
Concepts Used	OOP, Exception Handling, CRUD, Billing Logic

 --Database Tables--

customers

Stores customer master data.

loans

Stores loan subscription details.

billing

Stores monthly EMI data.

invoice

Stores final invoice records.

--System WORKFLOW--

Customer Creation
       ↓
Eligibility Validation (Age, Salary, Credit Score)
       ↓
Loan Type Selection (Subscription Product)
       ↓
Rating Logic (EMI Calculation)
       ↓
Billable Items (Monthly EMI Records)
       ↓
Invoice Generation (Summary Bill)
       ↓
CRUD Operations via JDBC + MySQL


--How to Run--

Install Java (JDK 8+)

Install MySQL Server

Create database & tables (SQL script included)

Add MySQL JDBC Connector

Run the Java program from any IDE

--SAMPLE OUTPUT--

Customer added successfully.
Loan Type: Home Loan
Interest Rate: 8.5%
EMI: ₹12,350

Data Saved Successfully.




/Java-Project
│── src/main/java/com

│   ├── db
│    ├── DatabaseHandler.java
│    ├── Query1.sql

|   |── Exception
│    ├── InvalidAgeException.java
│    ├── InvalidCreditScoreException.java
|    ├── InvalidSalaryException.java

|    |── loantype
│     ├── borrower.java
│     ├── Carloan.java
│     ├── Educationloan.java
│     ├── Homeloan.java
│     ├── loan.java
│── README.md


