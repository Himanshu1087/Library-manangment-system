# 📚 Library Management System

A full-stack Library Management System built with **React.js**, **Node.js**, **Express.js**, and **MySQL**.

## Features
- 🔐 Separate Admin and Student login portals (JWT Authentication)
- 📚 Admin: Add, Edit, Delete books
- 🔄 Admin: Issue & Return books with live fine calculation
- 👥 Admin: View all registered students
- 📖 Student: Browse available books with search & filter
- 📊 Student: Dashboard showing issued books and fine status
- 💰 Auto fine calculation — ₹2/day after due date

## Tech Stack
| Layer | Technology |
|-------|-----------|
| Frontend | React.js (Vite), React Router, Axios |
| Backend | Node.js, Express.js |
| Database | MySQL (Railway) |
| Auth | JWT + bcryptjs |

---

## Setup Instructions

### Step 1 — Setup MySQL on Railway
1. Go to [railway.app](https://railway.app) → New Project → Add MySQL
2. Click on MySQL → Go to **Variables** tab
3. Copy: `MYSQL_HOST`, `MYSQL_PORT`, `MYSQL_USER`, `MYSQL_PASSWORD`, `MYSQL_DATABASE`
4. Open Railway's **Query tab** → paste contents of `backend/config/schema.sql` → Run

### Step 2 — Backend Setup
```bash
cd backend
npm install
cp .env.example .env
# Fill in your Railway MySQL credentials in .env
npm run dev
```

### Step 3 — Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

### Step 4 — Open in browser
```
http://localhost:5173
```

## Default Admin Login
```
Email: admin@library.com
Password: admin123
```

---

## Project Structure
```
library-management/
├── backend/
│   ├── config/
│   │   ├── db.js          # MySQL connection
│   │   └── schema.sql     # Database setup
│   ├── middleware/
│   │   └── auth.js        # JWT middleware
│   ├── routes/
│   │   ├── auth.js        # Login/Register APIs
│   │   ├── books.js       # Book CRUD APIs
│   │   └── issues.js      # Issue/Return APIs
│   ├── .env.example
│   ├── package.json
│   └── server.js
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Admin/     # Dashboard, Books, IssueReturn, Students
    │   │   ├── Student/   # Dashboard, Books, MyBooks
    │   │   └── Common/    # Sidebar
    │   ├── context/
    │   │   └── AuthContext.jsx
    │   ├── pages/
    │   │   └── Login.jsx
    │   ├── utils/
    │   │   └── api.js
    │   ├── App.jsx
    │   ├── main.jsx
    │   └── index.css
    ├── index.html
    └── package.json
```
