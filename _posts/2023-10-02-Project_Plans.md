---
toc: true
comments: true
layout: post
title: Project Plans
description: xx
type: plans
courses: { compsci: {week: 6} }
---

# Astronomy Project Plan

## Project Overview

The goal of this project is to create an astronomy-focused platform that provides users with information about celestial events, celestial objects, and allows them to track and record their observations. The project will consist of a Java backend, a frontend built using HTML, CSS, and JavaScript (React or Angular), and will be deployed on AWS (Amazon Web Services).

## Team Roles

- Scrum Master: Paaras
- DevOps: Yuri
- Frontend Developer: Shreyas
- Backend Developer: Tanay

## Technology Stack

- **Backend**:
  - Java with Spring Boot
  - Amazon RDS for database storage
  - Amazon S3 for image storage
  - Amazon SNS for notifications
  
- **Frontend**:
  - React (or Angular) for the user interface
  - HTML, CSS, JavaScript for frontend development
  - API calls to the backend for data retrieval

## Detailed Plan

### 1. Backend Development

- Set up the Java Spring Boot application with a clean project structure.
- Design and implement RESTful APIs for the following functionalities:
  - Celestial events (GET: /events)
  - Celestial objects (GET: /objects)
  - User registration (POST: /register)
  - User login (POST: /login)
  - User favorites (GET: /favorites, POST: /favorites, DELETE: /favorites/{objectId})
- Implement authentication and authorization mechanisms for user registration and login.
- Integrate a notification system using Amazon SNS to inform users about upcoming celestial events.
- Implement robust error handling and logging mechanisms.
- Test the backend APIs thoroughly, including unit tests and integration tests, to ensure reliability.

### 2. Frontend Development

- Choose a frontend framework (React or Angular) and set up the project.
- Design and develop the following frontend components:
  - User registration form
  - User login form
  - Celestial events display page
  - Celestial objects catalog
  - User favorites management page
  - Notifications display for upcoming celestial events
- Create a user-friendly and responsive design that aligns with the astronomy theme.
- Implement logic for making API requests to the backend to fetch data and manage user interactions.
- Ensure a smooth and intuitive user experience.
- Conduct thorough testing of frontend components, including functionality and UI/UX.

### 3. Database Setup (Amazon RDS)

- Set up an Amazon RDS database instance to store user data and celestial event information.
- Define and create database schemas for:
  - User accounts (including user authentication data)
  - Celestial events data (event name, date, description, etc.)
  - Celestial objects data (object name, image, description, etc.)
- Establish a secure connection between the backend application and the RDS database.
- Implement necessary database operations for user registration, login, and managing celestial event data.

### 4. Cloud Deployment (Amazon EC2)

- Set up an Amazon EC2 instance to host the backend application.
- Configure the environment on EC2, including installing required dependencies and libraries.
- Deploy the backend application to the EC2 instance.
- Set up an Amazon S3 bucket for storing user-uploaded images and celestial object images.
- Ensure secure access control to the S3 bucket.

### 5. Integration and Testing

- Integrate the frontend, backend, and database components to create a cohesive application.
- Conduct comprehensive testing, including:
  - Unit testing for individual backend and frontend components.
  - Integration testing to ensure smooth interaction between frontend and backend.
  - User acceptance testing to validate the entire application's functionality.
- Collaborate to address any bugs, issues, or optimizations identified during testing.

## Timeline

- **Week 1-2**: Backend development, API implementation, and database setup.
- **Week 3-4**: Frontend development, user interface design, and integration with backend.
- **Week 5-6**: Cloud deployment of the backend, configuration, and S3 setup.
- **Week 7-8**: Comprehensive testing, bug fixing, and optimization of the application.

## Communication and Collaboration

- Regular team meetings will be conducted using video conferencing tools.
- Collaboration and project tracking will be managed using Notion or a similar project management tool.