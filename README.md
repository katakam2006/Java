```markdown
# Kisan Sarthi - Java JDBC Project

This repository contains the Kisan Sarthi console-based application. It is built using Java and JDBC with an Oracle database to manage farmer and crop details.

## Project Structure

* **/src/com/kisan/**: Contains the main Java source file (`KisanSarthi.java`)
* **Oracle Database**: Stores farmer and crop data

## Prerequisites

1. **Java (JDK 8 or above)**: Make sure Java is installed  
2. **Eclipse IDE** (or any Java IDE)  
3. **Oracle Database**: Installed and running (SID: `orcl`)  
4. **Oracle JDBC Driver (ojdbc)** added to project  

## Database Setup

### Create User
```

Username: JAVA43
Password: 12345

````

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
````

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

Update database connection if needed:

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

```
```
