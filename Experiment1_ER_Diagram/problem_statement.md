# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
![image](https://github.com/user-attachments/assets/b043e08a-bef4-4e3f-9fff-f6d2df360d55)


## Entities and Attributes:
### Student
stuID, stuName, DOB, stuPhone, stuEmail, stuAddress
### Courses
courseName, credits, units, courseType
### Enrollment
enrollDate, courseID, Prerequisite
### Staffs
staffID, staffName, staffAddress, staffPhone, staffEmail
### University
(no attributes)
### Programs
programID, programName, Department

## Relationships and Constraints
- Student can Enrollment (can): One student can enroll in many courses.
- Enrollment for Courses (for): Each enrollment is for one course.
- University has Student (has): One university can have many students.
- University offers Programs (offers): One university can offer many programs.
- University employee Staffs (employee): One university employs many staff members.
- Programs belong to University: Each program is offered by a university (implied from "offers").

## Extension (Prerequisite / Billing):
- Courses Prerequisite Courses: A course can have zero or more prerequisite courses (recursive relationship).
- Student Billing (bills): A student can have one or more billing records; each billing record is linked to one student.


## Design Choices:
Brief explanation of why you chose certain entities, relationships, and assumptions

## RESULT
A complete ER model of a university system that defines students, courses, professors, and their interrelationships, including prerequisites, with proper constraints and rationale.
