# Student-Grade-Tracker
🎓 Student Grade Tracker

A simple Java + MySQL JDBC console application that allows users to enter student names and marks, stores the data in a MySQL database, and calculates basic statistics such as the average, maximum, and minimum marks.

📌 Features

Add multiple students through the console.

Enter student names and marks.

Validate marks to ensure they are between 0 and 100.

Store student records in a MySQL database.

Calculate and display:

📊 Average score

🏆 Maximum marks

📉 Minimum marks

Uses JDBC (PreparedStatement) for database interaction.

🛠️ Technologies Used

Java

MySQL

JDBC

SQL

Scanner for console input

📂 Project Structure
StudentGradeTracker/
│
├── StudentGradeTracker.java
└── README.md

⚙️ Prerequisites

Before running the project, make sure you have:

Java JDK 8 or later

MySQL Server

MySQL JDBC Driver

An IDE such as IntelliJ IDEA, Eclipse, or VS Code

🗄️ Database Setup
1. Create the database

Open MySQL and run:

CREATE DATABASE student_grades_db;

2. Select the database
USE student_grades_db;

3. Create the table
CREATE TABLE student_grades (
    id INT AUTO_INCREMENT PRIMARY KEY,
    student_name VARCHAR(100) NOT NULL,
    marks INT NOT NULL
);

🔐 Configure Database Credentials

Open StudentGradeTracker.java and update these values:

static final String JDBC_URL = "jdbc:mysql://localhost:3306/student_grades_db";
static final String JDBC_USER = "USER";
static final String JDBC_PASS = "PASSWORD";


For example:

static final String JDBC_USER = "root";
static final String JDBC_PASS = "your_mysql_password";


⚠️ Do not commit your real database password to GitHub. For a real project, use environment variables or another secure configuration method.

📦 Add MySQL JDBC Driver

You need the MySQL Connector/J JDBC driver in your project.

If you're using Maven, add:

<dependency>
    <groupId>com.mysql</groupId>
    <artifactId>mysql-connector-j</artifactId>
    <version>9.4.0</version>
</dependency>


If you're not using Maven, download the MySQL Connector/J .jar file and add it to your project's classpath.

▶️ How to Run

Start your MySQL server.

Create the database and table using the SQL commands above.

Configure your MySQL username and password.

Make sure the MySQL JDBC driver is available.

Compile and run the Java program.

Example:

javac StudentGradeTracker.java
java StudentGradeTracker

💻 Example Usage
Enter the total number of Students:
3

Enter the name of Student 1:
Rahul
Enter marks obtained by Rahul (Out of 100):
85

Enter the name of Student 2:
Priya
Enter marks obtained by Priya (Out of 100):
92

Enter the name of Student 3:
Aman
Enter marks obtained by Aman (Out of 100):
76

Student's Average Score: 84.33333333333333
Maximum Marks obtained by student: 92
Minimum Marks obtained by student: 76

🧮 How It Works

The application follows these steps:

Takes the total number of students from the user.

Creates arrays to store student names and marks.

Establishes a connection to MySQL using JDBC.

Accepts each student's name and marks.

Validates that marks are between 0 and 100.

Inserts each student's data into the student_grades table.

Calculates the total marks.

Determines the maximum and minimum marks.

Calculates the average score.

Displays the results in the console.

🗃️ Database Example

After running the program, the student_grades table may look like:

id	student_name	marks
1	Rahul	85
2	Priya	92
3	Aman	76

You can view the stored records using:

SELECT * FROM student_grades;

🔒 Validation

The program prevents invalid marks:

Enter marks obtained by Rahul (Out of 100):
120

Invalid Marks. Please enter valid marks for Rahul (out of 100):
85


Only values from 0 to 100 are accepted.

🚀 Future Improvements

Some possible improvements for future versions:

Add student ID/roll number.

Add grade calculation such as A, B, C, etc.

Add options to update and delete student records.

Display all students from the database.

Search for a student by name or ID.

Generate a student report.

Add a graphical user interface (GUI).

Use environment variables for database credentials.

Add transaction handling and better exception management.

🤝 Contributing

Contributions are welcome!

Fork the repository.

Create a new branch:

git checkout -b feature/new-feature


Make your changes.

Commit your changes:

git commit -m "Add new feature"


Push the branch:

git push origin feature/new-feature


Open a Pull Request.

📄 License

This project is open-source and available for educational purposes.

⭐ If you found this project useful, consider giving the repository a star!
