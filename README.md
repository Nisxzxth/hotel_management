# Hotel Reservation System (HRS) - Java Console Application

This project is a simple console-based Hotel Reservation System (HRS) developed in Java. It allows users to manage hotel room reservations through a command-line interface. The application uses JDBC to connect to a MySQL database for storing and retrieving reservation data.

## Features

* **Reserve Room:** Add new room reservations with guest details.
* **View Reservations:** Display a list of all current reservations.
* **Get Room Number:** Retrieve a room number for a specific reservation ID and guest name.
* **Update Reservations:** Modify existing reservation details.
* **Delete Reservations:** Remove a reservation from the system.
* **Exit:** Terminate the application.

## Prerequisites

* **Java Development Kit (JDK):** Ensure you have JDK installed on your system.
* **MySQL Database:** A MySQL database server is required to store reservation data.
* **MySQL JDBC Driver:** The MySQL Connector/J driver is needed for Java to connect to the MySQL database.
* **Database Setup:** Create a database named `hotel_db` and a table named `RESERVATIONS` with the following structure:

    ```sql
    CREATE TABLE RESERVATIONS (
        R_ID INT AUTO_INCREMENT PRIMARY KEY,
        GUEST_NAME VARCHAR(255),
        GUEST_CONTACT VARCHAR(20),
        ROOM_NUMBER INT,
        R_DATE TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );
    ```

## Getting Started

1.  **Clone the repository (or copy the code):**
    * If you have the source code in a file, copy the `MainOfHMS.java` file to a suitable directory.
2.  **Set up MySQL Connection:**
    * Ensure your MySQL server is running.
    * Update the `dburl`, `user`, and `password` variables in the `MainOfHMS.java` file with your MySQL database credentials.
3.  **Add MySQL JDBC Driver:**
    * Download the MySQL Connector/J driver (JAR file) and add it to your project's classpath.
4.  **Compile the Java Code:**
    * Open a terminal or command prompt and navigate to the directory containing `MainOfHMS.java`.
    * Compile the code using the following command:
        ```bash
        javac MainOfHMS.java
        ```
5.  **Run the Application:**
    * Execute the compiled code using the following command:
        ```bash
        java MainOfHMS
        ```
6.  **Interact with the Application:**
    * Follow the on-screen menu to perform various operations.

## Code Explanation

* **Database Connection:**
    * The code establishes a connection to the MySQL database using JDBC.
    * The `Class.forName("com.mysql.cj.jdbc.Driver")` line loads the MySQL JDBC driver.
    * `DriverManager.getConnection()` creates a connection using the provided URL, username, and password.
* **Main Loop:**
    * The `main` method contains a `while` loop that displays a menu and handles user input.
    * A `switch` statement is used to execute different functions based on the user's choice.
* **Database Operations:**
    * Methods like `reserveRoom`, `viewReservations`, `getRoomNo`, `updateReservations`, and `deleteReservations` perform database operations using `Statement` and `ResultSet`.
    * SQL queries are constructed and executed to interact with the `RESERVATIONS` table.
* **Error Handling:**
    * `try-catch` blocks are used to handle `SQLException` and `ClassNotFoundException`.
* **Utility Methods:**
    * `reservationExists()` checks to see if a reservation exists.
    * `exit()` displays an exit message with a delay.

## Limitations

* This is a basic console application with limited functionality.
* It lacks a graphical user interface (GUI).
* Input validation and error handling could be improved.
* The application does not include security features.

## Future Improvements

* Implement a GUI using JavaFX or Swing.
* Add more advanced features like room availability checks and payment processing.
* Enhance input validation and error handling.
* Implement user authentication and authorization.
* Add logging functionality.
* Refactor to use prepared statements for better security.

## License

This project is open source. You are free to use and modify it as you see fit.
