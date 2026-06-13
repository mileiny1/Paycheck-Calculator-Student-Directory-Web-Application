# Paycheck Calculator & Student Directory

A full-stack web application built with **PHP 8**, **MySQL**, and **Bootstrap 5** — featuring a paycheck calculator, guestbook, student directory, and book finder. Designed to be secure, responsive, and easy to deploy on any PHP-enabled server.

<br />

![PHP](https://img.shields.io/badge/PHP-8.0+-777BB4?style=flat-square&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-22C55E?style=flat-square)

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Security](#security)
- [Screenshots](#screenshots)
- [Developer](#developer)
- [License](#license)

---

## Features

### Paycheck Calculator
Calculates employee pay based on hours worked and hourly rate, automatically applying a 15% tax deduction.

| Output | Description |
|--------|-------------|
| Gross Pay | `hours_worked × hourly_rate` |
| Tax (15%) | `gross_pay × 0.15` |
| Net Pay | `gross_pay − tax` |

### Guestbook
Visitors can leave their name and a message. Entries are stored in MySQL and displayed in reverse-chronological order. All input is protected against SQL injection via prepared statements.

### Student Directory
Add students by first and last name and view them in a sortable table. All queries are fully parameterized.

### Book Finder
Search and discover books through a clean, integrated browsing interface.

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | PHP 8+ |
| Database | MySQL / MariaDB |
| Frontend | Bootstrap 5, HTML5, CSS3 |
| Scripting | JavaScript (Bootstrap components) |

---

## Project Structure

```
project-root/
├── index.php                  # Home page
├── paycheckCalculator.php     # Paycheck input form
├── paycheckResult.php         # Paycheck results display
├── guestbook.php              # Guestbook form & message feed
├── add_student.php            # Add a new student
├── students.php               # View all students
├── about.php                  # About the developer
├── nav.php                    # Shared navigation bar
└── config.php                 # Database connection (add to .gitignore)
```

---

## Getting Started

### Prerequisites

- PHP 8.0 or higher
- MySQL 8.0 or MariaDB
- A local server environment ([XAMPP](https://www.apachefriends.org/) or [MAMP](https://www.mamp.info/)) or any PHP-enabled remote host

### 1. Clone the Repository

```bash
git clone https://github.com/mileiny1/Paycheck-Calculator-Student-Directory-Web-Application.git
cd Paycheck-Calculator-Student-Directory-Web-Application
```

### 2. Create the Database

```sql
CREATE DATABASE guestbook_app;
USE guestbook_app;
```

### 3. Run the Schema

```sql
CREATE TABLE guestbook_entries (
  id           INT AUTO_INCREMENT PRIMARY KEY,
  name         VARCHAR(100)  NOT NULL,
  message      TEXT          NOT NULL,
  submitted_at TIMESTAMP     DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE students (
  id       INT AUTO_INCREMENT PRIMARY KEY,
  name     VARCHAR(100) NOT NULL,
  lastname VARCHAR(100) NOT NULL
);
```

### 4. Configure the Connection

Open `config.php` and update your credentials:

```php
<?php
$host     = 'localhost';
$dbname   = 'guestbook_app';
$username = 'your_username';
$password = 'your_password';

$pdo = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
```

> **Important:** Add `config.php` to `.gitignore` before pushing to a public repository.
> ```bash
> echo "config.php" >> .gitignore
> ```

### 5. Deploy

Point your local or remote server root to the project folder and open `index.php` in a browser.

---

## Usage

| Page | URL |
|------|-----|
| Home | `index.php` |
| Paycheck Calculator | `paycheckCalculator.php` |
| Paycheck Results | `paycheckResult.php` |
| Guestbook | `guestbook.php` |
| Add Student | `add_student.php` |
| Student Directory | `students.php` |
| About | `about.php` |

---

## Security

- All database queries use **prepared statements** to prevent SQL injection
- User inputs are sanitized before display to prevent XSS attacks
- Database credentials are isolated in `config.php` — never commit this file to version control

---

## Screenshots

### Home Page
![Home Page](./screenshots/screenshot-home.png)

---

## Developer

**Mileiny Nolasco**

- Portfolio: [mileiny.dev](#)
- GitHub: [@mileiny1](https://github.com/mileiny1)

---

## License

This project is open source and available under the [MIT License](LICENSE).
