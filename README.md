# Library Management System - Node.js & MySQL

## Introduction

This project aims to streamline day-to-day tasks for librarians by providing a user-friendly interface. The system consists of two main parts:

### Admin Part

Admins can log in using their email and password, accessing a dashboard displaying management statuses and customer details. Key functionalities include:

- View dashboard details
- Check own profile
- Update profile information
- Change password
- View all customer details
- Add and delete customers
- Edit customer details
- View book records
- Add new books
- Check issued books
- Accept user book requests
- View requested books

### User Part

Users can create new accounts and log in via email and password. Once logged in, they can:

- Access dashboard
- View total books borrowed
- View profile
- Edit and change own password
- View received books list
- Request books with details
- View book history and borrowed books

## Project Structure

|--/controller
|-admin.js
|-customer.js
|-login.js
|-logout.js
|-signup.js
|
|--/css
|-admin.css
|-customer.css
|-login.css
|-signup.css
|
|--/images
|
|--/models
|-bookModel.js
|-config.js
|-userModel.js
|
|--/views
|---/admin
|---/customer
|---/partials
|--login.ejs
|--signup.ejs
|----app.js
## System Requirements

- XAMPP server
- Node.js
- Visual Studio Code

## Installation Steps

### Step 1: Setting Up the Database

1. **Open XAMPP Server:**
   - Launch XAMPP Control Panel.

2. **Create Database:**
   - Open phpMyAdmin from XAMPP Control Panel.
   - Click on the "Databases" tab.
   - Enter the database name as "library_management_system".
   - Click on the "Create" button to create the database.

3. **Run SQL Script:**
   - Open the SQL tab in phpMyAdmin.
   - Copy and paste the following SQL script into the SQL tab:
     ```sql
     SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
     START TRANSACTION;
     SET time_zone = "+00:00";

     CREATE TABLE `books` (
       `book_id` int(100) NOT NULL,
       `user_id` int(100) DEFAULT NULL,
       `genre` varchar(300) NOT NULL,
       `title` varchar(300) NOT NULL,
       `author` varchar(300) NOT NULL,
       `publisher` varchar(300) NOT NULL,
       `edition` int(100) NOT NULL,
       `isbn` varchar(100) NOT NULL,
       `pages` int(100) NOT NULL,
       `date_issued` date DEFAULT NULL
     ) ENGINE=InnoDB DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

     -- Insert sample data into the books table here...

     CREATE TABLE `books_request` (
       `request_id` int(10) NOT NULL,
       `user_id` int(10) NOT NULL,
       `genre` varchar(300) NOT NULL,
       `title` varchar(300) NOT NULL,
       `author` varchar(300) NOT NULL,
       `edition` int(10) NOT NULL,
       `isbn` varchar(100) NOT NULL,
       `date` date NOT NULL
     ) ENGINE=InnoDB DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

     -- Insert sample data into the books_request table here...

     CREATE TABLE `issue_date` (
       `issue_id` int(10) NOT NULL,
       `book_id` int(10) NOT NULL,
       `user_id` int(10) NOT NULL,
       `date` date NOT NULL
     ) ENGINE=InnoDB DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

     -- Insert sample data into the issue_date table here...

     CREATE TABLE `users` (
       `user_id` int(100) NOT NULL,
       `name` varchar(300) NOT NULL,
       `phone` varchar(11) NOT NULL,
       `email` varchar(300) NOT NULL,
       `is_admin` tinyint(1) NOT NULL,
       `password` varchar(300) NOT NULL,
       `address` varchar(300) NOT NULL,
       `gender` varchar(300) NOT NULL
     ) ENGINE=InnoDB DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;

     -- Insert sample data into the users table here...

     ALTER TABLE `books`
       ADD PRIMARY KEY (`book_id`),
       ADD KEY `user_id` (`user_id`);

     ALTER TABLE `books_request`
       ADD PRIMARY KEY (`request_id`);

     ALTER TABLE `issue_date`
       ADD PRIMARY KEY (`issue_id`);

     ALTER TABLE `users`
       ADD PRIMARY KEY (`user_id`),
       ADD UNIQUE KEY `email` (`email`);

     ALTER TABLE `books`
       MODIFY `book_id` int(100) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;

     ALTER TABLE `books_request`
       MODIFY `request_id` int(10) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=4;

     ALTER TABLE `issue_date`
       MODIFY `issue_id` int(10) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=24;

     ALTER TABLE `users`
       MODIFY `user_id` int(100) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=9;
     COMMIT;
     ```
   - Click on the "Go" button to execute the script.

   **Note:** Replace the "-- Insert sample data..." comments with actual data if required.





### Step 2:

#### Option 1(Recomended):

1. Create a new folder.
2. Open terminal in the folder and execute:
   ```sh
   git clone https://github.com/Souvik09022002/Node_library.git
   cd .\Node_library\
   npm install
   npm start
#### Option 2:
 1.Download the zip file and extract it.
 2.Execute the following commands in the terminal:
 ```sh
 npm init -y
 npm install
 npm start
