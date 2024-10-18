# Blog Application

A simple blog application built with Node.js, Express, and MySQL that allows users to create, delete, update, and view blog posts.

## Features

- Create, edit, update, and delete blog posts.
- Store blog data in a MySQL database.
- User-friendly API for interacting with the blog posts.
- Basic error handling for database and application errors.

## Table of Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Database Schema](#database-schema)
- [Technologies](#technologies)

## Installation

### Prerequisites

Ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/en/download/) (v14.x or higher)
- [MySQL](https://www.mysql.com/) (v5.7 or higher)

### Steps

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/blog-app.git
   cd blog-app
   ```

2. Install the dependencies:

   ```bash
   npm install
   ```

3. Set up the database:

   - Create a new MySQL database.
   - Update the database configuration in the `.env` file (see [Configuration](#configuration)).

4. Run the application:

   ```bash
   npm start
   ```

## Configuration

This application uses environment variables for configuration. You will need to create a `.env` file in the root directory of the project with the following content:

```bash
DB_HOST=localhost
DB_PORT=3307    # or your preferred MySQL port
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=blog_db
```

## Usage

To start the application, run:

```bash
npx nodemon app.js
```

The application will be accessible at http://localhost:3000.

## API Endpoints

The application provides the following RESTful API endpoints to interact with the blog:

### 1. Get all blog posts

- **URL**: `/api/posts`
- **Method**: `GET`
- **Description**: Retrieve all blog posts from the database.

### 2. Get a single blog post by ID

- **URL**: `/api/posts/:id`
- **Method**: `GET`
- **Description**: Retrieve a single blog post by its ID.

### 3. Create a new blog post

- **URL**: `/api/posts`
- **Method**: `POST`
- **Description**: Create a new blog post.
- **Body Parameters**:
  - `title` (string): The title of the blog post.
  - `content` (string): The content of the blog post.

### 4. Update a blog post

- **URL**: `/api/posts/:id`
- **Method**: `PUT`
- **Description**: Update an existing blog post by its ID.
- **Body Parameters**:
  - `title` (string): The updated title of the blog post.
  - `content` (string): The updated content of the blog post.

### 5. Delete a blog post

- **URL**: `/api/posts/:id`
- **Method**: `DELETE`
- **Description**: Delete a blog post by its ID.

## Database Schema

Here's the schema for the `posts` table in MySQL:

```sql
CREATE TABLE posts (
  id INT AUTO_INCREMENT PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  content TEXT NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

## Technologies

- [Node.js](https://nodejs.org/) - JavaScript runtime
- [Express](https://expressjs.com/) - Web framework for Node.js
- [MySQL](https://www.mysql.com/) - Relational database
- [dotenv](https://www.npmjs.com/package/dotenv) - For environment variable management
