# 🎓 Student Management System

A full-stack **Student Management System** built with **React, FastAPI, MySQL, SQLAlchemy and Docker**, and deployed on **AWS EC2**.

The application provides a simple web interface for managing student records through a REST API, with the complete application containerized using Docker.

## 🚀 Live Demo

**Application:**
http://3.6.168.234

**Backend API:**
http://3.6.168.234:8000

**API Documentation (Swagger):**
http://3.6.168.234:8000/docs

---

## 📌 Project Overview

The Student Management System is a full-stack application designed to demonstrate the complete development and deployment lifecycle of a modern web application.

Users can interact with the frontend to manage student information, while the FastAPI backend handles API requests and communicates with a MySQL database.

The application is containerized with Docker and deployed on an AWS EC2 instance.

### Application Flow

```text
User
  │
  ▼
React Frontend
  │
  │ HTTP Requests
  ▼
FastAPI Backend
  │
  │ SQLAlchemy
  ▼
MySQL Database
```

---

## ✨ Features

* 👨‍🎓 Add student records
* 📋 View student records
* 🔄 REST API based communication
* 🗄️ MySQL database integration
* 🐍 FastAPI backend
* ⚛️ React frontend
* 🔗 SQLAlchemy ORM
* 🐳 Docker containerization
* ☁️ AWS EC2 deployment
* 📖 Swagger API documentation
* 🔐 Environment-based database configuration
* 🔄 Docker restart policy for application containers

---

## 🛠️ Tech Stack

### Frontend

* React
* Vite
* JavaScript
* HTML
* CSS

### Backend

* Python
* FastAPI
* Uvicorn
* SQLAlchemy
* PyMySQL

### Database

* MySQL 8.0

### DevOps / Deployment

* Docker
* Docker Compose
* Docker Hub
* AWS EC2
* Ubuntu

### Version Control

* Git
* GitHub

---

## 🏗️ Project Structure

```text
student_management_system/
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── database.py
│   │   └── ...
│   │
│   ├── Dockerfile
│   ├── requirements.txt
│   ├── .dockerignore
│   └── .gitignore
│
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   └── ...
│   │
│   ├── Dockerfile
│   ├── package.json
│   └── .dockerignore
│
├── docker-compose.yml
├── .gitignore
└── README.md
```

---

## 🐳 Docker Architecture

The application is divided into three Docker services:

```text
                    AWS EC2
                       │
          ┌────────────┴────────────┐
          │                         │
     Frontend                    Backend
     React/Vite                  FastAPI
       :80                        :8000
          │                         │
          └──────────┬──────────────┘
                     │
                  MySQL
               Docker Network
```

### Containers

| Service  | Technology        |     Port |
| -------- | ----------------- | -------: |
| Frontend | React + Vite      |       80 |
| Backend  | FastAPI + Uvicorn |     8000 |
| Database | MySQL 8.0         | Internal |

The MySQL database is kept inside the Docker network and is **not publicly exposed**.

---

## ⚙️ Environment Configuration

Database credentials are provided through environment variables.

Example:

```env
DB_USERNAME=root
DB_PASSWORD=your_password
DB_HOST=localhost
DB_PORT=3306
DB_NAME=sms
```

For Docker deployment, the backend receives the database configuration from `docker-compose.yml`.

> `.env` files are excluded from Git using `.gitignore` so that sensitive credentials are not committed to the repository.

---

## 🐳 Running with Docker

Make sure Docker and Docker Compose are installed.

Clone the repository:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd student_management_system
```

Start the application:

```bash
docker compose up -d
```

Check running containers:

```bash
docker ps
```

Stop the application:

```bash
docker compose down
```

---

## 🔌 API Endpoints

The backend exposes REST API endpoints for student management.

### Health / Home

```http
GET /
```

### Get Students

```http
GET /students
```

### Create Student

```http
POST /students
```

Example request:

```json
{
  "name": "Rahul Sharma",
  "email": "rahul@example.com",
  "age": 22
}
```

The API can also be explored interactively through Swagger:

**Swagger UI:**
http://3.6.168.234:8000/docs

---

## ☁️ AWS Deployment

The application is deployed on an **AWS EC2 Ubuntu server**.

Deployment flow:

```text
Local Development
       │
       ▼
     Git
       │
       ▼
    GitHub
       │
       ▼
  Docker Images
       │
       ▼
   Docker Hub
       │
       ▼
   AWS EC2
       │
       ▼
 Docker Compose
       │
       ├── Frontend
       ├── Backend
       └── MySQL
```

The Docker containers are configured with:

```yaml
restart: unless-stopped
```

This allows the containers to automatically restart after common container/host restart scenarios.

---

## 🔒 Security Considerations

* Database credentials are not committed to GitHub.
* `.env` files are ignored using `.gitignore`.
* MySQL is not exposed publicly.
* Backend and frontend communicate through HTTP.
* Docker isolates the application services.

> For production systems, HTTPS, stronger secret management, authentication/authorization, monitoring, logging and additional network restrictions should be added.

---

## 📊 Current Capabilities

The current version focuses on the core student management workflow:

```text
Create Student
      ↓
React Frontend
      ↓
FastAPI REST API
      ↓
SQLAlchemy
      ↓
MySQL
      ↓
Student Record
```

---

## 🔮 Future Improvements

Potential future enhancements include:

* 🔐 User authentication and authorization
* ✏️ Update student records
* 🗑️ Delete student records
* 🔎 Search and filtering
* 📄 Pagination
* 📊 Student analytics dashboard
* 📱 Improved responsive UI
* 🔒 HTTPS with a domain name
* 🔄 CI/CD pipeline
* 📈 Application monitoring
* 🧪 Automated testing
* ☁️ Production-grade AWS architecture

---

## 🎯 What This Project Demonstrates

This project demonstrates practical experience with:

* Full-stack application development
* REST API development
* Database integration
* ORM-based database operations
* Docker containerization
* Multi-container application architecture
* Docker Compose
* Docker Hub
* AWS EC2 deployment
* Linux server environment
* Git/GitHub workflow
* Environment-based configuration

---

## 👨‍💻 Author

**Agrim Agrawal**

B.Tech — Computer Science & Engineering

### Technologies

```text
Python • FastAPI • React • JavaScript
MySQL • SQLAlchemy • Docker
AWS EC2 • Docker Hub • Git • GitHub
```

---

## ⭐ If You Find This Project Useful

If you found this project interesting, consider giving the repository a ⭐ on GitHub.
