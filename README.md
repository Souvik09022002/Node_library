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
   ```sh
  

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



INSERT INTO `books` (`book_id`, `user_id`, `genre`, `title`, `author`, `publisher`, `edition`, `isbn`, `pages`, `date_issued`) VALUES
(1, 5, 'Horror', 'Zombie Day', 'Kazi Nazrul Islam', 'Nazrul Publications', 3, 'jfklsgsdlg5qw7q87w', 800, '2018-07-10'),
(3, 4, 'Adventure', 'A Song of Ice & Fire', 'George R. R. Martin', 'Game of Thrones', 8, 'has23dadh123427', 1200, '2018-07-11'),
(4, 5, 'Adventure', 'Harry Potter & The Half Blood Prince', 'J.K Rowling', 'Rowling\'s Publications', 1, '31ghf1jk24kjb3l4l1gjh', 667, '2018-07-10'),
(5, 2, 'Adventure', 'Harry Potter & The Deadly Hallows', 'J.K Rowling', 'Rowling\'s Publications', 2, 'agsh32gqkj12bkl134', 798, '2018-07-10'),
(7, 2, 'Mystery', 'The Mysterious Affair at Styles', 'Agatha Christie', 'Agatha Publications', 2, '4zgdhdv2dfh81v31sdgj', 669, '2024-04-29'),
(10, 0, 'Modern Literature', 'In Search of Lost Time', 'Marcel Proust', 'NY Publishers', 8, '2j3nsd235habh3dfkj', 4215, '2018-07-11');




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


INSERT INTO `books_request` (`request_id`, `user_id`, `genre`, `title`, `author`, `edition`, `isbn`, `date`) VALUES
(1, 2, 'Mystery', 'Murder on the Orient Express', 'Agatha Christie', 3, '12gf3gj1jhr3jklj1ugjkb', '2018-07-10'),
(2, 5, 'Mystery', 'The Mysterious Affair at Styles', 'Agatha Christie', 3, '4zgdhdv2dfh81v31sdgj', '2018-07-10'),
(3, 4, 'Mystery', 'The Mysterious Affair at Styles', 'Agatha Christie', 3, '4zgdhdv2dfh81v31sdgj', '2018-07-10');


CREATE TABLE `issue_date` (
  `issue_id` int(10) NOT NULL,
  `book_id` int(10) NOT NULL,
  `user_id` int(10) NOT NULL,
  `date` date NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;



INSERT INTO `issue_date` (`issue_id`, `book_id`, `user_id`, `date`) VALUES
(1, 1, 2, '2018-07-10'),
(2, 5, 2, '2018-07-10'),
(3, 3, 2, '2018-07-10'),
(4, 4, 5, '2018-07-10'),
(5, 1, 2, '2018-07-10'),
(6, 5, 5, '2018-07-10'),
(7, 1, 5, '2018-07-10'),
(8, 4, 5, '2018-07-10'),
(9, 3, 5, '2018-07-10'),
(10, 5, 5, '2018-07-10'),
(11, 3, 5, '2018-07-10'),
(12, 3, 5, '2018-07-10'),
(13, 3, 5, '2018-07-10'),
(14, 3, 5, '2018-07-10'),
(15, 3, 4, '2018-07-10'),
(16, 1, 5, '2018-07-10'),
(17, 3, 5, '2018-07-10'),
(18, 5, 2, '2018-07-10'),
(19, 3, 4, '2018-07-11'),
(20, 7, 4, '2018-07-11'),
(21, 7, 5, '2018-07-11'),
(22, 3, 4, '2018-07-11'),
(23, 7, 2, '2024-04-29');


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


INSERT INTO `users` (`user_id`, `name`, `phone`, `email`, `is_admin`, `password`, `address`, `gender`) VALUES
(1, 'Souvik', '01711568524', 'souvik@gmail.com', 1, '1234', 'Howrah', 'Male'),
(2, 'Arefin', '01764431859', 'arefin@gmail.com', 0, 'yellow', 'Mirpur 13', 'Male'),
(4, 'A', '01924184941', 'A@outlook.com', 0, 'horse', 'Mirpur', 'Male'),
(5, 'Sovan', '01723645289', 'sovan@gmail.com', 0, 'abcd', 'Uttarpara, Sector 13', 'Male'),
(6, 'Jhuma', '01782963175', 'jhuma@gmail.com', 0, 'qwerty', 'duhhdhdhd', 'Male'),
(7, 'Istiak', '01932478293', 'istiakisha69@gmail.com', 0, 'istiak', 'Baily Road', 'Male'),
(8, 'Fahim Ahmed', '01726972364', 'fahim152@gmail.com', 0, 'fahimma', 'Kallayanpur', 'Male');


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
