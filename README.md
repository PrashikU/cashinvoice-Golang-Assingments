# cashinvoice-Golang-Assingments
cashinvoice Golang Assingments
# 🚀 Task M – Full Stack Task Management Application

A production-ready **Task Management System** built using:

- 🖥 **Frontend**: Angular 18  
- ⚙ **Backend**: Go (Gin Framework)  
- 🗄 **Database**: PostgreSQL 16  
- 🔐 **Authentication**: JWT (Role-Based)  
- 🐳 **Containerization**: Docker & Docker Compose  

---

# 📁 Project Structure

```
Task-M/
├── backend/                      # Go REST API
│   ├── main.go
│   ├── db/
│   ├── internal/
│   ├── services/
│   ├── docker-compose.yml
│   ├── Dockerfile
│   └── postman/
│
└── frontend/                     # Angular 18 App
    ├── src/
    ├── public/
    ├── docs/images/
    └── Dockerfile (optional)
```

---

# 🏗 System Architecture

```
Angular Frontend  →  Gin Backend API  →  PostgreSQL
        │                  │                │
        └──────────── Docker Network ───────┘
```

All services can run inside Docker containers using Docker Compose.

---

# ✨ Core Features

## 🔐 Authentication
- User Registration
- Login with JWT
- Token Expiry Control
- Role-based Authorization

## 📝 Task Management
- Create Task
- List Tasks
- Get Task by ID
- Delete Task
- Task Status: `pending`, `in_progress`, `completed`

## 🧱 Architecture
- Clean Architecture Pattern
- Service Layer + Repository Layer
- Middleware for Auth
- Environment-based config
- Dockerized deployment

---

# 🗄 Task Model

```json
{
  "id": "uuid",
  "title": "string",
  "description": "string",
  "status": "pending | in_progress | completed",
  "created_at": "timestamp",
  "updated_at": "timestamp"
}
```

---

# 🔗 API Endpoints

## Public Routes

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/register` | Register user |
| POST | `/login` | Login & receive JWT |
| GET | `/health` | Health check |

## Protected Routes (JWT Required)

| Method | Endpoint |
|--------|----------|
| POST | `/tasks` |
| GET | `/tasks` |
| GET | `/tasks/:id` |
| DELETE | `/tasks/:id` |

---

# 🐳 Docker Support (Important Section)

This project is fully containerized.

## 📦 Services in Docker Compose

- `app` → Go Backend
- `db` → PostgreSQL 16
- (Optional) `frontend` → Angular build container

---

## ▶ Run Full Stack with Docker

From backend root:

```bash
docker-compose up -d --build
```

Check running containers:

```bash
docker ps
```

View logs:

```bash
docker-compose logs -f
```

Stop containers:

```bash
docker-compose down
```

---

## 🔧 Dockerized Architecture Flow

```
Client Browser
      ↓
Angular Container (Optional)
      ↓
Go API Container
      ↓
PostgreSQL Container
```

All containers communicate through Docker internal network.

---

# 🛠 Local Development (Without Docker)

## Backend

```bash
go run main.go
```

## Frontend

```bash
cd frontend
npm install
npm start
```

---

# ⚙ Environment Variables

| Variable | Description |
|----------|------------|
| PORT | Server port |
| DATABASE_URL | PostgreSQL connection |
| JWT_SECRET | JWT signing key |
| JWT_EXPIRY_MINUTES | Token expiration |

---

# 📡 API Usage Example

### Register

```bash
curl -X POST http://localhost:8080/register \
-H "Content-Type: application/json" \
-d '{"email":"user@example.com","username":"user1","password":"secret123"}'
```

### Login

```bash
curl -X POST http://localhost:8080/login \
-H "Content-Type: application/json" \
-d '{"email":"user@example.com","password":"secret123"}'
```

### Create Task

```bash
curl -X POST http://localhost:8080/tasks \
-H "Authorization: Bearer <TOKEN>" \
-H "Content-Type: application/json" \
-d '{"title":"My Task","description":"Task description","status":"pending"}'
```

---

# 🧪 Postman Collection

Import:

```
postman/Task_Management_API.postman_collection.json
```

---

# 🚀 Production Build

Frontend:

```bash
npm run build
```

Backend:

```bash
go build -o app
```

Docker Production:

```bash
docker-compose -f docker-compose.yml up --build -d
```

---

# 💎 Why This Project is Strong

- Full Stack Implementation
- Secure JWT System
- Clean Go Architecture
- Angular 18 Modern UI
- PostgreSQL + sqlc
- Fully Dockerized
- Production Ready Structure
- Interview Ready

---
Demo Images 

<img width="1920" height="1200" alt="Screenshot from 2026-02-16 01-07-19" src="https://github.com/user-attachments/assets/1d436b5f-9a25-440d-b6b5-248218e2b353" />
<img width="1920" height="1200" alt="Screenshot from 2026-02-16 01-08-02" src="https://github.com/user-attachments/assets/78fa190e-02cf-4b35-83cd-0358087d6fbf" />
<img width="1920" height="1200" alt="Screenshot from 2026-02-16 01-08-19" src="https://github.com/user-attachments/assets/33b72f4b-df3e-4169-bc2d-e6ea8aa6ac40" />
<img width="1920" height="1200" alt="Screenshot from 2026-02-16 01-10-17" src="https://github.com/user-attachments/assets/d449a352-5777-4b77-99ba-8d6947a93209" />





---
# 📜 License

MIT

---

# 👨‍💻 Author

Prashik Unawane  
Full Stack Developer (Angular + Go)
