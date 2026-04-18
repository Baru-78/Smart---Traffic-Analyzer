# 🚦 Smart Traffic Analyzer

A comprehensive web application for analyzing and monitoring website traffic with AI-powered insights, anomaly detection, and forecasting capabilities.

![Project Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)
![React](https://img.shields.io/badge/React-19.2.0-61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-Express-339933)
![Python](https://img.shields.io/badge/Python-Flask-3776AB)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
- [Running the Application](#running-the-application)
  - [Frontend](#frontend)
  - [Backend](#backend)
  - [AI Service](#ai-service)
- [API Documentation](#api-documentation)
- [AI/ML Models](#aiml-models)
- [Contributing](#contributing)
- [License](#license)

---

## 📖 Overview

**Smart Traffic Analyzer** is a full-stack web application that provides real-time website traffic monitoring, analytics, and AI-powered predictions. It enables website owners to:

- Track visitor traffic in real-time
- Visualize traffic patterns with interactive charts
- Detect anomalies in traffic data
- Forecast future traffic trends
- Manage multiple websites from a single dashboard

---

## ✨ Features

### 🔐 Authentication & Authorization
- User registration and login
- JWT-based authentication
- Protected routes for secure access

### 📊 Traffic Analytics
- Real-time visitor tracking
- Traffic pattern visualization
- Historical data analysis
- Multiple metrics tracking (page views, unique visitors, sessions)

### 🤖 AI-Powered Insights
- **Anomaly Detection**: Identify unusual traffic patterns
- **Traffic Forecasting**: Predict future traffic trends
- **Classification**: Categorize traffic types

### 🌐 Website Management
- Add and manage multiple websites
- Track individual website performance
- Unique tracking scripts per website

### 📈 Dashboard
- Interactive charts using Chart.js
- Traffic overview widgets
- Recent activity feed

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        Frontend (React + Vite)                  │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐           │
│  │  Home   │  │ Login   │  │Dashboard│  │  Add    │           │
│  │  Page   │  │ Register│  │         │  │Website  │           │
│  └────┬────┘  └────┬────┘  └────┬────┘  └────┬────┘           │
└───────┼────────────┼────────────┼────────────┼─────────────────┘
        │            │            │            │
        └────────────┴─────┬──────┴────────────┘
                           │
                    ┌──────▼──────┐
                    │  REST API   │
                    │ (Express.js)│
                    └──────┬──────┘
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
┌──────▼──────┐    ┌──────▼──────┐    ┌──────▼──────┐
│  MongoDB    │    │  AI Service │    │  Tracker    │
│  Database   │    │  (Flask)    │    │  (Client)   │
└─────────────┘    └─────────────┘    └─────────────┘
```

---

## 🛠️ Tech Stack

### Frontend
| Technology | Version | Purpose |
|------------|---------|---------|
| React | 19.2.0 | UI Framework |
| Vite | 7.3.1 | Build Tool |
| React Router DOM | 7.13.0 | Routing |
| Chart.js | 4.5.1 | Data Visualization |
| React Chart.js | 5.3.1 | React Chart.js Wrapper |
| Axios | 1.13.5 | HTTP Client |
| ESLint | 9.39.1 | Code Linting |

### Backend
| Technology | Version | Purpose |
|------------|---------|---------|
| Node.js | LTS | Runtime Environment |
| Express | 4.18.2 | Web Framework |
| MongoDB | - | Database |
| Mongoose | 7.6.3 | ODM |
| JWT | 9.0.2 | Authentication |
| bcrypt | 5.1.1 | Password Hashing |
| CORS | 2.8.5 | Cross-Origin Support |
| dotenv | 16.3.1 | Environment Variables |

### AI/ML Service
| Technology | Version | Purpose |
|------------|---------|---------|
| Python | 3.x | ML Runtime |
| Flask | 3.0.0 | Web Framework |
| scikit-learn | 1.3.2 | Machine Learning |
| pandas | 2.1.3 | Data Processing |
| numpy | 1.26.2 | Numerical Computing |
| statsmodels | 0.14.0 | Statistical Modeling |

---

## 📂 Project Structure

```
Phase1Intelli/
├── src/                          # React Source Code
│   ├── components/               # Reusable Components
│   │   ├── Navbar.jsx            # Navigation Bar
│   │   ├── ProtectedRoute.jsx    # Route Protection
│   │   └── TrafficChart.jsx      # Chart Component
│   ├── pages/                    # Page Components
│   │   ├── Home.jsx              # Landing Page
│   │   ├── Login.jsx             # Login Page
│   │   ├── Register.jsx          # Registration Page
│   │   ├── Dashboard.jsx         # Main Dashboard
│   │   └── AddWebsite.jsx        # Add Website Form
│   ├── services/                 # API Services
│   │   └── api.js                # Axios Instance
│   ├── App.jsx                   # Root Component
│   ├── main.jsx                  # Entry Point
│   └── index.css                 # Global Styles
├── server/                       # Backend Server
│   ├── config/
│   │   └── db.js                 # MongoDB Connection
│   ├── controllers/
│   │   ├── authController.js     # Auth Logic
│   │   ├── websiteController.js  # Website Management
│   │   └── analyticsController.js# Analytics Logic
│   ├── middleware/
│   │   └── authMiddleware.js     # JWT Verification
│   ├── models/
│   │   ├── User.js               # User Model
│   │   ├── Website.js            # Website Model
│   │   └── TrafficLog.js         # Traffic Data Model
│   ├── routes/
│   │   ├── authRoutes.js         # Auth Endpoints
│   │   ├── websiteRoutes.js      # Website Endpoints
│   │   ├── trackRoutes.js        # Tracking Endpoints
│   │   └── analyticsRoutes.js    # Analytics Endpoints
│   ├── server.js                 # Server Entry Point
│   └── tracker.js                # Traffic Tracker
├── ai-service/                   # AI/ML Service
│   ├── app.py                    # Flask Application
│   ├── generate_dataset.py       # Dataset Generator
│   ├── train_models.py           # Model Training Script
│   ├── requirements.txt          # Python Dependencies
│   └── traffic_dataset.csv       # Training Data
├── index.html                    # Main HTML Entry
├── simulator.html                # Traffic Simulator
├── test-site.html                # Test Website
├── package.json                  # Frontend Dependencies
├── vite.config.js                # Vite Configuration
└── eslint.config.js              # ESLint Configuration
```

---

## 🚀 Getting Started

### Prerequisites

Before running the application, ensure you have the following installed:

| Requirement | Version | Installation |
|-------------|---------|--------------|
| Node.js | 18+ | [Download](https://nodejs.org/) |
| npm | 9+ | Comes with Node.js |
| Python | 3.8+ | [Download](https://www.python.org/) |
| MongoDB | 6.0+ | [Download](https://www.mongodb.com/) |

### Installation

#### 1. Clone the Repository
```bash
git clone https://github.com/Baru-78/Smart---Traffic-Analyzer.git
cd Smart---Traffic-Analyzer/Phase1Intelli
```

#### 2. Install Frontend Dependencies
```bash
npm install
```

#### 3. Install Backend Dependencies
```bash
cd server
npm install
```

#### 4. Install AI Service Dependencies
```bash
cd ../ai-service
pip install -r requirements.txt
```

### Configuration

#### 1. Backend Environment Variables
Create a `.env` file in the `server/` directory:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# MongoDB Connection
MONGODB_URI=mongodb://localhost:27017/intelli-traffic

# JWT Configuration
JWT_SECRET=your-super-secret-key-change-in-production

# AI Service URL
AI_SERVICE_URL=http://localhost:5001
```

#### 2. Frontend API Configuration
The frontend is pre-configured to connect to `http://localhost:5000`. If your backend runs on a different port, update the API base URL in `src/services/api.js`:

```javascript
// src/services/api.js
const API = axios.create({
  baseURL: 'http://localhost:5000/api', // Change port if needed
  // ...
});
```

---

## ▶️ Running the Application

### Option 1: Run All Services Separately

#### Start MongoDB
```bash
# Start MongoDB locally (default port 27017)
mongod
```

#### Start Backend Server
```bash
cd Phase1Intelli/server
npm run dev
# Server runs on http://localhost:5000
```

#### Start AI Service
```bash
cd Phase1Intelli/ai-service
python app.py
# AI service runs on http://localhost:5001
```

#### Start Frontend
```bash
cd Phase1Intelli
npm run dev
# Frontend runs on http://localhost:5173
```

### Option 2: Using the Traffic Simulator

For testing purposes, use the included simulator:

1. Start all services as above
2. Open `simulator.html` in your browser
3. Enter your website's tracking ID
4. Configure traffic parameters
5. Start generating simulated traffic

---

## 📚 API Documentation

### Authentication Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/auth/register` | Register new user | No |
| POST | `/api/auth/login` | Login user | No |
| GET | `/api/auth/me` | Get current user | Yes |

### Website Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/websites` | Get all websites | Yes |
| POST | `/api/websites` | Add new website | Yes |
| GET | `/api/websites/:id` | Get website details | Yes |
| DELETE | `/api/websites/:id` | Delete website | Yes |

### Tracking Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/track/event` | Track event | No |
| GET | `/api/track/:websiteId` | Get tracked data | Yes |

### Analytics Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/analytics/:websiteId` | Get analytics | Yes |
| GET | `/api/analytics/:websiteId/forecast` | Get traffic forecast | Yes |
| GET | `/api/analytics/:websiteId/anomalies` | Get anomalies | Yes |

---

## 🤖 AI/ML Models

The AI service provides three main prediction models:

### 1. Traffic Forecasting Model
- **Algorithm**: ARIMA (AutoRegressive Integrated Moving Average)
- **Purpose**: Predict future traffic trends
- **Input**: Historical traffic data
- **Output**: Traffic predictions for next N days

### 2. Anomaly Detection Model
- **Algorithm**: Isolation Forest
- **Purpose**: Detect unusual traffic patterns
- **Input**: Traffic features (visitors, page views, session duration)
- **Output**: Anomaly scores and labels

### 3. Traffic Classification Model
- **Algorithm**: Random Forest
- **Purpose**: Classify traffic types
- **Input**: Traffic patterns and user behavior
- **Output**: Traffic category (normal, bot, suspicious)

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** - see the LICENSE file for details.

---

## 🔗 Related Links

- [GitHub Repository](https://github.com/Baru-78/Smart---Traffic-Analyzer)
- [React Documentation](https://react.dev/)
- [Express Documentation](https://expressjs.com/)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [scikit-learn Documentation](https://scikit-learn.org/)

---

**Made with ❤️ by Team IntelliTraffic**
- **`TrafficChart.jsx`**: Uses `chart.js` and `react-chartjs-2` to render a line graph of website visits over time.

### Pages
- **`Home.jsx`**: The first page users see—a clean landing page introducing the service.
- **`Login.jsx` & `Register.jsx`**: Handle user authentication. On successful login, the JWT is stored in `localStorage`.
- **`Dashboard.jsx`**: Fetches and displays analytics data (total visits and hourly trends) for a selected website.
- **`AddWebsite.jsx`**: Allows users to input their website name and domain. It generates a unique `websiteId` and provides a `<script>` tag for tracking.

### Services
- **`api.js`**: Centralized Axios configuration. It automatically attaches the JWT from `localStorage` to every request header using an interceptor.

## 🔄 User Flow: Getting Started

Here is the typical path a new user takes:

1.  **Discovery**: User visits the **Home** page and clicks "Get Started".
2.  **Registration**: User fills out the **Register** form (Name, Email, Password).
3.  **Authentication**: User logs in via the **Login** page. A secure token is saved to their browser.
4.  **Onboarding**: User navigates to **Add Website**, enters their domain (e.g., `example.com`), and receives a tracking script.
5.  **Integration**: User copies the generated `<script>` tag into their website's code.
6.  **Monitoring**: Once visitors hit their site, the user can visit the **Dashboard** to see real-time charts of their traffic.

## 🛠️ Tech Stack
- **React (Vite)**
- **React Router DOM** (Routing)
- **Axios** (API requests)
- **Chart.js** (Data visualization)
- **CSS** (Custom sky-blue theme)
