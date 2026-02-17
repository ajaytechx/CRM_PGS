# 🏢 PGS CRM - Overseas Recruitment Management System

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.0-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Production-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![SQLite](https://img.shields.io/badge/SQLite-Development-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![Render](https://img.shields.io/badge/Render-Deployed-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://render.com)

---

## 🎯 What I Built

A **complete CRM system** for my overseas recruitment agency (**Pavishna Global Services**) to manage candidates applying for jobs in **Gulf countries, Maldives, and USA**.

### The Problem I Solved
- Managing 2000+ candidates manually was chaotic
- Tracking visa status, medical reports, payments across Excel sheets
- No centralized system for 30+ employees to access

### My Solution
Built a **full-stack web application** from scratch that handles the entire recruitment pipeline.

---

## 🛠️ Tech Stack I Used

| Layer | Technology |
|-------|------------|
| **Backend** | Python, Flask |
| **Database** | SQLite (local), PostgreSQL (production) |
| **Frontend** | HTML, CSS, JavaScript |
| **Deployment** | Render.com |
| **Authentication** | Session-based with SHA-256 password hashing |

---

## ✨ Features I Implemented

### 👥 Client Management
- Add, edit, delete, search candidates
- Store 50+ fields per candidate (personal info, documents, status)
- Real-time search and filtering

### 📋 Complete Recruitment Pipeline Tracking

| Stage | What I Track |
|-------|--------------|
| **Registration** | Name, phone, district, job role, country |
| **Passport** | Number, submit date, fee, payment status |
| **Interview** | Date, time, location, status, remarks |
| **Offer Letter** | Status, date, reference, employer, salary |
| **Medical** | Status, date, report number |
| **MOFA** | Status, number, date |
| **VFS** | Status, appointment date, reference |
| **Takamual** | Status, date, certificate number |
| **Visa** | Status, number, expiry date |
| **Agreement** | Process status, date, number, signature |
| **Payment** | Advance, full payment, modes, dates |
| **Flight** | Flying date, flight details, ticket status |

### 💰 Payment Tracking
- Advance payment tracking
- Full payment tracking  
- Passport fee tracking (when agency handles)
- Payment mode (Cash, UPI, Bank Transfer)
- Payment reference numbers

### 📊 Dashboard Analytics
- Total clients count
- Interview pending/passed counts
- Visa approved/processing counts
- Ready to fly count
- **Total revenue calculation** (advance + full + passport fees)

### 🔐 Security Features
- Admin login with hashed passwords (SHA-256)
- Session-based authentication
- Login required decorator for protected routes
- Change credentials functionality

### 🌐 Dual Database Support
- **SQLite** for local development (no setup needed)
- **PostgreSQL** for production (Render deployment)
- Auto-detects environment and switches database

---

## 📁 Project Structure

```
PGS_CRM/
├── app.py                 # Main Flask application (730+ lines)
├── requirements.txt       # Python dependencies
├── Procfile              # Render deployment config
├── render.yaml           # Render blueprint
├── .gitignore            # Git ignore rules
├── README.md             # This file
│
├── templates/
│   ├── login.html        # Admin login page
│   └── dashboard.html    # Main CRM dashboard (full UI)
│
└── static/
    └── images/           # Logo and assets
```

---

## 🔌 API Endpoints I Created

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/login` | Login page |
| POST | `/login` | Authenticate user |
| GET | `/logout` | Logout user |
| GET | `/api/admin/credentials` | Get admin info |
| POST | `/api/admin/change-credentials` | Update credentials |

### Client CRUD
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/clients` | Get all clients |
| POST | `/api/clients` | Add new client |
| GET | `/api/clients/<id>` | Get single client |
| PUT | `/api/clients/<id>` | Update client |
| DELETE | `/api/clients/<id>` | Delete client |
| DELETE | `/api/clients/clear` | Delete all clients |

### Dashboard
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/stats` | Get dashboard statistics |
| GET | `/health` | Health check for Render |

---

## 🚀 How to Run Locally

```bash
# Clone
git clone https://github.com/YOUR_USERNAME/pgs-crm.git
cd pgs-crm

# Create virtual environment
python -m venv venv

# Activate (Windows)
.\venv\Scripts\Activate.ps1

# Activate (Linux/Mac)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run
python app.py
```

Open: `http://localhost:5001`

**Default Login:** `admin` / `admin123`

---

## ☁️ Production Deployment

Deployed on **Render.com** with:
- PostgreSQL database
- Auto-deploy from GitHub
- Environment variables for secrets

---

## 📊 Database Schema

### admin_users
```sql
id, username, password, created_at, updated_at
```

### clients (50+ columns)
```sql
id, name, phone, district, job_role, country,
passport_no, passport_submit_date, passport_fee, ...
interview_date, interview_status, ...
medical_status, medical_date, ...
mofa_status, mofa_number, ...
visa_status, visa_number, visa_expiry_date, ...
advance_payment, full_payment, ...
flying_date, flight_details, ticket_status,
remarks, created_at, updated_at
```

---

## 🔒 Security Notes

- Passwords hashed with SHA-256
- Session-based authentication
- SQL injection prevented with parameterized queries
- CORS enabled for API access
- Environment variables for sensitive config

---

## 📝 What I Learned

- Building REST APIs with Flask
- Database design for real-world applications
- Handling dual database environments
- Deploying Python apps to cloud (Render)
- Authentication and session management
- Working with PostgreSQL and SQLite

---

## 👨‍💻 Author

**Pavishna Global Services**  
Overseas Recruitment Agency  
Coimbatore / Thoothukudi, Tamil Nadu, India

[![Website](https://img.shields.io/badge/Website-pavishnagroups.com-blue?style=flat-square)](https://pavishnagroups.com)

---

**Made with ❤️ in Tamil Nadu, India**
