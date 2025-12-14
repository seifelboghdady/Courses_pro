<p align="center">
  <img src="https://img.shields.io/badge/Node.js-18.x-green?logo=node.js" />
  <img src="https://img.shields.io/badge/License-MIT-blue" />
</p>

---

# 💻 RESTful API: CoursesAPP Backend

This repository hosts the backend service for **Courses\_pro**, a robust, scalable RESTful API built with Node.js and the Express framework. It is designed to manage course data, user authentication, and resource access for a learning platform.

## Table of Contents

1.  [🚀 Executive Summary](#1--executive-summary)
2.  [🔗 Live API & Documentation](#2--live-api--documentation)
3.  [🌐 API Endpoints (CRUD Operations)](#3--api-endpoints-crud-operations)
4.  [🎯 Project Architecture](#4--project-architecture)
5.  [🛠 Technology Stack](#5--technology-stack)
6.  [📁 File Structure](#6--file-structure)
7.  [⚙️ Local Development Setup](#️7--local-development-setup)
8.  [👤 Author & Contribution](#8--author--contribution)

---

## 1. 🚀 Executive Summary

The **Courses\_pro Backend** is a modular and scalable REST API implementing the **Model-View-Controller (MVC)** architectural pattern. It handles core business logic for a course management system, providing endpoints for creating, retrieving, updating, and deleting course resources, as well as managing user authentication and authorization.

The project emphasizes code clarity, separation of concerns, and security best practices for production deployment.

## 2. 🔗 Live API & Documentation

The API is currently hosted and running on Railway.

* **Base URL:** `https://coursespro-production.up.railway.app`
* **API Specification (Postman):**
    For a detailed list of all endpoints, required parameters, and response schemas, please refer to the public Postman specification:
    [Postman API Documentation Link](https://web.postman.co/workspace/My-Workspace~95afe2d7-608d-47b7-8fbf-96deeab9a74b/specification/35a06556-fc0c-492a-9e76-983846e3d5e8/file/9eb689b1-8466-4668-8416-12d9cf581102)

---

## 3. 🌐 API Endpoints (CRUD Operations)

All endpoints use the Base URL followed by the route prefix (e.g., `/api/courses`).

### 3.1 Course Management (`/api/courses`)

| HTTP Method | Endpoint | Description | Authentication |
| :--- | :--- | :--- | :--- |
| **GET** | `/` | Retrieves a list of all available courses. | Public |
| **GET** | `/:id` | Retrieves details for a single course by its ID. | Public |
| **POST** | `/` | Creates a new course resource. (Requires JSON body: `{"title": "...", "price": ...}`) | **Required (Admin)** |
| **PATCH** | `/:id` | Updates an existing course resource by ID. (Requires JSON body) | **Required (Admin)** |
| **DELETE** | `/:id` | Deletes a course resource by ID. | **Required (Admin)** |

### 3.2 User & Authentication (`/api/users`)

| HTTP Method | Endpoint | Description | Body Example (JSON/Form-Data) |
| :--- | :--- | :--- | :--- |
| **GET** | `/` | Retrieves a list of all registered users. | N/A |
| **POST** | `/register` | Registers a new user account. (Requires: `firstName`, `lastName`, `email`, `password`, `role`, and `avatar` file upload) | Form-Data |
| **POST** | `/login` | Authenticates a user and returns a token. (Requires: `{"email": "...", "password": "..."}`) | JSON |
| **GET** | `/uploads/:fileName` | Accesses and previews uploaded files (e.g., user avatars). | N/A |

---

## 4. 🎯 Project Architecture

The API adheres to the **Model-View-Controller (MVC)** pattern 

![Project Screenshot](uploads/screenshot.png)
, ensuring that the application logic is clearly separated, making the codebase easier to scale, maintain, and test.

| Component | Directory | Responsibility |
| :--- | :--- | :--- |
| **Model** | `models/` | Manages data structure, relationships, and direct interaction with the database. |
| **Controller** | `controllers/` | Contains the business logic, handles request input, and prepares the response. |
| **Routing** | `routes/` | Defines API endpoints and maps them to specific controller functions. |
| **Middleware** | `middlewares/` | Functions executed before the controller, used for authentication, validation, and error handling. |

## 5. 🛠 Technology Stack

| Technology | Role |
| :--- | :--- |
| **Node.js** | JavaScript runtime environment. |
| **Express.js** | Minimalist web application framework for building REST APIs. |
| **MongoDB** | NoSQL Database for flexible, high-performance data storage. |
| **Mongoose** | Object Data Modeling (ODM) library for MongoDB. |
| **JSON Web Tokens (JWT)** | Secure, state-less user authentication and authorization. |
| **`multer`** | Middleware for handling `multipart/form-data` (file uploads). |
| **Railway** | Production deployment and hosting platform. |

## 6. 📁 File Structure

The logical organization follows industry-standard Node.js practices:

```text
src/
├── config/            
├── controllers/        
├── middlewares/        
├── models/             
├── routes/            
├── utils/            
├── app.js            
└── server.js          
```

## 7. ⚙️ Local Development Setup

Follow these steps to get a development copy of the API running on your local machine.

### Prerequisites

* Node.js (LTS version recommended)
* npm or yarn
* A running instance of MongoDB

### Setup Procedure

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/seifelboghdady/Courses_pro.git](https://github.com/seifelboghdady/Courses_pro.git)
    cd Courses_pro
    ```
2.  **Install Dependencies:**
    ```bash
    npm install
    ```
3.  **Configure Environment Variables:**
    Create a `.env` file in the root directory and define necessary variables (e.g., Database URI, JWT Secret Key, Port).

    ```
    DATABASE_URI=mongodb://127.0.0.1:27017/coursesdb
    JWT_SECRET=your_super_secret_key
    ```
4.  **Start the Server:**
    ```bash
    # node index.js
    ```
    The server should now be running locally, typically accessible at `http://localhost:3000`. 

---

## 8. 👤 Author & Contribution

This project is developed and maintained by:

* **Author:** Seif El-Islam Elboghdady
* **GitHub Profile:** [https://github.com/seifelboghdady](https://github.com/seifelboghdady)






