INSTAGRAM PROJECT
Java Maven Spring Boot MySQL

This project is a basic web application that allows users to sign in, sign up, and manage their profile information. Additionally, users can create posts and view posts created by other users. The application uses authentication tokens to secure user data and ensure that only authenticated users can access certain features of the application.


Framework Used
Spring Boot

Dependencies
The following dependencies are required to run the project:

Spring Boot Dev Tools
Spring Web
Spring Data JPA
MySQL Driver
Lombok
Validation
Swagger

Database Configuration
To connect to a MySQL database, update the application.properties file with the appropriate database URL, username, and password. The following properties need to be updated:

spring.datasource.driverClassName=com.mysql.cj.jdbc.Driver
spring.datasource.url = jdbc:mysql://localhost:3306/<DatabaseName>
spring.datasource.username = <userName>
spring.datasource.password = <password>
spring.jpa.show-sql = true
spring.jpa.hibernate.ddl-auto = update

spring.jpa.properties.hibernate.show_sql=true
spring.jpa.properties.hibernate.use_sql_comments=true
spring.jpa.properties.hibernate.format_sql=true


Language Used
Java

Data Model
The Job data model is defined in the Job class, which has the following attributes:

User Model
Id : integer
firstName : string
lastName : string
age : integer
email : string
password : string
phoneNumber : string
Post Model
postId = Long
createdDate : Timestamp
updatedDate : Timestamp
postData : String
@ManyToOne
user : User

Authentication Token
tokenId : Long
token : string
tokenCreationDate : LocalDate
@OneToOne 
user : User
Data Flow
The user at client side sends a request to the application through the API endpoints.
The API receives the request and sends it to the appropriate controller method.
The controller method makes a call to the method in service class.
The method in service class builds logic and retrieves or modifies data from the database, which is in turn given to controller class
The controller method returns a response to the API.
The API sends the response back to the user.

API End Points
The following endpoints are available in the API:

User Controller:
POST /user/signup: create a new user account
POST /user/signin: authenticate a user and receive an authentication token
PUT /user: update user details
DELETE /user/signout: authenticate a user and delete authentication token
Post Controller
POST /post: create a new post
GET /post: get all posts

DataBase Used
SQL database
We have used Persistent database to implement CRUD Operations.

Project Summary
The project is a basic web application built using Java and the Spring framework. It allows users to sign up, sign in, and manage their profile information. Users can also create and view posts. The application uses authentication tokens to secure user data and ensure that only authenticated users can access certain features. The API endpoints include user signup, signin, and update details, post creation and retrieval, and authentication token creation.
