# Information Gathering

## 1. Project Overview

The Student Attendance Management System is intended to digitally manage and monitor student attendance in an academic environment such as NIT Hamirpur. The system supports role-based access for different authorities to ensure secure, accurate, and efficient attendance recording, management, and reporting.

The system is designed with three primary authorities: Admin, Faculty, and Student. Each authority has clearly defined responsibilities and permissions, which directly influence the database design and relationships.

---

## 2. Stakeholders and Authorities

### 2.1 Admin Authority

The Admin acts as the central controller of the system and is responsible for maintaining institutional data.

**Responsibilities:**

* Enroll and manage faculty records
* Assign faculty to courses and sections
* Add and enroll students into courses and sections
* Monitor system activities
* Broadcast messages to faculty and students (optional)
* View and manage tickets raised by faculty or students (optional)

---

### 2.2 Faculty Authority

Faculty members are responsible for marking and managing attendance for the courses they teach.

**Responsibilities:**

* View the batch years assigned to them
* Access courses taught in a selected batch
* View section details for each course
* Create and manage lecture sessions
* Mark attendance for each lecture
* Finish a lecture to finalize attendance
* Automatically generate attendance percentage for students in a section
* Broadcast messages or raise tickets to admin (optional)

---

### 2.3 Student Authority

Students have read-only access to their attendance data and limited communication features.

**Responsibilities:**

* View attendance details for enrolled courses
* Track attendance percentage
* Raise tickets or queries to faculty regarding attendance

---

## 3. Functional Requirements

* The system shall support role-based login for Admin, Faculty, and Student.
* Attendance shall be recorded on a per-lecture basis.
* A lecture must be explicitly created and finished by faculty.
* Attendance once finalized cannot be modified without authorization.
* A student can be enrolled in multiple courses.
* A course can have multiple students and multiple lecture records.
* Attendance percentage shall be calculated automatically.

---

## 4. Data Requirements and Assumptions

* Each student is uniquely identified by a student ID or roll number.
* Each faculty member is uniquely identified by a faculty ID.
* Courses are uniquely identified by course code.
* Attendance is recorded per student, per lecture, per course.
* One student cannot have more than one attendance record for the same lecture.
* Faculty can mark attendance only for courses assigned to them.

---

## 5. Identified Database Entities

Based on the information gathered, the following core entities are identified:

1. Student
2. Faculty
3. Admin
4. Course
5. Section
6. Attendance
7. Lecture (recommended for proper normalization)
8. Ticket (optional)
9. BroadcastMessage (optional)

---

## 6. Entity Relationship Overview

* A Student enrolls in one or more Courses.
* A Course is taught by one or more Faculty members.
* A Course is associated with one or more Sections.
* A Faculty conducts multiple Lectures for a Course.
* Attendance records associate Students with Lectures.
* Students and Faculty can raise Tickets to Admin.

---

## 7. Design Considerations

* The system follows normalization principles to reduce redundancy.
* Attendance is separated from lecture details to ensure data integrity.
* Optional features such as tickets and broadcast messages are modular and can be excluded if required.
* The design supports scalability for multiple batches, courses, and sections.

---

## 8. Scope Limitations

* The system focuses only on attendance management.
* Examination, grading, and evaluation modules are outside the scope.
* Authentication mechanisms are assumed but not implemented at the database level.

---

## 9. Conclusion

This information-gathering phase establishes a clear understanding of the system’s scope, stakeholders, functional requirements, and data needs. The gathered information serves as a foundation for ER diagram design, normalization, and database schema implementation.
