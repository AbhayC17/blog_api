# Blog API with CRUD, Pagination, Search and Authentication

A backend development project built using **Node.js, Express.js, MongoDB, Mongoose, JWT, and bcrypt.js**.

This project is a RESTful Blog API that allows users to register, login, create blog posts, view posts, search posts, paginate results, update posts, and delete posts. It also includes authentication for protected routes and ownership restrictions so that only the creator of a blog post can update or delete it.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation and Setup](#installation-and-setup)
- [Environment Variables](#environment-variables)
- [Running the Project](#running-the-project)
- [API Endpoints](#api-endpoints)
- [Authentication Flow](#authentication-flow)
- [CRUD Operations](#crud-operations)
- [Pagination Logic](#pagination-logic)
- [Search Logic](#search-logic)
- [Ownership Restriction](#ownership-restriction)
- [Testing the API](#testing-the-api)
- [Expected Deliverables](#expected-deliverables)
- [Future Enhancements](#future-enhancements)
- [Author](#author)

---

## Project Overview

The **Blog API with CRUD, Pagination, Search and Authentication** is a backend project designed to manage blog posts using REST API principles.

Users can create an account and login using their credentials. After successful login, the server generates a JWT token. This token is required to access protected routes such as creating, updating, and deleting blog posts.

The API allows public users to view blog posts, search posts by keyword, and retrieve paginated results. Authenticated users can create posts, but they can update or delete only the posts that they have created.

This project demonstrates important backend development concepts such as routing, controllers, database models, authentication middleware, password hashing, JWT-based authorization, MongoDB integration, search functionality, pagination, and ownership-based access control.

---

## Features

- User registration
- User login
- Password hashing using bcrypt.js
- JWT-based authentication
- Protected API routes
- Create blog posts
- Read all blog posts
- Read a single blog post
- Update blog posts
- Delete blog posts
- Ownership restriction for update and delete operations
- Search blog posts by title or content
- Pagination support
- MongoDB database integration
- Mongoose schema design
- Clean and modular backend structure
- Environment variable configuration
- API testing support using Postman or Thunder Client

---

## Tech Stack

| Technology | Purpose |
|---|---|
| Node.js | Runtime environment for running JavaScript on the server |
| Express.js | Backend framework for creating REST APIs |
| MongoDB | NoSQL database for storing users and blog posts |
| Mongoose | ODM library for working with MongoDB |
| JWT | Used for authentication and protected routes |
| bcrypt.js | Used for hashing user passwords |
| dotenv | Used for managing environment variables |
| cors | Used to allow cross-origin requests |
| nodemon | Used to automatically restart the server during development |
| Postman | Used for testing API endpoints |

---

## Project Structure

```bash
blog-api-crud-pagination
│
├── config
│   └── db.js
│
├── controllers
│   ├── authController.js
│   └── postController.js
│
├── middleware
│   └── authMiddleware.js
│
├── models
│   ├── User.js
│   └── Post.js
│
├── routes
│   ├── authRoutes.js
│   └── postRoutes.js
│
├── .env
├── .gitignore
├── package.json
└── server.js
