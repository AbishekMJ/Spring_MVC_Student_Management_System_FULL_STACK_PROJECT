
```markdown
# Spring MVC Student Management System

A full-stack web application for managing student records, built using **Spring MVC** for the backend, **JSP** and **Spring Boot** for configuration, and **MySQL** for the database.

## Table of Contents

- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Features](#features)
- [Controller Endpoints](#controller-endpoints)
- [Frontend Setup](#frontend-setup)
- [Backend Setup](#backend-setup)
- [Database Setup](#database-setup)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This **Student Management System** is designed to efficiently manage student information, including their personal details and academic records. The application supports the following functionalities:

- Adding, editing, and deleting student records.
- Viewing student information and academic performance.
- Assigning students to courses.
- Managing student grades.

The backend is implemented using **Spring MVC** framework, with **JSP** views for the frontend, and **Spring JDBC** or **Spring Data JPA** to interact with the **MySQL** database.

## Technologies Used

- **Backend**:
  - Spring MVC
  - Spring Boot (for simplified configuration)
  - Spring Data JPA or Spring JDBC
  - MySQL
  - Hibernate
  - JSP for views
- **Frontend**:
  - JSP (Java Server Pages)
  - Bootstrap (for UI design)
- **Database**:
  - MySQL
  
## Installation

### Backend Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/AbishekMJ/spring-mvc-student-management-system.git
   ```

2. Navigate to the backend directory:
   ```bash
   cd spring-mvc-student-management-system/backend
   ```

3. Install dependencies:
   - If you're using **Maven** for dependency management, make sure you have **JDK 11** or higher installed.
   - You can also import the project into your IDE (e.g., IntelliJ IDEA, Eclipse).

4. Set up the MySQL database:
   - Create a database named `student_management_db`.
   - Modify `application.properties` (located in `src/main/resources/application.properties`) with your database credentials:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/student_management_db
     spring.datasource.username=root
     spring.datasource.password=password
     ```

5. Build and run the Spring MVC application:
   ```bash
   ./mvnw spring-boot:run
   ```

### Frontend Setup

1. The frontend for this project uses **JSP**. If you're using an IDE like **Eclipse** or **IntelliJ IDEA**, the JSP pages should be served automatically when the backend is running.
2. There’s no need to set up a separate frontend server for this project, as JSP is handled by the Spring MVC backend.

## Features

- **Student Management**:
  - Add, Edit, and Delete student records.
  - View student details and academic records.
- **Course Management**:
  - Add, Edit, and Delete courses.
  - Assign students to courses.
- **Grade Management**:
  - Assign and manage student grades for each course.
- **Responsive UI**:
  - The app is built with **Bootstrap** for a clean, responsive UI.

## Controller Endpoints

### Student Controller Endpoints

- **GET** `/students`: Retrieve all students.
- **GET** `/students/{id}`: Retrieve details of a student by ID.
- **POST** `/students`: Add a new student.
- **PUT** `/students/{id}`: Update student information by ID.
- **DELETE** `/students/{id}`: Delete student information by ID.

### Course Controller Endpoints

- **GET** `/courses`: Retrieve all courses.
- **GET** `/courses/{id}`: Retrieve details of a specific course.
- **POST** `/courses`: Add a new course.
- **PUT** `/courses/{id}`: Update course information.
- **DELETE** `/courses/{id}`: Delete a course.

### Grade Controller Endpoints

- **GET** `/grades`: Retrieve all grades.
- **POST** `/grades`: Assign a grade to a student for a course.

## Backend Setup

1. The backend is built using **Spring MVC** to handle requests and interact with the database.
2. It also uses **Spring Data JPA** (or Spring JDBC, depending on your choice) for the database layer.

### Running the Application

To run the application:

1. Build the project using **Maven**:
   ```bash
   mvn clean install
   ```
   
2. Run the Spring Boot application:
   ```bash
   ./mvnw spring-boot:run
   ```

3. Access the application in your browser:
   - The application will be available at `http://localhost:8080`.

## Database Setup

1. Create a MySQL database:
   ```sql
   CREATE DATABASE student_management_db;
   ```

2. Create necessary tables using the provided **schema.sql** file in the **resources** folder or run these SQL queries:
   ```sql
   CREATE TABLE students (
       id INT AUTO_INCREMENT PRIMARY KEY,
       first_name VARCHAR(100),
       last_name VARCHAR(100),
       email VARCHAR(100),
       dob DATE
   );

   CREATE TABLE courses (
       id INT AUTO_INCREMENT PRIMARY KEY,
       course_name VARCHAR(100),
       description TEXT
   );

   CREATE TABLE grades (
       id INT AUTO_INCREMENT PRIMARY KEY,
       student_id INT,
       course_id INT,
       grade VARCHAR(5),
       FOREIGN KEY (student_id) REFERENCES students(id),
       FOREIGN KEY (course_id) REFERENCES courses(id)
   );
   ```

## Contributing

Feel free to fork the repository, create branches, and submit pull requests. Contributions for bug fixes, feature improvements, and documentation updates are highly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

### Key Changes:
1. **Spring MVC**: The backend is built using **Spring MVC**, which handles request mapping and view resolution via JSP.
2. **JSP Views**: The frontend part uses **JSP** (Java Server Pages) instead of React. It works with Spring MVC to display student, course, and grade data.
3. **Database Setup**: MySQL is used for storing data, and the schema is outlined.

