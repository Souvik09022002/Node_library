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

### Step 1:

1. Open XAMPP server.
2. Create a database named 
 
 "library_management_system".

3. Run "library_management_system.sql"  codes  on XAMPP SQL section.

### Step 2:

#### Option 1:

1. Create a new folder.
2. Open terminal in the folder and execute:
   ```sh
   git clone https://github.com/Souvik09022002/Node_library.git
   npm install
   npm start
#### Option 2:
 1.Download the zip file and extract it.
 2.Execute the following commands in the terminal:
 ```sh
 npm init -y
 npm install
 npm start
