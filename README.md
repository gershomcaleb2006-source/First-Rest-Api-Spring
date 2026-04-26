# Spring Framework Application - Task 2 (REST API)
**Author:** Gershom Goldlin Ranjit
**University:** Vistula University

## Project Overview
This repository contains a fully functional backend REST API built using the Spring Framework. This project was completed as "Task 2" for university coursework to demonstrate enterprise-level architecture (Controllers, Services, Repositories, Domains) and database integration.

### Technologies & Architecture Used
* **Java & Spring Boot** (Spring Web)
* **Spring Data JPA & Hibernate** (ORM for database interaction)
* **H2 Database** (In-memory database for testing)
* **Swagger UI / OpenAPI** (Automated API documentation and testing)
* **Layered Architecture:** The codebase is strictly separated into `api` (Controllers, Requests, Responses), `service` (Business Logic), `domain` (Entities), `repository` (Database Access), and `support` (Mappers and Exception Handling).

---

## API Endpoints (CRUD Operations)
This API manages a `Product` entity. The following HTTP methods and use cases have been fully implemented and tested.

### 1. Create a Product
* **Method:** `POST`
* **Path:** `/api/v1/products`
* **Description:** Accepts a JSON body containing a product name, saves it to the database, automatically generates an ID, and returns the created object.
* **Status Code:** `201 Created`

### 2. Get a Specific Product
* **Method:** `GET`
* **Path:** `/api/v1/products/{id}`
* **Description:** Retrieves a specific product by its database ID. 
* **Status Code:** `200 OK`

### 3. Get All Products
* **Method:** `GET`
* **Path:** `/api/v1/products`
* **Description:** Retrieves a complete list of all products currently stored in the database.
* **Status Code:** `200 OK`

### 4. Update a Product
* **Method:** `PUT`
* **Path:** `/api/v1/products/{id}`
* **Description:** Accepts a JSON body and an ID parameter to update the name of an existing product in the database.
* **Status Code:** `200 OK`

### 5. Delete a Product
* **Method:** `DELETE`
* **Path:** `/api/v1/products/{id}`
* **Description:** Permanently removes a product from the database based on its ID.
* **Status Code:** `204 No Content`

---

## Global Exception Handling
The API includes a global `@ControllerAdvice` handler. If a user attempts to `GET`, `PUT`, or `DELETE` a product ID that does not exist in the database, the API intercepts the error and prevents a server crash.
* **Returns:** A clean `404 Not Found` HTTP status along with a custom JSON error message (e.g., `{"message": "Product with 99 not found"}`).

---

## Application Screenshots

**1. API Documentation & Testing (Swagger UI / Postman)**
<img width="2559" height="1599" alt="Screenshot 2026-04-26 163921" src="https://github.com/user-attachments/assets/0a249190-2d90-4e9b-adfd-cc230a13a748" />


**2. Exception Handling (404 Not Found)**
<img width="2559" height="1599" alt="Screenshot 2026-04-26 163451" src="https://github.com/user-attachments/assets/61d42814-eada-4977-be67-7472e6bab8a8" />


**3. Database Integration (H2 Console)**
<img width="2559" height="1599" alt="Screenshot 2026-04-26 163810" src="https://github.com/user-attachments/assets/ee0a0786-ec42-4aee-bea2-728ad6ba9fb1" />


---

## How to Run This Application
1. Clone the repository to your local machine.
2. Open the project in IntelliJ IDEA (or your preferred Java IDE).
3. Ensure Maven has downloaded all required dependencies (Spring Web, Spring Data JPA, H2 Database, Springdoc OpenAPI).
4. Run the `FirstRestApiSpringApplication.java` main class.
5. To test the API endpoints, navigate to **Swagger UI** in your browser: `http://localhost:8080/swagger-ui/index.html`
6. To view the live database, navigate to the **H2 Console**: `http://localhost:8080/console` (Ensure the JDBC URL is set to `jdbc:h2:mem:testdb`).
