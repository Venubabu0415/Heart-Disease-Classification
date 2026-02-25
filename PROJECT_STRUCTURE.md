# Project Structure

```
AIML_4/
├── backend/                    # Node.js + Express API
│   ├── config/
│   │   └── database.js         # Sequelize configuration
│   ├── middleware/
│   │   ├── auth.js            # JWT authentication
│   │   └── errorHandler.js    # Error handling
│   ├── models/                 # Database models
│   │   ├── User.js
│   │   ├── Patient.js
│   │   ├── ClinicalResult.js
│   │   ├── Prediction.js
│   │   ├── MLMetric.js
│   │   └── index.js
│   ├── routes/                 # API routes
│   │   ├── auth.js
│   │   ├── predictions.js
│   │   ├── dataset.js
│   │   ├── ml.js
│   │   └── users.js
│   ├── scripts/
│   │   ├── migrate.js         # Database migration
│   │   └── seed.js            # Seed initial data
│   ├── server.js              # Express server
│   ├── package.json
│   └── env.example
│
├── frontend/                   # React + Vite application
│   ├── src/
│   │   ├── components/
│   │   │   ├── Layout.jsx
│   │   │   └── PrivateRoute.jsx
│   │   ├── contexts/
│   │   │   └── AuthContext.jsx
│   │   ├── pages/
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── admin/         # Admin Portal
│   │   │   │   ├── AdminDashboard.jsx
│   │   │   │   ├── AdminHome.jsx
│   │   │   │   ├── DatasetManagement.jsx
│   │   │   │   ├── ModelTraining.jsx
│   │   │   │   ├── ModelMetrics.jsx
│   │   │   │   └── UserManagement.jsx
│   │   │   ├── doctor/        # Doctor Portal
│   │   │   │   ├── DoctorDashboard.jsx
│   │   │   │   ├── DoctorHome.jsx
│   │   │   │   ├── PatientPrediction.jsx
│   │   │   │   └── PredictionHistory.jsx
│   │   │   ├── patient/       # Patient Portal
│   │   │   │   ├── PatientDashboard.jsx
│   │   │   │   ├── PatientHome.jsx
│   │   │   │   └── MyPredictions.jsx
│   │   │   └── datascientist/ # Data Scientist Portal
│   │   │       ├── DataScientistDashboard.jsx
│   │   │       ├── DataScientistHome.jsx
│   │   │       ├── DatasetExplorer.jsx
│   │   │       ├── FeatureAnalysis.jsx
│   │   │       └── ModelComparison.jsx
│   │   ├── utils/
│   │   │   └── api.js         # Axios configuration
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── ml-service/                 # Python ML service
│   ├── data/                   # Dataset storage
│   ├── models/                 # Trained models
│   ├── app.py                 # Flask application
│   ├── requirements.txt
│   └── generate_sample_data.py
│
├── package.json               # Root package.json
├── README.md
├── SETUP.md
└── .gitignore
```

## Key Features by Portal

### 1. Admin Portal (`/admin`)
- Dataset upload and management
- Model training trigger
- Model metrics visualization
- User management
- Algorithm comparison

### 2. Doctor Portal (`/doctor`)
- Patient data entry form
- Real-time risk prediction
- SHAP explainability (top risk factors)
- Prediction history
- Risk level visualization

### 3. Patient Portal (`/patient`)
- Personal health dashboard
- Risk score visualization
- Top risk factors display
- Lifestyle recommendations
- Prediction history with trends

### 4. Data Scientist Portal (`/datascientist`)
- Dataset explorer with statistics
- Feature correlation analysis
- Model version comparison
- Performance metrics over time
- Feature importance charts

## Database Schema

### Tables
1. **users** - User accounts with roles
2. **patients** - Patient demographic and basic health data
3. **clinical_results** - Detailed clinical test results
4. **predictions** - Risk predictions with SHAP values
5. **ml_metrics** - Model training metrics and performance

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user

### Predictions
- `POST /api/predictions/heart-risk` - Create prediction
- `GET /api/predictions/history` - Get prediction history
- `GET /api/predictions/:id` - Get single prediction

### Dataset
- `GET /api/dataset/summary` - Dataset statistics
- `GET /api/dataset/features` - Feature statistics
- `POST /api/dataset/upload` - Upload dataset
- `GET /api/dataset/correlation` - Feature correlation

### ML
- `POST /api/ml/train` - Train model
- `GET /api/ml/metrics` - Get metrics
- `GET /api/ml/metrics/latest` - Latest metrics
- `GET /api/ml/compare` - Compare models

### Users
- `GET /api/users` - List users (admin)
- `GET /api/users/:id` - Get user (admin)
- `PUT /api/users/:id` - Update user (admin)

