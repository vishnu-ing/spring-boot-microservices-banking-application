# Transaction Service

## Introduction
The Transaction Service is a microservice responsible for managing bank transactions. It provides APIs for creating, retrieving, and listing transactions. This project is actively maintained by Vishnu Kumar to ensure high performance and reliability in financial data processing.

## Table of Contents
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
    - [Spring Boot](#spring-boot)
    - [Spring Data JPA](#spring-data-jpa)
    - [MySQL](#mysql)
    - [Spring Cloud](#spring-cloud)
    - [Eureka Server](#eureka-server)
    - [Feign Client](#feign-client)
    - [Lombok](#lombok)
- [API Endpoints](#api-endpoints)
    - [Create Transaction](#create-transaction)
    - [Get Transaction Details](#get-transaction-details)
    - [List Transactions](#list-transactions)
- [Error Handling](#error-handling)
- [Security](#security)
- [Configuration](#configuration)
- [Monitoring](#monitoring)
- [Logging](#logging)
- [Testing](#testing)
- [Build and Deployment](#build-and-deployment)

## Project Structure
The project structure of the Transaction Service is as follows:
```
Transaction Service
|-- src
|   |-- main
|   |   |-- java
|   |   |   `-- com
|   |   |       `-- example
|   |   |           `-- transactionservice
|   |   |               |-- controller
|   |   |               |   `-- TransactionController.java
|   |   |               |-- model
|   |   |               |   `-- Transaction.java
|   |   |               |-- repository
|   |   |               |   `-- TransactionRepository.java
|   |   |               |-- service
|   |   |               |   `-- TransactionService.java
|   |   |               `-- TransactionServiceApplication.java
|   |   `-- resources
|   |       |-- application.properties
|   |       `-- static
|   |           `-- index.html
|-- .gitignore
|-- Dockerfile
|-- mvnw
|-- mvnw.cmd
|-- pom.xml
`-- README.md
```

## Technologies Used

### Spring Boot
Spring Boot is used to create stand-alone, production-grade Spring-based applications. It simplifies the configuration and deployment process by providing a set of default configurations and a wide range of features such as embedded servers, security, and monitoring.

### Spring Data JPA
Spring Data JPA is used for data access and manipulation. It provides a repository abstraction over the JPA (Java Persistence API) and simplifies the implementation of data access layers by reducing boilerplate code.

### MySQL
MySQL is a popular open-source relational database management system. It is widely used for storing and managing data in web applications. When used with Spring Data JPA, MySQL serves as the database where the application's data is persisted. Spring Boot provides easy integration with MySQL through auto-configuration and properties settings, allowing developers to quickly set up and use MySQL in their applications.

### Spring Cloud
Spring Cloud is used for building microservices architectures. It provides tools for configuration management, service discovery, circuit breakers, intelligent routing, and more.

### Eureka Server
Eureka Server is a service registry used for service discovery. It allows microservices to register themselves at runtime and discover other registered services.

### Feign Client
Feign is a declarative web service client. It simplifies the process of making HTTP requests to other microservices by providing a simple and intuitive API.

### Lombok
Lombok is a Java library that helps to reduce boilerplate code by generating common methods like getters, setters, equals, hashCode, and toString at compile time.

## API Endpoints

### Create Transaction
- **URL:** /transactions
- **Method:** POST
- **Description:** Creates a new transaction.
- **Request Body:**
    ```json
    {
        "accountId": "string",
        "amount": "number",
        "transactionType": "string"
    }
    ```
- **Response:**
    ```json
    {
        "transactionId": "string",
        "accountId": "string",
        "amount": "number",
        "transactionType": "string",
        "transactionDate": "string"
    }
    ```

### Get Transaction Details
- **URL:** /transactions/{transactionId}
- **Method:** GET
- **Description:** Retrieves transaction details by transaction ID.
- **Response:**
    ```json
    {
        "transactionId": "string",
        "accountId": "string",
        "amount": "number",
        "transactionType": "string",
        "transactionDate": "string"
    }
    ```

### List Transactions
- **URL:** /transactions
- **Method:** GET
- **Description:** Retrieves a list of all transactions.
- **Response:**
    ```json
    [
        {
            "transactionId": "string",
            "accountId": "string",
            "amount": "number",
            "transactionType": "string",
            "transactionDate": "string"
        }
    ]
    ```

## Error Handling
The API uses standard HTTP status codes to indicate the success or failure of an API request. Common status codes include:
- 200 OK - The request was successful.
- 201 Created - The resource was successfully created.
- 204 No Content - The resource was successfully deleted.
- 400 Bad Request - The request was invalid or cannot be served.
- 404 Not Found - The requested resource was not found.
- 500 Internal Server Error - An error occurred on the server.

## Security
The Transaction Service uses Spring Security to secure the API endpoints. Authentication and authorization are handled using JWT (JSON Web Tokens).

## Configuration
The service configuration is managed using Spring Cloud Config, which allows for centralized and externalized configuration management across all microservices.

## Monitoring
Spring Boot Actuator is used for monitoring and managing the application. It provides various endpoints to check the health, metrics, and other operational information of the service.

## Logging
Logging is configured using Logback, which is the default logging framework in Spring Boot. It provides powerful and flexible logging capabilities.

## Testing
JUnit and Mockito are used for unit and integration testing. These frameworks provide a comprehensive set of tools for writing and running tests.

## Build and Deployment
The project uses Maven for build automation and dependency management. The service can be packaged as a Docker container for deployment in a containerized environment.

## About the Developer
Vishnu Kumar is a Full Stack Software Engineer with over 6 years of experience building scalable web applications and backend services. He specializes in Java, Spring Boot, and cloud-native architectures, with a focus on delivering secure and reliable software solutions.

- **LinkedIn:** https://www.linkedin.com/in/vishnu-kumar-rs/
- **Email:** vishnu.rsvk@gmail.com
- **Role:** Project Maintainer