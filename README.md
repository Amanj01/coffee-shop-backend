# Coffee Shop API

## Overview
The **Coffee Shop API** is a Spring Boot-based RESTful service for managing coffee items. It allows users to retrieve a list of coffee products and add new ones. The project follows a structured MVC architecture, integrating Spring Boot, Spring Data JPA, and MySQL for data persistence.

## Features
- Retrieve all available coffee items
- Add new coffee items
- Uses MySQL as the database
- Follows RESTful API principles
- JSON responses for easy integration

## Technologies Used
- **Java 17+**
- **Spring Boot 3+**
- **Spring Data JPA**
- **MySQL Database**
- **Hibernate ORM**
- **Jackson for JSON serialization**

## Project Structure
```
│── src/main/java/com/amanj01/coffeeshop/
│   ├── controller/        # Handles HTTP requests (API layer)
│   ├── service/           # Business logic layer
│   ├── repository/        # Data access layer
│   ├── model/             # Entity definitions
│   ├── CoffeeShopApplication.java  # Main application entry point
│── src/main/resources/
│   ├── application.properties  # Configuration file
│── pom.xml                     # Maven dependencies
```

## Setup and Installation
### Prerequisites
- Java 17+
- Maven
- MySQL Database

### Steps
1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/coffee-shop.git
   cd coffee-shop
   ```
2. Configure the database in `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/coffeeshop?useSSL=false&serverTimezone=UTC
   spring.datasource.username=root
   spring.datasource.password=your_password
   spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

   spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   ```
3. Create the MySQL database:
   ```sql
   CREATE DATABASE coffeeshop;
   ```
4. Build and run the project:
   ```sh
   mvn clean install
   mvn spring-boot:run
   ```

## API Endpoints
| Method | Endpoint  | Description |
|--------|----------|-------------|
| GET    | `/coffee` | Get all coffee items |
| POST   | `/coffee` | Add a new coffee item |

## Example JSON Response
```json
[
  {
    "id": 1,
    "name": "Latte",
    "coffeeType": "hot",
    "description": "A creamy hot coffee",
    "price": 3.99
  }
]
```

## License
This project is licensed under the MIT License. Feel free to use and modify it.

---

### Notes
- Make sure MySQL is running before starting the app.
- Use **Postman** or **cURL** to test the API endpoints.
- Replace `your_password` in `application.properties` with your actual MySQL password.

---

Happy coding! 🚀
