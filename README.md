# Student-Course-Management-System
Project Description
This SQL project implements a Student Course Management System for an EdTech company, built using PostgreSQL and designed to run in DBeaver. It includes a complete database schema, sample data, complex queries, advanced SQL features, and proper documentation.
Instructions to Run
1.	Install PostgreSQL: Ensure PostgreSQL is installed (version 14 or later recommended).
2.	Set up DBeaver: Install DBeaver and connect to your PostgreSQL server.
3.	Create Database:
o	Open DBeaver and create a new database named course_management.
o	Open a new SQL editor in DBeaver connected to course_management.
4.	Execute SQL:
o	Copy the contents of the SQL file (Student_Course_Management_System.sql).
o	Paste and execute the entire script in the DBeaver SQL editor.
o	Run the script sequentially to create tables, insert data, and execute queries.
5.	Verify Results:
o	Check the tables (Students, Instructors, Courses, Enrollments) for data.
o	Run individual queries to see results.
o	Verify the student_course_summary view and enrollment_log table.
Schema Explanation
The database consists of four main tables:
•	Students: Stores student information (ID, name, email, DOB).
•	Instructors: Stores instructor details (ID, name, email).
•	Courses: Contains course details (ID, name, description, instructor).
•	Enrollments: Tracks student course registrations (ID, student, course, date, grade).
•	Foreign keys ensure referential integrity, and constraints (e.g., UNIQUE email, CHECK for grades) maintain data quality.
Key Queries
1.	Students in at least one course: Uses JOIN and DISTINCT to list enrolled students.
2.	Students in >2 courses: Groups enrollments by student with HAVING clause.
3.	Courses with enrollment counts: LEFT JOIN to include all courses, even those with zero enrollments.
4.	Average grade per course: Converts grades to numeric values (A=4, F=0) for averaging.
5.	Non-enrolled students: LEFT JOIN with NULL check to find students without enrollments.
6.	Student average grades: Calculates GPA-like average across courses per student.
7.	Instructor course counts: Counts courses per instructor, including those with zero courses.
8.	Students under John Smith: Joins tables to find students in courses taught by John Smith.
9.	Top 3 students by grade: Orders students by average grade, limited to three.
10.	Students failing multiple courses: Identifies students with multiple 'F' grades.
Advanced Features
•	View: student_course_summary combines student names, course names, and grades.
•	Index: Improves query performance on Enrollments.student_id.
•	Trigger: Logs new enrollments into enrollment_log table with timestamps.
Sample Output
•	Query 1: Lists all students with at least one enrollment (e.g., Emma Wilson, Liam Johnson).
•	Query 4: Shows average grades (e.g., Database Systems: 2.67).
•	Query 9: Top students (e.g., Emma Wilson with avg_grade 3.5).
•	View: SELECT * FROM student_course_summary shows formatted student-course-grade data.
Challenges and Lessons Learned
•	Challenge: Ensuring grade conversion (A=4, F=0) was consistent across queries.
o	Solution: Used CASE statements for reliable grade mapping.
•	Challenge: Handling students with no enrollments in queries.
o	Solution: Used LEFT JOINs to include all students/courses.
•	Lesson: Indexes significantly improve query performance for large datasets.
•	Lesson: Triggers are powerful for auditing but require careful function design.


