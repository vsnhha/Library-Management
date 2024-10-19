Library Management System
Project Overview
This Library Management System (LMS) is a web-based application developed in PHP and MySQL, designed to manage a library's operations efficiently. The system provides functionalities for both students/users and administrators to streamline processes such as:

User authentication and registration
Searching for books based on title and author
Renting and returning books
Tracking book availability
Managing rental deadlines and overdue fines
Sending notifications to users when books become available
Features
User Features
Login and Registration:

Users can register with their personal details and log in to the system to access their dashboard.
Search Books:

Users can search for books by title or author and view details such as book edition, publisher, and availability.
Rent Books:

Users can rent available books by selecting a rental period. The availability status of the book is updated in the system, and users are notified if they miss the return deadline (fines applied).
Book Availability Notifications:

Users can sign up to receive notifications via SMS when books become available for rent.
Admin Features
Manage Books:

Admins can add, update, or delete books from the library.
Monitor Rentals:

Admins can track the rental history of all users, including details of rented books, rental periods, and overdue fines.
User Management:

Admins can view and manage user profiles and rental records.
Fines Calculation
The system automatically calculates a fine of 50 rupees per day for overdue rentals.
Tech Stack
Frontend: HTML5, CSS3, Bootstrap
Backend: PHP (Procedural & OOP)
Database: MySQL
Libraries/Packages:
Twilio API for sending SMS notifications to users when books are available.
Composer for package management.
Database Schema
userlogin Table
Column	Type	Description
user_id	INT	Primary Key, Auto Increment
name	VARCHAR(255)	User's full name
email	VARCHAR(255)	User's email address
password	VARCHAR(255)	User's encrypted password
mobile	VARCHAR(15)	User's mobile number
fine	INT	User's accumulated fines
books Table
Column	Type	Description
book_id	INT	Primary Key, Auto Increment
book_name	VARCHAR(255)	Title of the book
author_name	VARCHAR(255)	Author of the book
publication	VARCHAR(255)	Publisher name
edition	VARCHAR(50)	Edition of the book
price	FLOAT	Price of the book
availability	INT	1 for available, 0 for rented
rentals Table
Column	Type	Description
rental_id	INT	Primary Key, Auto Increment
user_id	INT	Foreign Key, References userlogin
book_id	INT	Foreign Key, References books
start_date	DATE	Rental start date
end_date	DATE	Rental end date
returned	BOOLEAN	1 if returned, 0 if not
