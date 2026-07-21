# SkillBridge

> AI-powered Skill Gap Analyzer & Personalized Learning Roadmap Generator

## 📖 Overview

SkillBridge is an AI-powered web application that helps job seekers identify the exact skills they should learn for a target software engineering role.

Instead of providing generic learning roadmaps, SkillBridge compares a user's current skills (resume or pasted background) against a specific job description and generates a personalized, prioritized learning roadmap using Generative AI.

Users can save multiple roadmaps, revisit them later, and track their learning progress over time.

---

## ✨ Features

### 🔐 Authentication

- User Registration
- User Login
- JWT Authentication
- Protected Routes
- Password Hashing using bcrypt

### 📄 Resume Input

- Paste resume/skills
- Upload PDF Resume
- Automatic PDF Text Extraction
- Editable extracted text

### 💼 Job Description Analysis

- Paste target job description
- Input validation
- AI-powered skill comparison

### 🤖 AI Skill Gap Analysis

Generates:

- ✅ Existing Skills
- ❌ Missing Skills
- 📈 Prioritized Learning Order

### 🗺 Personalized Learning Roadmap

For every missing skill, the application generates:

- Priority
- Description
- Suggested learning resource type
- Progress status

### 📊 Dashboard

Users can:

- Save multiple roadmaps
- View previous analyses
- Delete roadmaps
- Track completion percentage

### 📈 Progress Tracking

Each roadmap supports:

- Not Started
- In Progress
- Done

Completion percentage updates automatically.

---

# 🏗 Tech Stack

## Frontend

- React
- Vite
- React Router
- Tailwind CSS

## Backend

- Node.js
- Express.js

## Database

- MongoDB Atlas

## Authentication

- JWT
- bcrypt

## AI

- Anthropic Claude API

## Deployment

- Render
- MongoDB Atlas

---

# 📂 Project Structure

```
SkillBridge
│
├── client
│   ├── src
│   ├── components
│   ├── pages
│   ├── hooks
│   └── services
│
├── server
│   ├── controllers
│   ├── routes
│   ├── middleware
│   ├── models
│   ├── services
│   ├── utils
│   └── config
│
├── README.md
└── package.json
```

---

# 🚀 User Flow

```
Signup/Login
      │
      ▼
Upload Resume
or
Paste Resume
      │
      ▼
Paste Job Description
      │
      ▼
Generate AI Analysis
      │
      ▼
Review Skill Gap
      │
      ▼
Generate Learning Roadmap
      │
      ▼
Save Roadmap
      │
      ▼
Track Progress
```

---

# 🧠 How It Works

1. User creates an account.
2. Uploads a resume or pastes resume text.
3. Pastes a target job description.
4. Backend sends both inputs to the AI model.
5. AI compares the resume with the job description.
6. Returns:
   - Matched Skills
   - Missing Skills
   - Priority Order
   - Personalized Learning Roadmap
7. User saves the roadmap.
8. Progress is tracked from the dashboard.

---

# 📊 Data Model

## User

```text
name
email
hashedPassword
createdAt
```

## Roadmap

```text
userId
label
targetRole
targetCompany
resumeText
jobDescription
matchedSkills[]
gapSkills[]
completionPercentage
createdAt
updatedAt
```

---

# 🔒 Security

- Password hashing using bcrypt
- JWT Authentication
- Protected API routes
- Environment variables for secrets
- API keys never committed to source control

---

# ⚡ Non-Functional Requirements

- Responsive Design
- Modern UI
- Secure Authentication
- Fast AI Processing
- Clean Architecture
- Maintainable Codebase

---

# 🛣 Roadmap

### Version 1.0

- Authentication
- Resume Upload
- AI Analysis
- Learning Roadmap
- Dashboard
- Progress Tracking
- Multi-roadmap Support

### Future Enhancements

- Resume Tailoring
- Multiple Job Comparison
- Course Recommendations
- Notifications
- Premium Features
- Mobile Application

---

# 📸 Screenshots

Add screenshots here after implementation.

Example:

```
/screenshots

login.png
dashboard.png
analysis.png
roadmap.png
```

---

# 🛠 Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/skillbridge.git
```

## Install Dependencies

### Backend

```bash
cd server
npm install
```

### Frontend

```bash
cd client
npm install
```

---

## Environment Variables

Create a `.env` file in the server directory.

```env
PORT=5000

MONGODB_URI=your_mongodb_uri

JWT_SECRET=your_jwt_secret

CLAUDE_API_KEY=your_anthropic_api_key
```

---

## Run Backend

```bash
npm run dev
```

---

## Run Frontend

```bash
npm run dev
```

---

# 🌐 Deployment

Frontend

- Render

Backend

- Render

Database

- MongoDB Atlas

---

# 🎯 Project Goals

- Personalized AI-powered skill-gap analysis
- Save multiple learning plans
- Track learning progress
- Portfolio-ready full-stack application
- Demonstrate GenAI integration in MERN

---

# 📅 Development Timeline

| Day | Task |
|------|------|
| 1 | Requirements & Design |
| 2 | Project Setup |
| 3 | Authentication |
| 4 | AI Integration |
| 5 | Frontend Development |
| 6 | Analysis Flow |
| 7 | Dashboard |
| 8 | Testing |
| 9 | Deployment |
| 10 | Final Documentation |

---

# 🤝 Contributing

Contributions, suggestions, and feature requests are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push to your branch.
5. Open a Pull Request.

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Rudresh Srivastava**

- GitHub: https://github.com/srivastavarudresh552-cmyk
- LinkedIn: https://www.linkedin.com/

---

⭐ If you found this project useful, consider giving it a star!
