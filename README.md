# E-Commerce Web Application

This project is a simple e-commerce web application built using Spring Boot, H2 database, and React.js. The backend provides a RESTful API for managing products, while the frontend allows users to interact with the API for product management.

## Table of Contents

- [Features](#features)
- [Technologies](#technologies)
- [Project Structure](#project-structure)
- [Setup](#setup)
- [API Endpoints](#api-endpoints)
- [Usage](#usage)
- [Notes](#notes)

## Features

- Add and manage products with images
- View individual products by ID
- Uses an H2 in-memory database for testing and prototyping
- Full integration between Spring Boot REST API and React frontend

## Technologies

- **Backend**: Spring Boot, Java, Spring Data JPA, H2 Database
- **Frontend**: React.js, Axios for API calls
- **Other**: Maven for dependency management, MultipartFile for image uploads



## Features

- Add and manage products with images
- View individual products by ID
- Uses an H2 in-memory database for testing and prototyping
- Full integration between Spring Boot REST API and React frontend

## Technologies

- **Backend**: Spring Boot, Java, Spring Data JPA, H2 Database
- **Frontend**: React.js, Axios for API calls
- **Other**: Maven for dependency management, MultipartFile for image uploads

## Project Structure

```plaintext
src
├── main
│   ├── java
│   │   └── com
│   │       └── shop
│   │           └── E_Com
│   │               ├── Controller
│   │               │   └── ProductController.java
│   │               ├── model
│   │               │   └── Product.java
│   │               ├── repo
│   │               │   └── ProductRepo.java
│   │               ├── service
│   │               │   └── ProductService.java
│   │               └── EComApplication.java
│   └── resources
│       ├── application.properties
│       └── schema.sql (optional)
└── frontend
    └── src
        └── components
            └── Product.js
```



## Setup
Prerequisites
Java 17+
Maven
Node.js and npm (for frontend)
Backend Setup
Clone the repository:
```
bash
Copy code
git clone https://github.com/your-repo/ecommerce-spring-react
cd ecommerce-spring-react```
Update application.properties in the src/main/resources folder:

properties
```
# H2 database configuration
spring.datasource.url=jdbc:h2:mem:ecommerce-db
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
```
Build and run the backend:

```
bash
mvn clean install
mvn spring-boot:run```
 
## Frontend Setup
Navigate to the frontend folder:

```
bash
cd frontend
```
Install dependencies:

```
bash
npm install```
Start the frontend:

```
bash
Copy code
npm start```
The frontend will run on http://localhost:3000 by default, and the backend will run on http://localhost:8080.


## API Endpoints
Product Endpoints

### Add Product

URL: /api/addProduct
Method: POST
Request Body: JSON with Product details
Response: 201 Created



#### Get All Products

URL: /api/products
Method: GET
Response: 200 OK, returns a list of all products.

#### Get Product by ID

URL: /api/product/{id}
Method: GET
Response: 200 OK if found, 404 Not Found otherwise.
#### Add Product with Image

URL: /api/product
Method: POST
Request Parts: Product JSON, imgfile as MultipartFile
Response: 201 Created with the created Product, or 500 Internal Server Error on failure.
## Usage

Run the backend Spring Boot application as described above.
Start the frontend React application.

Open the browser and navigate to http://localhost:3000 to access the frontend.
Use the available options to add, view, and manage products.
## Notes
Database: The H2 database is in-memory and will reset each time the application restarts. You can configure a persistent database for production use.
Image Uploads: The /api/product endpoint supports adding products with images via MultipartFile. This is handled in the backend by the ProductService.
