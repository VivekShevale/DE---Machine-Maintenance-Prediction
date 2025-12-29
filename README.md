# Machine Maintenance Prediction System

A full-stack AI-powered predictive maintenance platform with machine learning models for equipment failure prediction and a modern React dashboard for monitoring and analytics.

## 📋 Table of Contents

- Overview
- Features
- Tech Stack
- Project Structure
- Getting Started
- Backend Setup
- Frontend Setup
- Architecture
- Data Flow
- ML Models
- API Documentation
- Contributing

## 🎯 Overview

This system combines machine learning and real-time monitoring to predict equipment failures before they occur. It leverages historical maintenance data and sensor readings to:
- Predict machine failures with high accuracy
- Schedule preventive maintenance
- Reduce downtime and operational costs
- Provide actionable insights through an intuitive dashboard

## ✨ Features

### Backend (Python/ML)
- **Multiple ML Models**: Logistic Regression, Decision Tree, and more
- **Data Pipeline**: Automated ETL with cleaning, encoding, and scaling
- **Balancing**: Handle imbalanced datasets with multiple strategies
- **Model Persistence**: Save and load trained models
- **Metrics Tracking**: Comprehensive model evaluation
- **Modular Architecture**: Easy to extend with new models and preprocessing

### Frontend (React)
- **Real-time Dashboard**: Live machine health monitoring
- **Sensor Data Visualization**: Interactive charts for sensor readings
- **Predictive Analytics**: AI-powered failure predictions with confidence scores
- **Alerts Management**: Real-time notifications and alert handling
- **Maintenance Tracking**: Historical records and scheduling
- **Reports Generation**: Analytics and performance reports
- **System Settings**: Configuration management
- **Responsive Design**: Works on desktop and tablet devices

## 🛠 Tech Stack

### Backend
- **Language**: Python 3.8+
- **ML Libraries**: Scikit-learn, XGBoost, etc.
- **Data Processing**: Pandas, NumPy
- **Model Serialization**: Joblib
- **Configuration**: YAML/Config files

### Frontend
- **Framework**: React 19.2.0
- **Build Tool**: Vite 5.1+
- **Styling**: Tailwind CSS 4.1+
- **Routing**: React Router DOM 7.11+
- **Visualization**: Recharts 3.6.0
- **Icons**: Lucide React 0.562.0

## 📁 Project Structure

```
DE - Machine Maintenance Prediction/
├── backend/
│   ├── data/
│   │   └── Predictive_Maintenance_dataset.csv    # Training dataset
│   ├── maintenance_ml/
│   │   ├── balancing/                             # Data balancing strategies
│   │   ├── config/                                # Configuration management
│   │   ├── data/                                  # Data loading utilities
│   │   ├── models/                                # ML model factory
│   │   ├── pipeline/                              # Complete ML pipeline
│   │   ├── preprocessing/                         # Data preprocessing
│   │   │   ├── cleaning.py                        # Data cleaning
│   │   │   ├── column_handler.py                  # Column management
│   │   │   ├── encoding.py                        # Categorical encoding
│   │   │   └── scaling.py                         # Feature scaling
│   │   ├── training/                              # Model training
│   │   └── utils/                                 # Utilities (metrics, I/O)
│   ├── notebooks/
│   │   ├── 1_EDA.ipynb                            # Exploratory Data Analysis
│   │   └── 2_Logistic_Regression.ipynb            # Model training notebook
│   └── artifacts/
│       ├── decision_tree_failure_prediction.joblib
│       └── logistic_regression_failure_prediction.joblib
│
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Navbar.jsx
    │   │   └── Sidebar.jsx
    │   ├── pages/
    │   │   ├── Dashboard.jsx
    │   │   ├── SensorData.jsx
    │   │   ├── Predictions.jsx
    │   │   ├── Alerts.jsx
    │   │   ├── MaintenanceHistory.jsx
    │   │   ├── Reports.jsx
    │   │   ├── Settings.jsx
    │   │   ├── MachineDetails.jsx
    │   │   └── Login.jsx
    │   ├── App.jsx
    │   ├── main.jsx
    │   └── index.css
    ├── package.json
    ├── vite.config.js
    └── index.html
```

## 🚀 Getting Started

### Prerequisites

