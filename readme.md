# Lab CRUD API

## Setup

1. Install dependencies:
   ```sh
   npm install
   ```

2. Create a `.env` file:
   ```env
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=yourpassword
   DB_NAME=lab_crud_3isc
   PORT=3000
   ```

3. Initialize MySQL database:
   ```sql
   CREATE DATABASE lab_crud_3isc;
   CREATE TABLE courses (
     id INT AUTO_INCREMENT PRIMARY KEY,
     code VARCHAR(20) UNIQUE NOT NULL,
     title VARCHAR(255) NOT NULL,
     units INT,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   CREATE TABLE students (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(255) NOT NULL,
     email VARCHAR(255) UNIQUE NOT NULL,
     course VARCHAR(255),
     year_level INT
   );
   ```

4. Run the server:
   ```sh
   npm run dev   # with nodemon
   # or
   npm start
   ```

Server runs at: [http://localhost:3000](http://localhost:3000)

## API Endpoints

**Health**
- `GET /api/health`

**Students**
- `GET /api/students`
- `GET /api/students/:id`
- `POST /api/students`
- `PUT /api/students/:id`
- `DELETE /api/students/:id`  
  Example body:
  ```json
  {
    "name": "John Doe",
    "email": "john@example.com",
    "course": "BSCS",
    "year_level": 3
  }
  ```

**Courses**
- `GET /api/courses`
- `GET /api/courses/:id`
- `POST /api/courses`
- `PUT /api/courses/:id`
- `DELETE /api/courses/:id`  
  Example body:
  ```json
  {
    "code": "CS101",
    "title": "Intro to Computer Science",
    "units": 3
  }
  ```
