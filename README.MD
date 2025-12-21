Paycheck Calculator & Student Directory Web Application

A full-stack web application built with PHP, MySQL, and Bootstrap, featuring a Paycheck Calculator, Guestbook, and Student Directory. Designed to be responsive, secure, and easy to use.

🚀 Features
1. Paycheck Calculator

Enter hours worked and hourly rate.

Calculates:

Gross Pay

Tax (15%)

Net Pay

Responsive layout using Bootstrap cards.

Displays results on a dedicated page.

2. Guestbook

Visitors can submit name and message.

Messages stored in MySQL database (guestbook_app → guestbook_entries).

Messages displayed in reverse chronological order.

Secure form submission with prepared statements.

3. Student Directory

Add students with first and last names.

View all students in a table.

Uses prepared statements to prevent SQL injection.

4. About Page

Introduces developer Mileiny Nolasco.

Highlights technical skills and links to portfolio & GitHub.

🗂 Project Structure
/project-root
│── index.php                 # Home page
│── guestbook.php             # Guestbook form & display
│── add_student.php           # Add new student
│── students.php              # View all students
│── nav.php                   # Navbar included in pages
│── config.php                # Database connection
│── paycheckCalculator.php    # Input form for paycheck calculation
│── paycheckResult.php        # Displays paycheck results
└── about.php                 # About the developer page

💻 Technologies Used

PHP 8+

MySQL / MariaDB

HTML5 & CSS3

Bootstrap 5

JavaScript (for Bootstrap components)

⚙ Installation & Setup

Clone the repository:

git clone : https://github.com/mileiny1/Paycheck-Calculator-Student-Directory-Web-Application.git


Create a MySQL database named guestbook_app.

Create the guestbook_entries table:

CREATE TABLE guestbook_entries (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    message TEXT,
    submitted_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);


Create the students table:

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    lastname VARCHAR(100) NOT NULL
);


Update config.php with your database credentials.

Deploy on a PHP-enabled server (e.g., XAMPP, MAMP, InfinityFree).

Access pages:

paycheckCalculator.php → Paycheck Calculator

guestbook.php → Guestbook

add_student.php → Add Student

students.php → View Students
