# 🏢 SJAM Connect

A web-based community facility management system built with **PHP**, **MySQL**, **HTML/CSS**, and **JavaScript**. SJAM Connect allows members and administrators to manage hall bookings, equipment rentals, ambulance requests, and user feedback — all through a unified portal.

> **Application Development Project** 

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Database Setup](#database-setup)
- [Usage](#usage)
---

## About

SJAM Connect is a multi-module facility management portal designed for community centres or similar organisations. It provides a centralised platform for members to interact with facility services — from booking halls to requesting ambulance assistance — while giving administrators the tools to manage users, approve requests, and track equipment.

---

## ✨ Features

### 👤 User Management
- User registration and login
- Profile management
- Role-based access (Admin / Member)

### 🏛️ Hall Booking
- View available halls and their schedules
- Submit hall booking requests
- Admin approval and management of bookings

### 🔧 Equipment Management
- Browse available equipment inventory (Admin view)
- Equipment request and rental by users (`Equipment_user`)
- Track equipment availability and return status

### 🚑 Ambulance Service
- Submit ambulance assistance requests
- Admin management of ambulance dispatch

### 💬 Feedback
- Members can submit feedback or complaints
- Admin can view and respond to submitted feedback

### 🖼️ Media Uploads
- Support for image and file uploads (stored in `uploads/`)

---

## 🛠️ Tech Stack

| Layer      | Technology              |
|------------|-------------------------|
| Backend    | PHP (native, no framework) |
| Database   | MySQL                   |
| Frontend   | HTML5, CSS3, JavaScript |
| Styling    | Custom CSS (`css/`)     |
| Server     | Apache (XAMPP / WAMP)   |

---

## 📁 Project Structure

```
SJAM-Connect/
├── mainPage/          # Landing page and main navigation
├── User/              # User registration, login, profile management
├── Hall/              # Hall booking pages and admin management
├── Equipment/         # Admin-side equipment management
├── Equipment_user/    # User-side equipment requests and rentals
├── ambulance/         # Ambulance request and management
├── Feedback/          # Feedback submission and admin review
├── database/          # SQL dump / database schema files
├── css/               # Global stylesheets
├── script/            # JavaScript files
├── img/               # Static images and assets
├── uploads/           # User-uploaded files (runtime)
└── .vscode/           # Editor settings
```

---

## ⚙️ Prerequisites

Before setting up the project, ensure you have:

- [XAMPP](https://www.apachefriends.org/) or [WAMP](https://www.wampserver.com/) (includes Apache + PHP + MySQL)
- PHP **7.4** or higher
- MySQL **5.7** or higher
- A web browser

---

## 🔧 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Mohamedarshathsaleem/SJAM-Connect.git
```

### 2. Move to Your Server's Root Directory

**For XAMPP:**
```bash
# Windows
cp -r SJAM-Connect C:/xampp/htdocs/SJAM-Connect

# macOS
cp -r SJAM-Connect /Applications/XAMPP/htdocs/SJAM-Connect

# Linux
cp -r SJAM-Connect /opt/lampp/htdocs/SJAM-Connect
```

**For WAMP:**
```
Copy the folder to: C:/wamp64/www/SJAM-Connect
```

### 3. Start Your Local Server

Launch **XAMPP Control Panel** (or WAMP) and start:
- ✅ Apache
- ✅ MySQL

---

## 🗄️ Database Setup

### 1. Open phpMyAdmin

Navigate to `http://localhost/phpmyadmin` in your browser.

### 2. Create a New Database

```sql
CREATE DATABASE sjam_connect;
```

### 3. Import the SQL Schema

- Click on the `sjam_connect` database
- Go to the **Import** tab
- Select the SQL file from the `database/` folder in this project
- Click **Go** to import

### 4. Configure Database Connection

Locate the database connection file (typically `config.php`, `db.php`, or similar inside a module folder) and update the credentials:

```php
<?php
$host     = "localhost";
$username = "root";        // Your MySQL username
$password = "";            // Your MySQL password (blank for default XAMPP)
$database = "sjam_connect";

$conn = mysqli_connect($host, $username, $password, $database);

if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}
?>
```

> **Note:** Check each module folder for its own connection file if credentials are not centralised.

---

## 🚀 Usage

Once the server is running and the database is configured:

1. Open your browser and go to:
   ```
   http://localhost/SJAM-Connect/mainPage/
   ```

2. **Register** a new account or **log in** with an existing account.

3. Navigate to the desired module:
   - **Hall** — Browse and book facility halls
   - **Equipment** — View and request equipment
   - **Ambulance** — Submit an emergency assistance request
   - **Feedback** — Leave feedback or a complaint

4. **Admin users** can access management dashboards to approve bookings, manage equipment, view feedback, and oversee user accounts.
