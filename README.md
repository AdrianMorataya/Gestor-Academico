# Gestor Académico API

A RESTful API for academic management, designed to handle students, teachers, courses, enrollment and user profiles in an educational environment.

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/Express-404040?style=flat-square&logo=express&logoColor=white" alt="Express.js" />
  <img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" alt="MongoDB" />
  <img src="https://img.shields.io/badge/Mongoose-880000?style=flat-square&logo=mongoose&logoColor=white" alt="Mongoose" />
  <img src="https://img.shields.io/badge/JWT-333333?style=flat-square&logo=jsonwebtokens&logoColor=white" alt="JWT" />
  <img src="https://img.shields.io/badge/License-MIT-6B7280?style=flat-square" alt="MIT License" />
</p>

---

## Overview

**Gestor Académico API** is a backend project developed to support academic administration through a modular REST API.

It provides separate functionality for students and teachers, with role-based access, course management and student enrollment. The application uses MongoDB for data persistence and JWT for token-based authentication.

## Features

- **User authentication:** Registration and login for students and teachers.
- **Role-based access:** Separate student and teacher roles.
- **Student management:** Retrieve, update and delete student profiles.
- **Teacher management:** Manage teacher profiles and their information.
- **Course management:** Create, list, update and delete courses.
- **Course enrollment:** Students can enroll in up to three courses.
- **Enrollment consistency:** Course updates and deletions trigger corresponding enrollment changes.
- **Profile pictures:** Support for uploading profile images.
- **Password management:** Password updates and secure password hashing.
- **Request validation:** Input validation and middleware for API requests.

## Tech Stack

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | REST API framework |
| MongoDB | NoSQL database |
| Mongoose | Database modeling and queries |
| JSON Web Token | Authentication tokens |
| Argon2 | Password hashing |
| Express Validator | Request validation |
| Helmet | HTTP security headers |
| Express Rate Limit | Request rate limiting |
| Multer | File uploads |
| Morgan | HTTP request logging |
| dotenv | Environment configuration |

## User Roles

### Student

- Register and authenticate.
- View and manage their profile.
- Update their password.
- Enroll in up to three courses.
- Retrieve their assigned courses.

### Teacher

- Register and authenticate.
- Manage their profile.
- Create and manage their own courses.
- Retrieve courses associated with their account.
- Update or delete courses while maintaining enrollment consistency.

## API Endpoints

The API exposes endpoints for authentication, students, teachers and courses.

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/registerStudent` | Register a student |
| `POST` | `/api/auth/registerTeacher` | Register a teacher |
| `POST` | `/api/auth/login` | Authenticate a user |
| `GET` | `/api/student/` | List students |
| `GET` | `/api/student/:id` | Retrieve a student |
| `PUT` | `/api/student/updateStudent/:id` | Update a student |
| `DELETE` | `/api/student/deleteStudent/:id` | Delete a student |
| `PATCH` | `/api/student/updatePassword/:id` | Update a student's password |
| `POST` | `/api/student/enrollInCourse` | Enroll a student in a course |
| `GET` | `/api/student/getCourses/:id` | Retrieve a student's courses |
| `GET` | `/api/teacher/` | List teachers |
| `GET` | `/api/teacher/findTeacher/:id` | Retrieve a teacher |
| `DELETE` | `/api/teacher/deleteTeacher/:id` | Delete a teacher |
| `PATCH` | `/api/teacher/updatePassword/:id` | Update a teacher's password |
| `POST` | `/api/teacher/addCourse` | Create a course |
| `PUT` | `/api/teacher/updateCourse/:id` | Update a course |
| `DELETE` | `/api/teacher/deleteCourse/:id` | Delete a course |
| `GET` | `/api/teacher/getCourses/:id` | Retrieve a teacher's courses |
| `GET` | `/api/course/` | List all courses |

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/)
- [MongoDB](https://www.mongodb.com/)
- npm

### Installation

Clone the repository and install the dependencies:

```bash
git clone https://github.com/AdrianMorataya/Gestor-Academico.git
cd Gestor-Academico
npm install
```

### Environment Configuration

Create a `.env` file in the root directory and configure the environment variables required by the application.

```env
PORT=3000
URI_MONGO=mongodb://127.0.0.1:27017/gestor_academico
```

These values are examples. Verify the variable names and database configuration used in the source code before running the application.

**Security note:** Never commit database credentials, authentication secrets or other sensitive environment variables.

### Run the Application

Start the server:

```bash
npm start
```

For development with Node.js watch mode:

```bash
npm run dev
```

## Testing the API

You can test the endpoints using [Postman](https://www.postman.com/) or another HTTP client.

For requests involving profile pictures, use `multipart/form-data`. For JSON-based requests, send the appropriate `Content-Type: application/json` header.

Protected endpoints may require an authentication token, depending on the route configuration.

## Security

The project incorporates several security-related dependencies, including password hashing, JWT, request validation, rate limiting and HTTP security headers.

For production use, ensure that sensitive routes enforce authentication and role-based authorization, validate uploaded files, and keep secrets outside version control.

## License

This project is distributed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

<p align="center">
  <sub>Developed by <a href="https://github.com/AdrianMorataya">Adrian Morataya</a></sub>
</p>
