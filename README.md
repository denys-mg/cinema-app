# Cinema app

## Project Description:

A simple cinema service on Spring framework that allows its users to view information about cinema halls, movies, movie sessions, and book tickets. Also, there is an administrator role that has the right to manage the application.

## Features:

 - authentication and registration
 - restricted access for User and Admin roles
 - create and search for movies, cinema halls
 - create, update, and delete movie sessions
 - find available movie sessions
 - add tickets to the shopping cart
 - get information about the shopping cart of a specific user
 - complete an order
 - get the user's orders history

## How to run:

- Clone the project repository to your local machine
- Configure your database properties in ```src/main/resources/db.properties```
- Check that you have an empty schema (with the name you specified in db.url property) in your MySQL Workbench
- Build the project using Maven: ___mvn clean package___
- Configure and deploy the generated WAR file by the server, such as Tomcat
- When the application starts, the initial data is created in the database, you have two roles (User and Administrator) and two accounts (email: admin@gmail.com, password: 1234) and (email: user@gmail.com, password: 1234), but you can register new users / create new roles. It is also possible to configure the initial data in the ```src/main/java/cinema/config/DataInitializer```

## Structure:

The project was created following SOLID principles, using Spring MVC + Spring Security.

- __Controllers__ (Presentation layer, handling http-requests)
  - ```POST: /login``` - authentication
  - ```GET: /logout``` - invalidate current session
  - ```POST: /register``` - registration
  - ```GET: /cinema-halls``` - display all cinema halls (user/admin)
  - ```POST: /cinema-halls``` - create a new cinema hall (admin)
  - ```GET: /movies``` - display all movies (user/admin)
  - ```POST: /movies``` - create a new movie (admin)
  - ```GET: /movie-sessions/available``` - display available movie sessions on a specified date (user/admin)
  - ```POST: /movie-sessions``` - create a new movie session (admin) 
  - ```PUT: /movie-sessions/{id}``` - update information about movie session (admin) 
  - ```DELETE: /movie-sessions/{id}``` - delete movie session (admin) 
  - ```GET: /orders``` - display all user orders (user) 
  - ```POST: /orders/complete``` - complete an order (user) 
  - ```PUT: /shopping-carts/movie-sessions``` - add a new ticket to the user shopping cart (user) 
  - ```GET: /shopping-carts/by-user``` - display the user shopping cart (user) 
  - ```GET: /users/by-email``` - get user by email (admin)
- __Service__ (Logic layer, handling all business logic)
- __DAO__ (Data layer, organization of work with database)

  ### Completed structure of project:
  ![Overview](/src/main/assets/uml_cinema.png)

## Used technologies:

- JDK ```17.0.6```
- Spring ```5.3.20```
- Spring Security ```5.6.10```
- Spring Web ```5.3.20```
- Apache Maven ```3.8.7```
- Hibernate ```5.6.14.Final```
- Hibernate validator ```6.1.6.Final```
- MySQL ```8.0.32```
- MySQL Connector ```8.0.22```
- Apache Tomcat ```9.0.73```
- Maven Checkstyle Plugin (config - ```checkstyle.xml```)
