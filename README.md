# Tuition Management System

## Project Overview

This project is a simple SQL-based Tuition Management System. It is designed to manage students, courses, batches, and enrollments, allowing for easy tracking of tuition activities. The system includes features such as batch management, student enrollment, and fee calculations.

## Features

- **Manage Students**: Store and retrieve information about students including their names, contact details, and more.
- **Manage Courses**: Store and manage course details like course name, description, duration, and fee.
- **Manage Batches**: Organize students into different batches for more streamlined management.
- **Enroll Students**: Enroll students into courses within specific batches.
- **Track Fees**: Calculate total fees collected from different batches.

## Database Schema

The system consists of four main tables:

1. **Students**
   - `StudentID`: Primary key, auto-incremented.
   - `FirstName`: First name of the student.
   - `LastName`: Last name of the student.
   - `DateOfBirth`: Date of birth.
   - `Gender`: Gender of the student.
   - `PhoneNumber`: Contact number.
   - `Email`: Email address.

2. **Courses**
   - `CourseID`: Primary key, auto-incremented.
   - `CourseName`: Name of the course.
   - `Description`: Brief description of the course.
   - `DurationInWeeks`: Duration of the course in weeks.
   - `Fee`: Course fee.

3. **Batches**
   - `BatchID`: Primary key, auto-incremented.
   - `BatchName`: Name of the batch.
   - `StartDate`: Start date of the batch.
   - `EndDate`: End date of the batch.

4. **Enrollment**
   - `EnrollmentID`: Primary key, auto-incremented.
   - `StudentID`: Foreign key referencing `Students`.
   - `CourseID`: Foreign key referencing `Courses`.
   - `BatchID`: Foreign key referencing `Batches`.
   - `EnrollmentDate`: Date when the student enrolled.

## SQL Scripts

### 1. Create the Database

```sql
CREATE DATABASE TuitionManagement;
USE TuitionManagement;
sql```

### 2. Create Tables
Student Table
CREATE TABLE Students (
    StudentID INT PRIMARY KEY AUTO_INCREMENT,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    DateOfBirth DATE,
    Gender VARCHAR(10),
    PhoneNumber VARCHAR(15),
    Email VARCHAR(100)
);

Courses Table
CREATE TABLE Courses (
    CourseID INT PRIMARY KEY AUTO_INCREMENT,
    CourseName VARCHAR(100),
    Description TEXT,
    DurationInWeeks INT,
    Fee DECIMAL(10, 2)
);

Batches Table
CREATE TABLE Batches (
    BatchID INT PRIMARY KEY AUTO_INCREMENT,
    BatchName VARCHAR(50),
    StartDate DATE,
    EndDate DATE
);

Enrollment Table
CREATE TABLE Enrollment (
    EnrollmentID INT PRIMARY KEY AUTO_INCREMENT,
    StudentID INT,
    CourseID INT,
    BatchID INT,
    EnrollmentDate DATE,
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID),
    FOREIGN KEY (BatchID) REFERENCES Batches(BatchID)
);

### 3. Insert Data

Insert Students
INSERT INTO Courses (CourseName, Description, DurationInWeeks, Fee)
VALUES 
('Mathematics', 'Basic Math Course', 12, 300.00),
('Physics', 'Introductory Physics Course', 10, 350.00);

Insert Batches
INSERT INTO Batches (BatchName, StartDate, EndDate)
VALUES 
('Batch A', '2024-08-01', '2024-10-31'),
('Batch B', '2024-09-01', '2024-11-30');

Insert Enrollment Records
INSERT INTO Enrollment (StudentID, CourseID, EnrollmentDate, BatchID)
VALUES 
(1, 1, '2024-08-01', 1),  -- John Doe in Batch A
(2, 2, '2024-09-01', 2);  -- Jane Smith in Batch B


### 4. Queries



