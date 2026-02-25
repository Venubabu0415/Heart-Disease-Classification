# AI-Powered Heart Disease Risk Prediction & Clinical Decision Support Platform

A comprehensive full-stack system for heart disease risk prediction using XGBoost and SMOTE-ENN, featuring multi-portal access for different user roles.

## 🏗️ Architecture

```
React (Frontend) → Node.js + Express (API) → Python ML Service → PostgreSQL
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Python 3.9+
- PostgreSQL 14+

### Installation

1. **Install all dependencies:**
```bash
npm run install:all
```

2. **Set up environment variables:**
- Copy `backend/.env.example` to `backend/.env`
- Copy `frontend/.env.example` to `frontend/.env`

3. **Set up database:**
```bash
npm run setup:db
```

4. **Start services:**

Terminal 1 - Backend:
```bash
npm run dev:backend
```

Terminal 2 - Frontend:
```bash
npm run dev:frontend
```

Terminal 3 - ML Service:
```bash
cd ml-service && python app.py
```

## 📁 Project Structure

```
├── backend/          # Node.js + Express API
├── frontend/         # React + Vite application
├── ml-service/       # Python ML service
└── database/         # Database migrations and seeds
```

## 🔐 Portals

1. **Admin Portal** - Dataset management, model training, metrics
2. **Doctor Portal** - Patient data entry, risk prediction
3. **Patient Portal** - Personal health dashboard
4. **Data Scientist Portal** - Dataset exploration, feature analysis

## 🧪 ML Pipeline

1. Data Cleaning & Preprocessing
2. Feature Selection (Information Gain)
3. Data Balancing (SMOTE-ENN)
4. Model Training (XGBoost)
5. Cross Validation
6. SHAP Explainability

## 📊 Tech Stack

- **Frontend**: React, Vite, Tailwind CSS, Recharts
- **Backend**: Node.js, Express, JWT, Sequelize
- **Database**: PostgreSQL
- **ML**: Python, XGBoost, Scikit-learn, SMOTE-ENN, SHAP

