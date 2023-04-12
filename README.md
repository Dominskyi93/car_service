# CAR SERVICE
This is a web application for a car service that provides information to users about all available cars and drivers. The project uses tools such as servlets, filters, JSP, JSTL, registration, authentication and password encryption. The project follows the Model-View-Controller (MVC) design pattern, with separate packages for controllers, models, and views.

# Features:
* User registration
* User authentication
* Ability to view all registered drivers
* Ability to view all cars
* Ability to view all car manufacturers
* Possibility to add and delete a new car manufacturer
* Possibility to add and delete a new car
* Ability to assign a driver to a specific car
* Ability to view all cars assigned to a specific driver

# How to run
To run the project locally, follow these steps:

* Clone the project
* Launch the `init_db.sql` script in MySQL to create the necessary database tables
* Enter your MySQL username and password in the `ConnectionUtil` class
* Build the project using Maven: `mvn package`
* Deploy the WAR file to a servlet container such as Tomcat

# Structure
* Controllers:
  * Car controllers:
    * `AddCarController` (POST `/cars/add`) to adding `Car` model to DB
    * `AddDriverToCarController` (POST `/cars/drivers/add`) to adding `Driver` model to existed `Car` model in DB
    * `DeleteCarController` (GET `/cars/delete`) to deleting `Car` model in DB
    * `GetAllCarsController` (GET `/cars`) to getting all `Car` models from DB
    * `GetMyCurrentCarsController` (GET `/cars/my`) to getting all my current cars from DB
  * Driver controllers:
    * `AddDriverController` (POST `/drivers/add`) to adding `Driver` model to DB
    * `DeleteDriverController` (GET `/drivers/delete`) to deleting `Driver` model in DB
    * `GetAllDriversController` (GET `/drivers`) to getting all `Driver` models from DB
  * Manufacturer controllers:
    * `AddManufacturerController` (POST `/manufacturers/add`) to adding `Manufacturer` model to DB
    * `DeleteManufacturerController` (GET `/manufacturers/delete`) to deleting `Manufacturer` model in DB
    * `GetAllManufacturersController` (GET `/manufacturers`) to getting all `Manufacturer` models from DB
  * `IndexController` (GET `/index`) get to the home page
  
* Exception:
  * `AuthenticationException` class - an exception indicating problems with authentication
  * `DataProcessingException` class is wrapping SQL exceptions to rethrow them as a runtime ones
  
* DAO:
  * `CarDaoImpl` handler of `Car` model to DB
  * `DriverDaoImpl` handler of `Driver` model to DB
  * `ManufacturerDaoImpl` handler of `Manufacturer` model to DB
  
* Model:
  * `Car` model class
  * `Driver` model class
  * `Manufacturer` model class
  
* Service:
  * `AuthenticationServiceImpl` class
  * `CarServiceImpl`
  * `DriverServiceImpl`
  * `ManufacturerServiceImpl`
  
* Util:
  * `ConnectionUtil` class for instance connection to DB
  
* Web.filter:
  * `AuthenticationFilter` class to handle Authentication process

# Security
The project has a built-in security mechanism that ensures the protection of user confidential
information and ride data. To use the service, you need to register and authorize.

* Registration
To register for the service, you need to make a POST request to the following endpoint: POST `/registration`
Where registration is the endpoint that handles registration requests. The request body should contain the following fields:

  * `login`: user's login address
  * `password`: password for logging into the system
  * `name`: user's name
In response to the request, you will receive a token that you will need to use for authorization.

* Authorization
To authorize, make a POST request to the following endpoint: POST `/login`
Where login is the endpoint that handles authorization requests. The request body should contain the following fields:

  * `login`: user's login address
  * `password`: password for logging into the system
In response to the request, you will receive a token that you will need to use to access protected resources.
Also we can perform a logout (GET `/logout`).

# Used technologies:
* JDK 1.8 version
* Maven 3.8.0 version
* JDBC 4.2 version
* MySql 8.0.32 version
* Java Servlets 4.0.1 version
* Apache Tomcat 10.1.17 version

# Author

Denys Dominskyi

