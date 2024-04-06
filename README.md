Got it, here's the README.md file in Markdown format:

# Library Management System API

This is the Library Management System API. Using Spring Boot for the backend framework.

## System Requirements

- Java Development Kit (JDK) 11 or later
- Maven
- PostgreSQL

## Getting Started

### Clone the Repository

First, clone this repository to your local machine using the following command:

```
git clone https://github.com/AdamSlei/backend-maids.cc.git
```

### Database Setup

The application is configured to connect to a PostgreSQL database. The necessary database connection details are already set in the application properties file to ensure a smooth run.

However, if you prefer to use your own database setup, you can create a new PostgreSQL database and update the connection details in `src/main/resources/application.properties` as follows:

```properties
spring.application.name=backend
spring.datasource.url=jdbc:postgresql://localhost:5432/your_database_name
spring.datasource.username=your_database_username
spring.datasource.password=your_database_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
spring.datasource.driver-class-name=org.postgresql.Driver
spring.profiles.active=dev
spring.datasource.hikari.maximum-pool-size=5
spring.datasource.hikari.leak-detection-threshold=2000
```

### Build and Run the Application

Navigate to the root directory of the project and build the application using Maven:

```
mvn clean install
```

After successfully building the project, you can run it using:

```
mvn spring-boot:run
```

The application will start and be accessible at `http://localhost:8080`.

## API Endpoints

The API provides endpoints for managing books, patrons, and borrowing records:

### Books

- `GET /api/books` - Retrieves a list of all books.
- `POST /api/books` - Adds a new book to the library.
- `GET /api/books/{id}` - Retrieves details of a specific book.
- `PUT /api/books/{id}` - Updates an existing book.
- `DELETE /api/books/{id}` - Removes a book from the library.

### Patrons

- `GET /api/patrons` - Retrieves a list of all patrons.
- `POST /api/patrons` - Adds a new patron to the library.
- `GET /api/patrons/{id}` - Retrieves details of a specific patron.
- `PUT /api/patrons/{id}` - Updates an existing patron.
- `DELETE /api/patrons/{id}` - Removes a patron from the library.

### Borrowing Records

- `POST /api/borrow/{bookId}/patron/{patronId}` - Allows a patron to borrow a book.
- `PUT /api/return/{bookId}/patron/{patronId}` - Records the return of a borrowed book.

## Testing

Run the following command in the root directory of the project to execute unit and integration tests:

```
mvn test
```


## Authors

- **Adam Sleiman** - [AdamSlei](https://github.com/AdamSlei)
