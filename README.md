# Car-Rental-and-Booking-System
The Car Rental and Booking System is a comprehensive web application designed to provide users with a seamless experience for browsing, booking, and managing car rentals. Built with HTML, CSS, JavaScript, and Java, this system offers a user-friendly interface alongside robust backend functionality.

🚗Key features:

1.User Registration and Authentication: Users can create accounts and log in securely, ensuring personalized access to booking and management features.

2.Car Listings and Search: A catalog of available cars allows users to browse vehicles by brand, model, price, and availability, with search and filter options.

3.Booking and Reservation Management: Users can reserve cars for specified dates, with the system managing vehicle availability and preventing double-bookings. This module also allows for booking modifications or cancellations as needed.

4.User Dashboard: Each user has a personalized dashboard displaying booking history, active rentals, and booking management options.

5.Admin Panel: Admins can manage car listings, update prices, monitor reservations, and track user activity, providing control over rental operations.

6.Database Integration: An SQL database handles storage of user information, car details, bookings, and transaction histories for reliable data management.

7.Maven for Dependency Management: Maven streamlines the build process, making the development workflow smoother by efficiently managing project dependencies.

Database Schema


1.Create Database:
CREATE DATABASE car_rental_system;
USE car_rental_system;

2.Cars Table:
CREATE TABLE cars (
    id INT AUTO_INCREMENT PRIMARY KEY,
    make VARCHAR(100) NOT NULL,
    model VARCHAR(100) NOT NULL,
    year INT NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    availability BOOLEAN DEFAULT TRUE,  -- TRUE means available, FALSE means rented
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

3.Customer table :
CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(100) NOT NULL,
    last_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    phone VARCHAR(15) NOT NULL,
    address TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);


4.Booking Table:
CREATE TABLE bookings (
    id INT AUTO_INCREMENT PRIMARY KEY,
    car_id INT NOT NULL,
    customer_id INT NOT NULL,
    start_date DATE NOT NULL,
    end_date DATE NOT NULL,
    total_price DECIMAL(10, 2) NOT NULL,
    status ENUM('booked', 'completed', 'cancelled') DEFAULT 'booked',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (car_id) REFERENCES cars(id) ON DELETE CASCADE,
    FOREIGN KEY (customer_id) REFERENCES customers(id) ON DELETE CASCADE
);

🗂️ Project Structure
---

## 🗂️ **Project Structure**

```
online-car-dealership/
    ├── src/
    │    ├── com/
    │    │    ├── cardealership/
    │    │    │    ├── Car.java
    │    │    │    ├── CarDAO.java
    │    │    │    ├── InventoryDAO.java
    │    │    │    └── DBConnection.java
    ├── lib/
    │    └── mysql-connector-java-x.x.x.jar (MySQL JDBC Driver)
    ├── assets/
    │    └── database-connection-success.png
    ├── .gitignore
    ├── README.md
    └── Main.java
├── src/
│   └── com/
│       └── cardealership/
│           ├── Car.java
│           ├── CarDAO.java
│           ├── InventoryDAO.java
│           └── DBConnection.java
├── lib/
│   └── mysql-connector-java-x.x.x.jar (MySQL JDBC Driver)
├── assets/
│   └── database-connection-success.png
├── .gitignore
├── README.md
└── Main.java
```
## 🚀 **Technologies Used**

- **Java (JDK)**: Backend logic.
- **Java (JDK)**: Backend development.
- **JDBC**: Database connectivity.
- **MySQL**: Database management.
- **MySQL**: Database storage.
- **VS Code**: Development environment.
- **MySQL JDBC Driver**: For connecting Java to MySQL.
- **MySQL JDBC Driver**: Connects Java to MySQL.



This system demonstrates skills in full-stack development, database management, and front-end design, providing a real-world example of a functional, user-centered web application. It effectively integrates essential web technologies and is scalable for future enhancements like payment gateways and automated notifications.
