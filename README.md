🚀 Three-Tier Next.js Application with Docker

This project demonstrates a three-tier architecture using:

Frontend (Presentation Layer): Next.js

Backend (Application Layer): Express.js + Node.js

Database (Data Layer): PostgreSQL with initialization script

All components are containerized using Docker Compose.

📂 Project Structure
task3/
│── docker-compose.yml
│
│── frontend/                 # Next.js frontend
│   │── app/
│   │   │── page.tsx          # Home page
│   │   │── login/page.tsx    # Login page
│   │   │── employees/page.tsx# Employees page (Add + List)
│   │── public/               # Static files
│   │── package.json
│   │── Dockerfile
│   │── .env.local
│
│── backend/                  # Express backend
│   │── server.js             # Main Express server
│   │── db.js                 # PostgreSQL connection
│   │── package.json
│   │── Dockerfile
│
│── database/                 # Database layer
│   │── init.sql              # Tables + seed data
│
└── README.md

⚙️ Setup & Installation
1️⃣ Clone the repo
git clone https://github.com/<your-username>/three-tier-nextjs-app.git
cd three-tier-nextjs-app

2️⃣ Run with Docker Compose
docker-compose up --build


This will start:

Frontend → http://localhost:3000

Backend → http://localhost:3001

Database (Postgres) → port 5432

🗄️ Database Initialization

The database is automatically seeded using database/init.sql:

users table → with default user admin/admin

employees table → with sample employees

🔑 API Endpoints (Backend)
Method	Endpoint	Description
GET	/api/health	Check backend health
GET	/api/database-status	Test DB connection
POST	/api/login	User login ({ username, password })
POST	/api/employees	Add employee ({ name, email, position })
GET	/api/employees	Get all employees
🖥️ Frontend Pages

/login → Login page (authenticates via backend)

/employees → Add + List employees

/ → Home page

🐳 Docker Services
services:
  frontend: Next.js app on port 3000
  backend: Express.js API on port 3001
  database: PostgreSQL with seed script

✅ How to Use

Start containers:

docker-compose up --build


Open browser:

Frontend → http://localhost:3000

Backend API → http://localhost:3001

Login with:

username: admin
password: admin

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/08438dd7-e86a-4f0f-8003-828616d3d061" />


