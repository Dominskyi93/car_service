# car_service
This is a web application for a taxi service that provides information to users about all available cars and drivers.

Deployment
This project has been deployed on Heroku. You can find it here: https://service-taxi-java.herokuapp.com/

Features:

User registration and login
* Ability to view all registered drivers
* Ability to view all cars
Ability to view all car manufacturers
Possibility to add and delete a new car manufacturer
Possibility to add and delete a new car
Ability to assign a driver to a specific car
Ability to view all cars assigned to a specific driver

HOW TO RUN

To run the project locally, follow these steps:

Clone the project
Launch the init_db.sql script in MySQL to create the necessary database tables
Enter your MySQL username and password in the ConnectionUtil class
Build the project using Maven: mvn package
Deploy the WAR file to a servlet container such as Tomcat

Structure
The project uses tools such as servlets, filters, JSP, JSTL, and password encryption. The project follows the Model-View-Controller (MVC) design pattern, with separate packages for controllers, models, and views.

Author

Denys Dominskyi


