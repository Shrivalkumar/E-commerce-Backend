# E-Commerce Backend

This is the **backend** for a simple E-Commerce application built with **Spring Boot**.  
It provides RESTful APIs to manage customers, sellers, products, carts, and orders, along with proper exception handling and database integration.  

---

## Technology Stack

- **Backend:** Java, Spring Boot  
- **Database:** MySQL  
- **API Documentation:** Swagger UI  
- **Build Tool:** Maven  

---

## Functionality

This backend supports the following features:

- **Customer Management:**  
  - Register, update, and fetch customer details  
  - Login/logout functionality  

- **Seller Management:**  
  - Add, update, and fetch seller details  

- **Product Management:**  
  - Add, update, fetch, and delete products  
  - Products are associated with sellers  

- **Cart Management:**  
  - Add/remove items from cart  
  - View cart details  

- **Order Management:**  
  - Place orders from the cart  
  - Track order status  

- **Exception Handling:**  
  - Custom exceptions for invalid requests, not found entities, and other error scenarios  

- **API Testing:**  
  - All endpoints are documented and testable via **Swagger UI**  

---

## API Documentation

After running the application, access Swagger UI to explore all endpoints:

## 2. Configure MySQL

Make sure MySQL is installed and running.

Create a database for the project:

CREATE DATABASE ecommerce_db;

Open src/main/resources/application.properties and update your database credentials:

spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce_db
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

## 3. Build the Project

Make sure Maven is installed:

mvn clean install

## 4. Run the Application

mvn spring-boot:run

- The backend will run on port 8009 by default.
- Swagger UI for API documentation and testing will be available at:

http://localhost:8009/swagger-ui.html

---

## API Endpoints

All endpoints are grouped by their respective controllers for clarity.

---

### Seller Controller

**GET**
- `/seller`
- `/sellers`
- `/seller/{sellerId}`
- `/seller/current`

**POST**
- `/addseller`

**PUT**
- `/seller`
- `/seller/update/password`
- `/seller/update/mobile`

**DELETE**
- `/seller/{sellerId}`

---

### Product Controller

**GET**
- `/products`
- `/products/{catenum}`
- `/products/status/{status}`
- `/products/seller/{id}`
- `/product/{id}`

**POST**
- `/products`

**PUT**
- `/products`
- `/products/{id}`

**DELETE**
- `/product/{id}`

---

### Order Controller

**GET**
- `/orders/{orderId}`
- `/orders`
- `/orders/by/date`
- `/customer/{orderId}`

**POST**
- `/order/place`

**PUT**
- `/orders/{orderId}`

**DELETE**
- `/orders/{orderId}`

---

### Customer Controller

**GET**
- `/customers`
- `/customer/orders`
- `/customer/current`

**PUT**
- `/customer`
- `/customer/update/password`
- `/customer/update/credentials`
- `/customer/update/card`
- `/customer/update/address`

**DELETE**
- `/customer`
- `/customer/delete/address`

---

### Login Controller

**POST**
- `/register/seller`
- `/register/customer`
- `/logout/seller`
- `/logout/customer`
- `/login/seller`
- `/login/customer`

---

### Cart Controller

**POST**
- `/cart/add`

**GET**
- `/cart`

**DELETE**
- `/cart`
- `/cart/clear`


You can test all endpoints directly from Swagger UI.


