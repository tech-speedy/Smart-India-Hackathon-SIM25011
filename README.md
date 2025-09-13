

---

```markdown
# 📚 Smart Attendance & Productivity System

A full-stack web application that automates student attendance using QR code scanning, provides real-time tracking for teachers/admins, and suggests personalized activities for students during free periods.  

Built with **Node.js + Express + Prisma + PostgreSQL (Backend)** and **React + Vite (Frontend)**.

---

## 🚀 Features

- **Authentication**: Secure signup & login with JWT (students, teachers, admins).
- **Attendance**: 
  - Teacher generates QR code for a session.
  - Students scan QR to mark attendance.
  - Face-recognition / Bluetooth/Wi-Fi proximity support can be added later.
- **Real-time Dashboard**:
  - Shows live attendance counts and session updates.
  - Interactive charts (Recharts) for admins.
  - Export attendance reports in CSV format.
- **Student Productivity**:
  - Personalized suggestions during free periods (e.g., revision, coding, career prep).
  - Daily planner with timetable + free slot guidance.
- **Admin Tools**:
  - Daily summary reports.
  - Session-wise student lists.
  - CSV export for records.

---

## 🛠️ Tech Stack

**Backend**
- Node.js + Express  
- Prisma ORM (PostgreSQL)  
- JSON Web Tokens (JWT)  
- Socket.IO (real-time updates)  

**Frontend**
- React (Vite)  
- Axios (API calls)  
- Recharts (charts)  
- Socket.IO Client  

**Other**
- QR Code generation (`qrcode` npm package)  
- CSV export (`json2csv`)  

---

## 📂 Project Structure

```
```
/backend
├── index.js              # Express app entry
├── prisma/
│   ├── schema.prisma     # Database schema
│   └── migrations/       # Migration history
├── routes/
│   ├── auth.js           # Signup & login
│   ├── attendance.js     # Attendance logic
│   ├── sessions.js       # Session mgmt
│   ├── reports.js        # Admin reports
└── Dockerfile            # Deployment

/web
├── src/
│   ├── pages/
│   │   ├── Signup.jsx
│   │   ├── Login.jsx
│   │   ├── Dashboard.jsx
│   │   └── AdminDashboard.jsx
│   ├── components/       # Reusable UI
│   └── main.jsx          # React entry
└── vite.config.js

````

---

## ⚙️ Setup Instructions

### 1. Clone the repo
```bash
git clone https://github.com/tech-speedy/Smart-India-Hackathon-SIM25011.git
cd Smart-India-Hackathon-SIM25011
````

### 2. Backend setup

```bash
cd backend
npm install
```

* Create a `.env` file:

```env
DATABASE_URL="postgresql://user:password@localhost:5432/attendance_db"
SECRET="your_jwt_secret"
ATTENDANCE_SECRET="your_attendance_secret"
```

* Run migrations:

```bash
npx prisma migrate dev --name init
```

* Start backend:

```bash
node index.js
```

Backend runs at **[http://localhost:5000](http://localhost:5000)**

---

### 3. Frontend setup

```bash
cd ../web
npm install
npm run dev
```

Frontend runs at **[http://localhost:5173](http://localhost:5173)**

---

## 🔑 Testing APIs (Optional with Postman / Thunder Client)

* `POST /auth/signup` → Register user
* `POST /auth/login` → Get JWT
* `POST /attendance/generate-qr` → Teacher generates QR for session
* `POST /attendance/mark` → Student marks attendance
* `GET /reports/daily-summary?date=YYYY-MM-DD` → Admin daily report
* `GET /reports/export?type=session&sessionId=1` → Download CSV

---

## 🐳 Deployment (Optional with Docker)

```bash
docker-compose up --build
```

This runs backend + PostgreSQL. Frontend can be deployed on **Vercel/Netlify** with `npm run build`.

---

## 📌 Future Improvements

* Add **face recognition** for attendance.
* AI-powered **personalized study plans**.
* Mobile app version (React Native).
* Role-based access control (RBAC).

---

## 👨‍💻 Contributors

* **Arnab Sarkar** (Developer)
