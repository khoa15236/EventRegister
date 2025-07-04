Event Management System (SDN302 Exam)
This project implements a simple Event Management System for FPT University Da Nang, allowing administrative staff (Admins) to manage events and student registrations, while students can browse and register for events.

Features
Authentication & Authorization Secure login system with JWTs and role-based access control for students and admins.

Event Management Display a list of available events with capacity details.

Student Registration Students can register for events, with capacity constraints.

Student Unregistration Students can cancel their existing registrations.

Admin Registration View Admins can view a paginated list of all event registrations.

Admin Search Admins can search registrations by date range.

Responsive UI Basic responsive design for optimal viewing on different devices.

MVC Architecture Project organized following Model-View-Controller pattern.

Prerequisites
Before running the project, ensure you have the following installed

Node.js (v18 or higher recommended)

MongoDB (local instance or a cloud-hosted service like MongoDB Atlas)

Setup Instructions
Clone the repository (or create project directory)
If you haven't already, create a directory named your_name_event and set it up.

Initialize Node.js Project
Navigate to the project directory in your terminal and run

npm init -y

Install Dependencies
Install all required Node.js packages

npm install

(This will install express, mongoose, dotenv, jsonwebtoken, bcryptjs, cookie-parser, cors, ejs, and nodemon).

Create .env file
In the root directory of your project, create a file named .env and add the following environment variables

MONGO_URI=mongodblocalhost27017your_database_name
JWT_SECRET=your_super_secret_jwt_key_here_make_it_long_and_random
PORT=3000

Replace your_database_name with your desired MongoDB database name (e.g., fpt_events).

Replace your_super_secret_jwt_key_here_make_it_long_and_random with a strong, random string. You can generate one online.

Setup MongoDB Database
Ensure your MongoDB server is running. The application will connect to the MONGO_URI specified in your .env file.

To populate initial data (Optional but Recommended)
The project expects User and Event data to exist. You'll need to manually add some users (admin and student) and events to your MongoDB database.

For Users You can use a tool like MongoDB Compass or a simple Node.js script to create users. Remember to hash passwords.

Example admin user username admin, password admin123 (hashed)

Example student user username student1, password student123 (hashed)

For Events Add some events with name, description, date,  location, and capacity` fields.

Running the Application
Start the server

npm run dev

This will start the server using nodemon, which automatically restarts on file changes.

Access the application
Open your web browser and navigate to

httplocalhost3000

(Or the PORT you specified in .env)

Usage Instructions
Login
Access the application at httplocalhost3000.

Use your created admin or student credentials to log in.

Student Role
Register Events After logging in as a student, you will be redirected to the Register Events page (registerEvent). Here you can see available events and register for them (if capacity allows).

Cancel Registration Navigate to the Cancel Registration page (cancelRegistration) to view your registered events and cancel them.

Admin Role
View Registrations After logging in as an admin, you will be redirected to the View Registrations page (listRegistrations). This shows a paginated list of all event registrations.

Search Registrations Navigate to the Search Registrations page (searchRegistrations) to search for registrations within a specific date range.

Project Structure (MVC)
The project adheres to the Model-View-Controller (MVC) architectural pattern

models Contains Mongoose schemas and models for database interactions.

views Contains EJS templates for rendering dynamic HTML pages.

controllers Contains the logic for handling requests, interacting with models, and preparing data for views.

routes Defines API endpoints and their corresponding controller functions.

middleware Contains custom Express middleware for authentication and authorization.

public Serves static assets like CSS files.

server.js The main entry point of the application, setting up Express, connecting to the database, and defining global middleware.