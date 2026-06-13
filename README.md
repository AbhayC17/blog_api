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
```

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
```

---

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/blog-api-crud-pagination.git
```

### 2. Move into the Project Folder

```bash
cd blog-api-crud-pagination
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Create `.env` File

Create a `.env` file in the root directory and add the following:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/blog_api
JWT_SECRET=your_super_secret_key
```

For MongoDB Atlas, replace the local MongoDB URI with your MongoDB Atlas connection string.

Example:

```env
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/blog_api
```

---

## Environment Variables

| Variable | Description |
|---|---|
| PORT | Port number on which the server runs |
| MONGO_URI | MongoDB connection string |
| JWT_SECRET | Secret key used to generate JWT tokens |

---

## Running the Project

### Development Mode

```bash
npm run dev
```

### Production Mode

```bash
npm start
```

If the server starts successfully, the terminal will show:

```bash
MongoDB connected successfully
Server running on port 5000
```

Open the browser and visit:

```bash
http://localhost:5000
```

Expected response:

```bash
Blog API is running successfully
```

---

## API Endpoints

---

# Authentication Routes

## Register User

### Endpoint

```http
POST /api/auth/register
```

### Full URL

```http
http://localhost:5000/api/auth/register
```

### Request Body

```json
{
  "name": "Abhay",
  "email": "abhay@example.com",
  "password": "123456"
}
```

### Success Response

```json
{
  "message": "User registered successfully",
  "user": {
    "id": "user_id",
    "name": "Abhay",
    "email": "abhay@example.com"
  },
  "token": "jwt_token"
}
```

### Explanation

This endpoint creates a new user account. The password is hashed before being stored in the database. After successful registration, a JWT token is generated and sent in the response.

---

## Login User

### Endpoint

```http
POST /api/auth/login
```

### Full URL

```http
http://localhost:5000/api/auth/login
```

### Request Body

```json
{
  "email": "abhay@example.com",
  "password": "123456"
}
```

### Success Response

```json
{
  "message": "Login successful",
  "user": {
    "id": "user_id",
    "name": "Abhay",
    "email": "abhay@example.com"
  },
  "token": "jwt_token"
}
```

### Explanation

This endpoint checks the user's email and password. If the credentials are correct, a JWT token is generated. This token is used to access protected routes.

---

# Blog Post Routes

## Create Blog Post

### Endpoint

```http
POST /api/posts
```

### Full URL

```http
http://localhost:5000/api/posts
```

### Headers

```http
Authorization: Bearer your_token_here
```

### Request Body

```json
{
  "title": "My First Blog",
  "content": "This is my first blog post created using Node.js and MongoDB."
}
```

### Success Response

```json
{
  "message": "Post created successfully",
  "post": {
    "_id": "post_id",
    "title": "My First Blog",
    "content": "This is my first blog post created using Node.js and MongoDB.",
    "author": "user_id",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Explanation

This endpoint allows an authenticated user to create a blog post. The user must send a valid JWT token in the Authorization header.

---

## Get All Blog Posts

### Endpoint

```http
GET /api/posts
```

### Full URL

```http
http://localhost:5000/api/posts
```

### Success Response

```json
{
  "currentPage": 1,
  "totalPages": 1,
  "totalPosts": 1,
  "posts": [
    {
      "_id": "post_id",
      "title": "My First Blog",
      "content": "This is my first blog post created using Node.js and MongoDB.",
      "author": {
        "_id": "user_id",
        "name": "Abhay",
        "email": "abhay@example.com"
      },
      "createdAt": "date",
      "updatedAt": "date"
    }
  ]
}
```

### Explanation

This endpoint returns all blog posts. It is a public route and does not require authentication.

---

## Get Posts with Pagination

### Endpoint

```http
GET /api/posts?page=1&limit=5
```

### Full URL

```http
http://localhost:5000/api/posts?page=1&limit=5
```

### Query Parameters

| Parameter | Description |
|---|---|
| page | The page number to be displayed |
| limit | The number of posts to display per page |

### Explanation

This endpoint returns a limited number of posts per page. Pagination improves performance because the API does not load all posts at once.

Example:

```http
GET /api/posts?page=2&limit=5
```

This skips the first 5 posts and returns the next 5 posts.

---

## Search Blog Posts

### Endpoint

```http
GET /api/posts?search=node
```

### Full URL

```http
http://localhost:5000/api/posts?search=node
```

### Explanation

This endpoint searches blog posts by title or content. The search is case-insensitive.

For example, searching for `node` can match:

```text
node
Node
NODE
```

---

## Pagination with Search

### Endpoint

```http
GET /api/posts?page=1&limit=5&search=node
```

### Full URL

```http
http://localhost:5000/api/posts?page=1&limit=5&search=node
```

### Explanation

This endpoint combines pagination and search. It returns paginated results that match the search keyword.

---

## Get Single Blog Post

### Endpoint

```http
GET /api/posts/:id
```

### Full URL Example

```http
http://localhost:5000/api/posts/64f123456789abcdef123456
```

### Explanation

This endpoint returns a single blog post using its post ID.

---

## Update Blog Post

### Endpoint

```http
PUT /api/posts/:id
```

### Full URL Example

```http
http://localhost:5000/api/posts/64f123456789abcdef123456
```

### Headers

```http
Authorization: Bearer your_token_here
```

### Request Body

```json
{
  "title": "Updated Blog Title",
  "content": "Updated blog content."
}
```

### Success Response

```json
{
  "message": "Post updated successfully",
  "post": {
    "_id": "post_id",
    "title": "Updated Blog Title",
    "content": "Updated blog content.",
    "author": "user_id"
  }
}
```

### Explanation

This endpoint allows a user to update a blog post. It is a protected route. Only the user who created the blog post can update it.

---

## Delete Blog Post

### Endpoint

```http
DELETE /api/posts/:id
```

### Full URL Example

```http
http://localhost:5000/api/posts/64f123456789abcdef123456
```

### Headers

```http
Authorization: Bearer your_token_here
```

### Success Response

```json
{
  "message": "Post deleted successfully"
}
```

### Explanation

This endpoint allows a user to delete a blog post. It is a protected route. Only the user who created the blog post can delete it.

---

## Authentication Flow

The authentication flow works as follows:

1. The user registers with name, email, and password.
2. The password is hashed using bcrypt.js.
3. The user data is stored in MongoDB.
4. The user logs in with email and password.
5. The backend compares the entered password with the hashed password.
6. If the credentials are valid, the backend generates a JWT token.
7. The token is sent to the client.
8. For protected routes, the client sends the token in the Authorization header.
9. The authentication middleware verifies the token.
10. If the token is valid, the user is allowed to access the protected route.

---

## CRUD Operations

CRUD stands for:

| Operation | Meaning | Example in This Project |
|---|---|---|
| Create | Add new data | Create a blog post |
| Read | Fetch data | Get all posts or a single post |
| Update | Modify existing data | Update a blog post |
| Delete | Remove data | Delete a blog post |

In this project, CRUD is implemented for blog posts.

---

## Pagination Logic

Pagination is used to divide large amounts of data into smaller pages.

The API accepts two query parameters:

```javascript
page
limit
```

Example:

```http
GET /api/posts?page=2&limit=5
```

Pagination logic:

```javascript
const page = Number(req.query.page) || 1;
const limit = Number(req.query.limit) || 5;
const skip = (page - 1) * limit;
```

If:

```javascript
page = 2
limit = 5
```

Then:

```javascript
skip = (2 - 1) * 5
skip = 5
```

This means the API skips the first 5 posts and returns the next 5 posts.

---

## Search Logic

Search is implemented using MongoDB regular expressions.

```javascript
const searchQuery = {
  $or: [
    { title: { $regex: search, $options: "i" } },
    { content: { $regex: search, $options: "i" } }
  ]
};
```

Explanation:

- `$or` checks multiple fields.
- `$regex` is used to match text.
- `$options: "i"` makes the search case-insensitive.
- The API searches both title and content.

Example:

```http
GET /api/posts?search=javascript
```

This returns blog posts where the title or content contains the word `javascript`.

---

## Ownership Restriction

Ownership restriction means that only the creator of a blog post can update or delete that blog post.

Each blog post stores the author's user ID.

Example post:

```json
{
  "title": "My First Blog",
  "content": "This is my blog content",
  "author": "user_id"
}
```

When a user tries to update or delete a post, the backend compares:

```javascript
post.author.toString() !== req.user._id.toString()
```

If both IDs are the same, the user is allowed to update or delete the post.

If both IDs are different, the request is rejected.

This prevents one user from modifying another user's blog post.

---

## Protected Routes

Protected routes require a valid JWT token.

The following routes are protected:

```http
POST /api/posts
PUT /api/posts/:id
DELETE /api/posts/:id
```

The following routes are public:

```http
GET /api/posts
GET /api/posts/:id
POST /api/auth/register
POST /api/auth/login
```

---

## Testing the API

The API can be tested using:

- Postman
- Thunder Client
- Insomnia
- Browser for GET requests

Recommended testing order:

1. Register a user.
2. Login with the registered user.
3. Copy the JWT token.
4. Create a blog post using the token.
5. Get all blog posts.
6. Test pagination.
7. Test search.
8. Get a single blog post.
9. Update the blog post using the token.
10. Delete the blog post using the token.

---

## Example Authorization Header

For protected routes, add this header:

```http
Authorization: Bearer your_jwt_token_here
```

Example:

```http
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

Without this token, protected routes will return an unauthorized error.

---

## Sample Error Responses

### Missing Token

```json
{
  "message": "Not authorized, token missing"
}
```

### Invalid Token

```json
{
  "message": "Not authorized, token failed"
}
```

### User Already Exists

```json
{
  "message": "User already exists"
}
```

### Invalid Login Credentials

```json
{
  "message": "Invalid email or password"
}
```

### Post Not Found

```json
{
  "message": "Post not found"
}
```

### Unauthorized Update or Delete

```json
{
  "message": "You can update only your own post"
}
```

or

```json
{
  "message": "You can delete only your own post"
}
```

---

## Database Models

## User Model

The User model stores user details.

```javascript
{
  name: String,
  email: String,
  password: String
}
```

Fields:

| Field | Description |
|---|---|
| name | Name of the user |
| email | Email address of the user |
| password | Hashed password of the user |

---

## Post Model

The Post model stores blog post details.

```javascript
{
  title: String,
  content: String,
  author: ObjectId
}
```

Fields:

| Field | Description |
|---|---|
| title | Title of the blog post |
| content | Main content of the blog post |
| author | User ID of the person who created the post |

The `author` field connects a blog post with a user.

---

## Security Features

- Passwords are hashed before storing in the database.
- JWT token is used for authentication.
- Protected routes cannot be accessed without a valid token.
- Users can only update or delete their own posts.
- Sensitive data is stored in environment variables.
- `.env` file is ignored using `.gitignore`.

---

## Expected Deliverables

- CRUD API for blog posts
- Pagination and search endpoints
- Authentication for restricted actions
- MongoDB database schema
- Clean and reusable backend code
- Protected routes using middleware
- Ownership restriction for edits and deletes
- API tested using Postman or Thunder Client
- GitHub repository with complete source code
- Deployed backend API

---

## Evaluation Criteria

This project satisfies the following evaluation criteria:

- CRUD operations work as expected.
- Code is clean, reusable, and modular.
- Authentication is implemented for protected endpoints.
- Pagination and search are implemented efficiently.
- MongoDB database integration is completed.
- Blog post ownership restriction is implemented.
- API responses are clear and structured.

---

## Screenshots to Include in Submission

Recommended screenshots:

1. Project folder structure in VS Code.
2. Server running successfully in terminal.
3. MongoDB connection success message.
4. Register API working in Postman.
5. Login API working and JWT token generated.
6. Create blog post API working.
7. Get all posts API working.
8. Pagination API working.
9. Search API working.
10. Get single post API working.
11. Update post API working.
12. Delete post API working.
13. MongoDB database showing users and posts collections.

---

## Future Enhancements

- Add comments for blog posts.
- Add likes and dislikes.
- Add user profile management.
- Add image upload for blog posts.
- Add categories and tags.
- Add role-based authorization.
- Add admin dashboard.
- Add input validation using Joi or Zod.
- Add API documentation using Swagger.
- Add frontend using React.js.
- Deploy backend using Render, Railway, or Vercel.
- Use MongoDB Atlas for cloud database.

---

## Learning Outcomes

Through this project, the following backend development concepts are learned:

- Creating a REST API using Express.js
- Connecting Node.js with MongoDB
- Designing Mongoose schemas
- Implementing user authentication
- Hashing passwords securely
- Generating and verifying JWT tokens
- Creating protected routes
- Writing middleware
- Performing CRUD operations
- Implementing pagination
- Implementing search functionality
- Handling errors in API responses
- Structuring a backend project professionally

---

## Author

**Abhay Chandrik**  
B.E. Computer Science and Engineering  
Vidyavardhaka College of Engineering, Mysuru

---

## Project Status

Core backend features completed:

- User registration
- User login
- JWT authentication
- Blog CRUD operations
- Search functionality
- Pagination functionality
- Protected routes
- Ownership restriction
- MongoDB integration
- Clean folder structure
- API testing support

---

## License

This project is created for learning and internship project submission purposes.
