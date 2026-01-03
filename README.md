# 🎓 University Course Registration System

A comprehensive Java-based simulation of a university course registration process. This project focuses on **low-level data structure management** by implementing complex object interactions without using the Java Collections Framework (no `ArrayList` or `List`).

## 📋 Project Overview
This system simulates the interaction between **Students**, **Courses**, and **Faculty** members. It handles the complete lifecycle of course registration, including quota checks, prerequisite validation, instructor assignments, and waitlist management.

The core challenge of this project was to implement **dynamic array resizing algorithms** manually, demonstrating a deep understanding of memory management and array manipulation in Java.

## ⚙️ Technical Highlights (The "Hard" Mode)
* **No ArrayLists Used:** Per project constraints, all data structures are managed using standard Java Arrays (`[]`).
* **Manual Dynamic Resizing:** Implemented custom algorithms to expand or shrink arrays when items (Students, Courses) are added or removed.
* **Object Association:** Uses wrapper classes (`RegisterInfo`, `AssignInfo`) to manage stateful relationships between entities (e.g., status of a registration request).

## 🚀 Key Features
* **Advanced Quota System:** Manages `maxEnrollment` and `reservedSeats`. If a course is full, students are automatically placed on a **Replacement List** (Waitlist).
* **Prerequisite Logic:** Enforces rules based on Student Year (e.g., a Freshman cannot take a Junior course).
* **Department Restrictions:** Implements a dynamic rule where department restrictions are enforced only after 70% of the course capacity is filled.
* **Faculty Management:** Allows assigning instructors to courses with conflict checks and "force assignment" capabilities.

## 📂 Class Structure
* **`Student`:** Manages personal info and a dynamic list of registered courses (`RegisterInfo[]`).
* **`Course`:** Handles credits, quotas, prerequisites, and the registered student list.
* **`Faculty`:** Represents instructors and tracks their assigned courses (`AssignInfo[]`).
* **`RegisterInfo`:** Connects a Student to a Course, storing the registration status (APPROVED, REJECTED, WAITING).
* **`AssignInfo`:** Connects a Faculty member to a Course.

## 💻 Usage
The project includes a test class to simulate the registration scenarios:

```java

Course c1 = new Course("CSE", "Computer Programming I", 6, 1, 100, 5);
Student s1 = new Student("Arif", "Erdem", "Computer Engineering", 123, 1);


c1.registerCourse(s1);


Faculty f1 = new Faculty(1, "John", "Doe", "Computer Engineering");
c1.assignInstructor(f1, false);