- **Python**: 3.8 or higher
- **Node.js**: v16 or higher
- **npm**: v8 or higher
- **Git**: For version control

### Quick Start

1. **Clone the repository**
```bash
cd "DE - Machine Maintenance Prediction"
```

2. **Setup Backend** (see Backend Setup)
3. **Setup Frontend** (see Frontend Setup)

## 🐍 Backend Setup

### Installation

1. **Navigate to backend directory**
```bash
cd backend
```

2. **Create virtual environment**
```bash
python -m venv venv
```

3. **Activate virtual environment**
```bash
# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

4. **Install dependencies**
```bash
pip install -r requirements.txt
```

### Running the Backend

#### Train Models
```bash
python -m maintenance_ml.training.trainer
```

#### Run Jupyter Notebooks
```bash
jupyter notebook notebooks/
```

#### Model Predictions
```bash
python -c "from maintenance_ml.models import ModelFactory; model = ModelFactory.load('logistic_regression'); predictions = model.predict(data)"
```

### Backend Project Structure Details

**`maintenance_ml/config/`**
- Centralized configuration for paths, model parameters, and thresholds

**`maintenance_ml/data/`**
- `data_loader.py`: Load and parse CSV datasets

**`maintenance_ml/preprocessing/`**
- `cleaning.py`: Remove duplicates, handle missing values
- `encoding.py`: Convert categorical features
- `scaling.py`: Normalize numerical features
- `column_handler.py`: Feature selection and management

**`maintenance_ml/balancing/`**
- Handle imbalanced datasets (SMOTE, undersampling, etc.)

**`maintenance_ml/models/`**
- `model_factory.py`: Factory pattern for model creation and management

**`maintenance_ml/pipeline/`**
- `build_pipeline.py`: Complete ML pipeline orchestration

**`maintenance_ml/training/`**
- `trainer.py`: Model training and validation logic

**`maintenance_ml/utils/`**
- `metrices.py`: Performance metrics (accuracy, precision, recall, F1)
- `model_io.py`: Save and load models

## ⚛️ Frontend Setup

### Installation

1. **Navigate to frontend directory**
```bash
cd frontend
```

2. **Install dependencies**
```bash
npm install
```

### Development

```bash
# Start development server with HMR
npm run dev
```

Server runs at `http://localhost:5173`

### Production Build

```bash
# Build for production
npm run build

# Preview production build
npm run preview
```

### Linting

```bash
# Run ESLint
npm run lint

# Fix linting issues
npm run lint -- --fix
```

### Frontend Pages

| Page | Purpose |
|------|---------|
| **Login** | Authentication |
| **Dashboard** | System overview, health metrics, OEE |
| **SensorData** | Real-time sensor monitoring & visualization |
| **Predictions** | AI predictions, failure probability, TTF |
| **Alerts** | Alert management and notifications |
| **MaintenanceHistory** | Historical records and scheduling |
| **Reports** | Analytics and report generation |
| **MachineDetails** | Individual machine analysis |
| **Settings** | System configuration |

## 🏗 Architecture

### High-Level Architecture

```
┌─────────────────────────────────────────┐
│         React Frontend (Vite)           │
│  Dashboard | Predictions | Alerts       │
└────────────────┬────────────────────────┘
                 │ HTTP/REST API
┌────────────────▼────────────────────────┐
│       Python Backend (FastAPI/Flask)    │
│  Routes | Controllers | Business Logic  │
└────────────────┬────────────────────────┘
                 │
┌────────────────▼──────────────────────┐
│      ML Pipeline & Models             │
│  Data Processing | Training | Predict │
└────────────────┬──────────────────────┘
                 │
┌────────────────▼──────────────────────┐
│      Data Layer                       │
│  CSV Files | Database | Sensors       │
└───────────────────────────────────────┘
```

### Model Factory Pattern

The backend uses the Factory pattern for flexible model management:

```
ModelFactory
├── load(model_name) → Model instance
├── train(model_type, data) → Trained model
├── predict(model, features) → Predictions
└── save(model, path)
```

## 📊 Data Flow

### Training Pipeline

```
Raw Data (CSV)
    ↓
Loading & Exploration
    ↓
Cleaning (Missing Values, Duplicates)
    ↓
Encoding (Categorical → Numerical)
    ↓
Scaling (Normalization)
    ↓
Balancing (Handle Imbalance)
    ↓
Train/Test Split
    ↓
Model Training
    ↓
Evaluation (Metrics)
    ↓
Model Artifact (Joblib)
```

