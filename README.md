
#  Library Management System

A comprehensive **Library Management System** built with **Java Spring Boot** that handles operations such as managing books, students, authors, and transactions like issuing and returning books. It follows a modular and scalable backend architecture using RESTful APIs, JPA/Hibernate for ORM, and Maven for build management.

---

##  Features

-  **Book Management**: Add, update, delete, and search for books by filters such as genre or author.
-  **Student Management**: Register new students, manage their profiles and account statuses.
-  **Transaction Handling**: Issue and return books with automated transaction records.
-  **Author Management**: Add authors and associate them with books.
-  **Enum-based Filtering**: Custom enums for genres, account statuses, transaction types, and more.


---

##  Tech Stack

| Layer              | Technology                      |
|-------------------|----------------------------------|
| Language           | Java 17                          |
| Framework          | Spring Boot                     |
| ORM                | Spring Data JPA + Hibernate     |
| REST API           | Spring MVC                      |
| Build Tool         | Maven                           |
| IDE                | IntelliJ IDEA / VS Code         |
| Database           | MySQL / PostgreSQL *(optional)* |

---

##  Project Structure

```
LibraryManagementSystem-main/
│
├── src/main/java/com/example/minorproject/
│   ├── controller/               # REST Controllers for Book, Student, Transaction
│   ├── models/                   # JPA Entity Classes (Book, Student, Author, Transaction)
│   ├── repository/               # Spring Data JPA Repositories
│   ├── enums/                    # Enum types (Genre, AccountStatus, etc.)
│   ├── exceptions/               # Custom Exception Classes
│   └── MinorprojectApplication.java  # Main Spring Boot Application
│
├── pom.xml                       # Maven Dependencies
└── README.md                     # Project Documentation (this file)
```

---

##  Key Modules Explained

### 1.  Book Module
- Manages all book-related CRUD operations.
- Supports filtering by genre or author.
- Book entity includes fields like title, genre, author, student association (if issued).

### 2.  Student Module
- Handles student registration and management.
- Maintains `AccountStatus` (ACTIVE, INACTIVE).
- Associates transactions and book issues with students.

### 3.  Transaction Module
- Responsible for issuing and returning books.
- Uses `TransactionType` enum (ISSUE, RETURN).
- Records date, fine (if any), and status.

### 4.  Author Module
- Allows managing authors separately.
- Each book links to one or more authors.

---

## ⚙️ How to Run Locally

###  Prerequisites
- Java 17+
- Maven
- MySQL (or any relational DB)
- IntelliJ IDEA / VS Code

###  Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/Anjali17aj/LibraryManagementSystem.git
   cd LibraryManagementSystem
   ```

2. **Configure `application.properties`**
   Add your MySQL DB configuration:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/library_db
   spring.datasource.username=root
   spring.datasource.password=your_password
   spring.jpa.hibernate.ddl-auto=update
   ```

3. **Run using Maven**
   ```bash
   mvn spring-boot:run
   ```

4. **Access API**
   ```
   http://localhost:8080/
   ```

---

##  API Endpoints (Sample)

| HTTP Method | Endpoint                  | Description                     |
|-------------|---------------------------|---------------------------------|
| `POST`      | `/book/add`               | Add a new book                  |
| `GET`       | `/book/all`               | Get all books                   |
| `POST`      | `/student/add`            | Register a student              |
| `POST`      | `/transaction/issue`      | Issue a book                    |
| `POST`      | `/transaction/return`     | Return a book                   |

