## Project Overview

Kisan Sarthi is a console-based application developed using Java and JDBC. It helps farmers manage their crop details efficiently by storing and retrieving data from an Oracle database.

The system allows farmers to register, log in, add crops, view available crops, and sell them while automatically updating stock and calculating total earnings.

## Technologies Used

* Java (Core Java)
* JDBC (Java Database Connectivity)
* Oracle Database
* Eclipse IDE

## Key Features

* Farmer Registration and Login
* Add Crop Details
* View Crop Records
* Sell Crops with Automatic Stock Update
* Database Integration using JDBC

## System Requirements

* Java JDK 8 or above
* Oracle Database (running with SID: `orcl`)
* Oracle JDBC Driver (ojdbc)
* Any Java IDE (Eclipse recommended)

## Project Objective

The main objective of this project is to provide a simple and efficient system for farmers to manage their crop data digitally using a database-driven approach.

---

## Project Structure

* **/src/com/kisan/**: Contains the main Java source file (`KisanSarthi.java`)
* **Oracle Database**: Stores farmer and crop data

## Prerequisites

1. Java (JDK 8 or above)
2. Eclipse IDE (or any Java IDE)
3. Oracle Database (running with SID: `orcl`)
4. Oracle JDBC Driver (ojdbc) added to project

## Database Setup

### Create User

Username: JAVA43
Password: 12345

### Create Tables

```sql
CREATE TABLE farmer (
    farmer_id NUMBER PRIMARY KEY,
    name VARCHAR2(50),
    phone VARCHAR2(15),
    location VARCHAR2(50),
    password VARCHAR2(50)
);

CREATE TABLE crop (
    crop_id NUMBER PRIMARY KEY,
    farmer_id NUMBER,
    crop_name VARCHAR2(50),
    quantity NUMBER,
    price NUMBER,
    FOREIGN KEY (farmer_id) REFERENCES farmer(farmer_id)
);
```

### Create Sequences

```sql
CREATE SEQUENCE farmer_seq START WITH 1 INCREMENT BY 1;
CREATE SEQUENCE crop_seq START WITH 1 INCREMENT BY 1;
```

## How to Run the Project

1. Open the project in Eclipse
2. Add Oracle JDBC Driver (ojdbc) to the build path
3. Ensure Oracle Database is running
4. Run the `KisanSarthi` class

The application will start in the console.

## Application Flow

1. Register as a new farmer
2. Login using phone and password
3. Access Farmer Menu:

   * Add Crop
   * View Crops
   * Sell Crop
   * Logout

## Example Functionality

### Adding a Crop

* Enter crop name, quantity, and price
* Data is stored in Oracle database

### Selling a Crop

* Select crop ID
* Enter quantity to sell
* System updates remaining stock and displays total amount

## Configuration

```java
static final String URL = "jdbc:oracle:thin:@localhost:1521:orcl";
static final String USER = "JAVA43";
static final String PASSWORD = "12345";
```

## Future Improvements

* Add Buyer Module
* GUI Interface (Swing / JavaFX / Web)
* Password Encryption
* Transaction History
* Real-time Market Price Integration

## Sahiti Machavarapu & Team

Developed as a mini project using Java, JDBC, and Oracle Database.