### Prediction Pipeline

```
Live Sensor Data
    ↓
Preprocessing (same as training)
    ↓
Load Trained Model
    ↓
Generate Predictions
    ↓
Risk Assessment
    ↓
Frontend Dashboard
```

## 🤖 ML Models

### Available Models

1. **Logistic Regression** (`logistic_regression_failure_prediction.joblib`)
   - Interpretable linear model
   - Fast inference
   - Good baseline

2. **Decision Tree** (`decision_tree_failure_prediction.joblib`)
   - Non-linear relationships
   - Feature importance ranking
   - Easy to explain

3. **Extensible Framework**
   - Add XGBoost, Random Forest, LSTM, etc.
   - Ensemble methods support
   - Hyperparameter tuning

### Dataset

**Source**: `data/Predictive_Maintenance_dataset.csv`

**Features**:
- Machine operational parameters
- Environmental conditions
- Historical maintenance data
- Sensor readings

**Target**:
- Failure prediction (binary classification)

### Model Performance

View model metrics in:
- Notebooks: `notebooks/2_Logistic_Regression.ipynb`
- Utility functions: `maintenance_ml/utils/metrices.py`

## 📡 API Documentation

*(Add specific API endpoints once backend API is created)*

### Predicted Endpoints Structure

```
POST /api/predict
  Request: { features: [...] }
  Response: { probability: 0.87, ttf: "48h", risk: "high" }

GET /api/models
  Response: { models: [...] }

POST /api/train
  Request: { model_type: "logistic_regression", params: {...} }
  Response: { model_id: "...", status: "training" }

GET /api/sensors/:machine_id
  Response: { readings: [...] }
```

## 🔄 Integration Steps

1. **Create Flask/FastAPI Backend**
   - Expose ML models as REST API
   - Connect to real sensor data source
   - Implement user authentication

2. **Connect Frontend to Backend**
   - Configure API base URL in `.env`
   - Implement API service layer
   - Add error handling and loading states

3. **Database Integration**
   - Store predictions and alerts
   - Maintain maintenance history
   - Track model performance

4. **Real-time Updates**
   - WebSockets for live sensor data
   - Push notifications for alerts
   - Live dashboard updates

## 📊 Key Metrics

- **OEE (Overall Equipment Effectiveness)**
- **MTBF (Mean Time Between Failures)**
- **MTTR (Mean Time To Repair)**
- **Prediction Accuracy**
- **Model Precision/Recall/F1-Score**
- **False Positive Rate**
- **Failure Detection Rate**

## 🔐 Security Considerations

- Authentication required for API access
- API key management in settings
- Data encryption in transit (HTTPS)
- Sensitive data not stored in frontend
- Input validation on backend
- CORS configuration

## 🐛 Troubleshooting

### Python Dependencies
```bash
# Install all requirements
pip install pandas numpy scikit-learn xgboost joblib

# Check versions
pip list
```

### Virtual Environment Issues
```bash
# Recreate virtual environment
deactivate
rm -rf venv
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Frontend Build Issues
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
npm run dev
```

## 📈 Future Enhancements

- [ ] Time-series models (LSTM, Prophet)
- [ ] Ensemble methods
- [ ] Real-time data streaming
- [ ] Advanced anomaly detection
- [ ] Mobile application
- [ ] Multi-language support
- [ ] Advanced RBAC
- [ ] Data export features
- [ ] Historical trend analysis
- [ ] Custom alert rules

## 🤝 Contributing

1. Create a feature branch
```bash
git checkout -b feature/your-feature
```

2. Make changes and commit
```bash
git commit -m "Add your feature"
```

3. Push to branch
```bash
git push origin feature/your-feature
```

4. Submit a Pull Request


## 👥 Team

- Machine Learning Engineer
- Full-Stack Developer

## 📞 Support & Contact

For issues, questions, or suggestions:
- Open an issue on the repository
- Contact the development team
- Check documentation and notebooks

## 📚 Additional Resources

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [React Documentation](https://react.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Jupyter Notebooks](https://jupyter.org/)

---

**Project Version**: 0.0.0  
**Last Updated**: December 29, 2025  
**Status**: In Development