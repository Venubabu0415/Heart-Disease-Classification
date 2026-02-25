# Setup Guide

## Prerequisites

- Node.js 18+ 
- Python 3.9+
- PostgreSQL 14+
- npm or yarn

## Step-by-Step Setup

### 1. Database Setup

```bash
# Create PostgreSQL database
createdb heart_disease_db

# Or using psql:
psql -U postgres
CREATE DATABASE heart_disease_db;
```

### 2. Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Copy environment file
cp env.example .env

# Edit .env file with your database credentials:
# DB_HOST=localhost
# DB_PORT=5432
# DB_NAME=heart_disease_db
# DB_USER=postgres
# DB_PASSWORD=your_password

# Run database migrations (creates tables)
npm run db:migrate

# Seed initial users
npm run db:seed
```

### 3. ML Service Setup

```bash
cd ml-service

# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Generate sample dataset (optional)
python generate_sample_data.py
```

### 4. Frontend Setup

```bash
cd frontend

# Install dependencies
npm install
```

## Running the Application

### Terminal 1: Backend
```bash
cd backend
npm run dev
```
Backend runs on http://localhost:5000

### Terminal 2: ML Service
```bash
cd ml-service
python app.py
```
ML Service runs on http://localhost:8000

### Terminal 3: Frontend
```bash
cd frontend
npm run dev
```
Frontend runs on http://localhost:5173

## Default Login Credentials

After running the seed script:

- **Admin**: admin@heartdisease.com / admin123
- **Doctor**: doctor@heartdisease.com / doctor123
- **Patient**: patient@heartdisease.com / patient123
- **Data Scientist**: scientist@heartdisease.com / scientist123

## First Steps

1. **Login as Admin**
   - Upload a dataset (CSV format)
   - Train the model
   - View metrics

2. **Login as Doctor**
   - Enter patient data
   - Get risk predictions
   - View prediction history

3. **Login as Patient**
   - View your health dashboard
   - See risk assessments
   - Check lifestyle recommendations

4. **Login as Data Scientist**
   - Explore dataset
   - Analyze features
   - Compare model versions

## Dataset Format

The CSV file should have:
- Required features: age, sex, smoke, diabetes, bp, cholesterol, ecg, heart_rate
- Optional features: lvef, hbg, bun, tc, scv_number, asa, nitrate
- Target column: 'target' or 'heart_disease' (0/1 or False/True)

## Troubleshooting

### Database Connection Issues
- Check PostgreSQL is running
- Verify credentials in .env file
- Ensure database exists

### ML Service Issues
- Make sure Python dependencies are installed
- Check if port 8000 is available
- Verify dataset is uploaded before training

### Frontend Issues
- Clear browser cache
- Check API URL in .env
- Verify backend is running

