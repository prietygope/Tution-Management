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

### 2. Create Tables
`Student Table`
CREATE TABLE Students (
    StudentID INT PRIMARY KEY AUTO_INCREMENT,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    DateOfBirth DATE,
    Gender VARCHAR(10),
    PhoneNumber VARCHAR(15),
    Email VARCHAR(100)
);

