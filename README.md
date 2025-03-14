# Spring MVC CRUD Application

A web application demonstrating CRUD operations using Spring MVC, PostgreSQL, and Thymeleaf templating engine.

## Features

- ✅ Create, Read, Update, Delete (CRUD) operations
- 🔍 Form validation with Hibernate Validator
- 📝 Clean and responsive UI with Thymeleaf templates
- 🛢️ PostgreSQL database integration
- 🔄 RESTful API endpoints

## Technologies

- **Backend**

  - Spring MVC 5.2.1
  - Spring JDBC
  - PostgreSQL Database
  - Hibernate Validator 6.1.6
  - Maven 3.8.0

- **Frontend**
  - Thymeleaf 3.0.11
  - HTML5
  - CSS3

## Project Structure

```
src/
├── main/
    ├── java/org/example/
    │   ├── config/
    │   │   └── SpringConfig.java        # Spring configuration
    │   ├── controllers/
    │   │   └── PeopleController.java    # MVC controller
    │   ├── dao/
    │   │   ├── PersonDAO.java           # Data access layer
    │   │   └── PersonMapper.java        # Row mapper
    │   └── model/
    │       └── Person.java              # Domain model
    └── webapp/
        └── WEB-INF/
            └── views/                    # Thymeleaf templates
                └── people/
                    ├── edit.html
                    ├── index.html
                    ├── new.html
                    └── show.html
```

## Database Configuration

```java
url=jdbc:postgresql://localhost:5432/first_db
username=postgres
password=12345
driver=org.postgresql.Driver
```

## API Endpoints

| Method | URL                 | Description      |
| ------ | ------------------- | ---------------- |
| GET    | `/people`           | Get all people   |
| GET    | `/people/{id}`      | Get person by ID |
| GET    | `/people/new`       | Show create form |
| POST   | `/people`           | Create person    |
| GET    | `/people/{id}/edit` | Show edit form   |
| PATCH  | `/people/{id}`      | Update person    |
| DELETE | `/people/{id}`      | Delete person    |

## Person Model

```java
public class Person {
    private int id;                    // Primary key
    private String name;               // Size: 2-20 chars
    private int age;                   // Min: 0
    private String email;              // Valid email format
}
```

## Setup Instructions

1. **Prerequisites**

   - JDK 16
   - Maven 3.8+
   - PostgreSQL 12+
   - IDE (IntelliJ IDEA recommended)

2. **Database Setup**

   ```sql
   CREATE DATABASE first_db;
   CREATE TABLE Person (
       id SERIAL PRIMARY KEY,
       name VARCHAR(20) NOT NULL,
       age INTEGER CHECK (age >= 0),
       email VARCHAR(50) NOT NULL
   );
   ```

3. **Build & Run**

   ```bash
   # Clone repository
   git clone [repository-url]

   # Navigate to project directory
   cd Spring_MVC_last

   # Build project
   mvn clean install

   # Deploy WAR file to your servlet container
   ```

## Dependencies

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-webmvc</artifactId>
        <version>5.2.1.RELEASE</version>
    </dependency>
    <dependency>
        <groupId>org.postgresql</groupId>
        <artifactId>postgresql</artifactId>
        <version>42.2.23</version>
    </dependency>
    <!-- Other dependencies in pom.xml -->
</dependencies>
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

[Add your license here]

## Author

[Your Name]

## Acknowledgments

- Spring Framework Documentation
- Thymeleaf Documentation
- PostgreSQL Documentation
