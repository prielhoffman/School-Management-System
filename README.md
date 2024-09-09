# School Management System

## Introduction

In this exercise, we practice object-oriented programming in C++. This project involves implementing a school management system using principles of polymorphism and inheritance. You must understand the hierarchy of inheritance and implement it correctly.

**Important Notes:**
- The exercise must be submitted in pairs.
- Submit all required files (`.cpp`, `.h`) as per the task guidelines.
- Ensure correct indentation and comments in your code.
- Provide informative comments on significant or complex code sections.
- Input validation should be performed where necessary.
- Use vectors instead of arrays where specified.

## Task Description

Implement a school management system with the following classes:

### 1. Person

**Description:** Represents a person who works or studies at the school.

**Data:**
- First name
- Surname

**Methods:**
- Constructors and destructors
- Getter/Setters
- `printDetails()`: Prints the person's details.
- `isOutstanding()`: Returns a boolean indicating if the person is outstanding.

### 2. Pupil

**Description:** Represents a student in the school.

**Data:**
- Grades in all subjects
- Grade level (a single letter 'f'-'a')
- Class number (1-3)

**Methods:**
- Constructors and destructors
- Getter/Setters
- `averageGrade()`: Returns the average of grades.
- `isOutstanding()`: Returns true if GPA > 85 and no grade is below 65.
- `printDetails()`: Prints all details including grades and average.

### 3. Worker

**Description:** Represents an employee who receives payment.

**Data:**
- Years of seniority
- Static variable `basis` (initialized to 25)

**Methods:**
- Constructors and destructors
- Getter/Setters
- `monthlySalary()`: Returns the employee's monthly salary.
- `printDetails()`: Prints the employee's details including years of seniority.

### 4. Teacher

**Description:** Represents a teacher who works at the school.

**Data:**
- Array of subject names
- Number of subjects taught

**Methods:**
- Constructors and destructors
- Getter/Setters
- `monthlySalary()`: Returns the teacher's monthly salary calculated using the formula provided.
- `isOutstanding()`: Returns true if the teacher teaches 5 or more subjects.
- `printSubjects()`: Prints all subjects taught by the teacher.
- `printDetails()`: Prints all details including subjects and salary.

### 5. Tutor

**Description:** Represents an educator who is a teacher and educates a class.

**Data:**
- Pointer to the class being educated

**Methods:**
- Constructors and destructors
- Getter/Setters
- `monthlySalary()`: Returns the educator's monthly salary (NIS 1000 more than a teacher with the same subjects and seniority).
- `isOutstanding()`: Returns true if at least 50% of students are outstanding.
- `printDetails()`: Prints all details including class and subjects.

### 6. PersonalAdministration

**Description:** Represents an administrative staff member at the school.

**Data:**
- Office location (string)

**Methods:**
- Constructors and destructors
- Getter/Setters
- `monthlySalary()`: Returns the staff member's salary (calculated differently from a teacher).
- `isOutstanding()`: Returns true if the staff member is outstanding.
- `printDetails()`: Prints the administrative staff member's details.

### 7. Manager

**Description:** Represents the principal of the school. A manager is also a teacher if they teach subjects.

**Data:**
- Private static pointer of type Manager

**Methods:**
- Constructors and destructors (private)
- `getInstance()`: Returns the singleton Manager object.
- `monthlySalary()`: Returns the manager's monthly salary, considering teaching and administrative seniority.
- `isOutstanding()`: Returns true if managerial seniority is greater than three years.
- `printDetails()`: Prints the manager's details, salary, and managerial seniority.

### 8. Secretary

**Description:** Represents a member of the secretarial staff.

**Data:**
- Number of children attending the school

**Methods:**
- Constructors and destructors
- Getter/Setters
- `monthlySalary()`: Returns the secretary's monthly salary based on the number of children.
- `isOutstanding()`: Returns true if seniority is greater than ten years.
- `printDetails()`: Prints the secretary's details.

### 9. Class

**Description:** Represents a class in the school.

**Data:**
- Grade level (a single letter 'f'-'a')
- Class number (1-3)
- Array of student pointers
- Number of students
- Pointer to the class educator

**Methods:**
- Constructors and destructors
- `addStudent(Student* student)`: Adds a student to the class.
- `getStudent(int index)`: Returns the student at the specified index.

### 10. Layer

**Description:** Represents a layer in the school.

**Data:**
- Grade level (a single letter 'f'-'a')
- Array of class pointers (up to 3)

**Methods:**
- Constructors and destructors
- `getClass(int index)`: Returns the class at the specified index.

### 11. School

**Description:** Represents the school. Only one instance should be created.

**Data:**
- Array of layer pointers (up to 6)
- Number of layers
- Vector of student pointers
- Vector of employee pointers
- Private static field of type School

**Methods:**
- Constructors and destructors (private)
- `getInstance()`: Returns the singleton School object.
- `menu()`: Displays the menu for managing the school.

### 12. Template Class `<T> VecAnalyser`

**Description:** A template class that analyzes vectors of pointers to employees or students.

**Methods:**
- `getElement(int index)`: Returns the element at the specified index.
- `swap(int index1, int index2)`: Swaps elements at the given indexes.
- `printElement(int index)`: Prints the element at the specified index.
- `printAll()`: Prints all elements in the vector.
- `printMax()`: Prints the element with the highest value (average for students, salary for employees).
- `isManager(int index)`: Checks if the element at the given index is a Manager.

## Menu Description

1. **Add Pupil**: Add a student with all details, including grades and class.
2. **Add Teacher**: Add a teacher with details and subjects.
3. **Add Tutor**: Add a tutor with details and class information.
4. **Add Manager**: Add a manager (only one allowed).
5. **Add Secretary**: Add a secretary with details and number of children.
6. **Print Details**: Print details of all people in the school.
7. **Print Outstanding People**: Print details of outstanding individuals.
8. **Print Class Details**: Print details of a class based on the tutor.
9. **Print Highest Salary Worker**: Print details of the worker with the highest salary.
10. **Exit**: Exit the system and release all allocated memory.

