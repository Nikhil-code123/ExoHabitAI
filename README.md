# 🪐 ExoHabitAI: The Intelligent Exoplanet Discovery Engine

[![Deployed on Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-000000?style=for-the-badge&logo=vercel)]https://exo-habit-ai.vercel.app/)
[![Backend on Render](https://img.shields.io/badge/Backend%20on-Render-46E3B7?style=for-the-badge&logo=render)](https://exohabitai-1-l6rr.onrender.com/)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-3776ab?style=for-the-badge&logo=python)](https://www.python.org/downloads/)
[![React 18](https://img.shields.io/badge/React-18-61dafb?style=for-the-badge&logo=react)](https://react.dev)

**Live Demo:** [exohabitai.vercel.app](https://exo-habit-ai.vercel.app/)  
**API:** [exohabitai-backend.onrender.com](https://exohabitai-1-l6rr.onrender.com/)

---

## 📋 Project Overview

ExoHabitAI is a **full-stack machine learning web application** that identifies potentially habitable exoplanets from NASA's confirmed exoplanet archive. Using a **Hybrid Stacking Ensemble Model** (XGBoost + Random Forest), it analyzes **39 physical and astronomical parameters** to predict habitability with **83.33% recall** and a precision-optimized threshold of **0.0763**.

### ⚡ Quick Stats
- **1,089** exoplanets analyzed
- **13** habitable candidates identified
- **99.17%** model accuracy
- **83.33%** recall rate
- **39** features analyzed per planet
- **<50ms** prediction latency

---

## ⭐ Key Features

### 🎬 **Cinematic User Experience**
- **3D Black Hole Visualization:** Interactive Three.js scene with particle effects
- **Glassmorphism Design:** Modern frosted glass UI with purple-pink-cyan gradients
- **Smooth Animations:** Framer Motion transitions and scroll parallax
- **Fully Responsive:** Desktop, tablet, and mobile optimization

### 🧠 **Intelligent ML Engine**
- **Hybrid Stacking Ensemble:** XGBoost + Random Forest meta-learning
- **Recall-Optimized:** 0.0763 threshold for maximum habitability detection
- **39-Parameter Analysis:** Comprehensive stellar & planetary characteristics
- **Sub-second Predictions:** Real-time analysis capabilities

### 📊 **Interactive Analytics Dashboard**
- **4 Dynamic Stat Cards:** Key metrics at a glance
- **4 Interactive Charts:** Feature importance, score distribution, classification, metrics
- **PDF & CSV Export:** Download complete analysis reports
- **Real-time Data Fetching:** Live dashboard updates

### 🚀 **Batch Processing**
- **Bulk Analysis:** Process 100+ planets in seconds
- **CSV Import:** Custom exoplanet datasets
- **Progress Tracking:** Real-time status updates
- **Batch Visualization:** Interactive results grid

### 🏆 **Ranking & Discovery**
- **Habitability Ranking:** Automatic sorting by confidence
- **Top Candidates:** Curated list of promising worlds
- **Detailed Metadata:** Complete parameters for each planet
- **Visual Indicators:** Trophy, medal, and award badges

---

## 🛠️ Technology Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| **Frontend** | React + Vite | 18.2.0 + 5.4.21 |
| **Styling** | Tailwind CSS | 3.4.0 |
| **Animations** | Framer Motion | 10.18.0 |
| **3D Graphics** | Three.js + React-Three/Fiber | 0.182.0 + 8.15.12 |
| **Charts** | Chart.js | 4.4.1 |
| **Backend** | Flask | 3.0.0 |
| **ML Models** | XGBoost + Scikit-Learn | 2.0.0 + 1.3.0 |
| **Data Processing** | Pandas + NumPy | 2.0.0 + 1.24.0 |
| **Server** | Gunicorn | 21.2.0 |
| **Deployment** | Vercel (Frontend) + Render (Backend) | Latest |

---

## 📊 Model Performance

| Metric | Value | Interpretation |
|--------|-------|-----------------|
| **Accuracy** | 99.17% | Overall correct predictions |
| **Recall** | 83.33% | Detects 5 out of 6 habitable planets |
| **Precision** | 38.46% | 1 in 2.6 "habitable" predictions correct |
| **F1 Score** | 52.63% | Balanced harmonic mean |
| **Threshold** | 0.0763 | Optimized decision boundary |

---

## 🚀 Quick Start

### **Local Development**

```bash
# Backend
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py

# Frontend (new terminal)
cd frontend
npm install
echo "VITE_API_URL=http://localhost:5000" > .env
npm run dev
```

Visit `http://localhost:5173` in your browser.

### **Live Deployment**

- **Frontend:** [exohabitai.vercel.app](https://exohabitai.vercel.app)
- **Backend:** [exohabitai-backend.onrender.com](https://exohabitai-backend.onrender.com)

---

## 📡 API Endpoints

```
GET    /status                      System health check
GET    /model/info                  Model specifications
POST   /predict                     Single planet prediction
POST   /predict/batch               Bulk analysis (100+ planets)
GET    /rank                        Top habitable candidates
GET    /planet/<index>              Detailed planet metadata
GET    /dashboard/stats             Dashboard statistics
GET    /dashboard/feature-importance Feature importance scores
GET    /dashboard/correlations      Correlation matrix
```

---

## 📁 Project Structure

```
ExoHabitAI/
├── backend/                  # Flask API
│   ├── app.py               # Main application
│   ├── utils.py             # Helper functions
│   ├── requirements.txt      # Python dependencies
│   └── sample_batch.json     # Example data
├── frontend/                # React SPA
│   ├── src/pages/           # Page components
│   ├── src/components/      # Reusable components
│   ├── src/services/        # API service layer
│   ├── package.json         # Node dependencies
│   └── .env                 # Environment config
├── data/                    # Dataset files
│   ├── raw/                 # Original NASA data
│   └── processed/           # Cleaned datasets
├── notebooks/               # Jupyter analysis
├── Procfile                 # Render deployment config
└── README.md               # This file
```

---

## 🎓 Deployment Guide

### **Phase 1: Deploy Backend on Render**

1. Create `Procfile` in project root:
   ```text
   web: gunicorn backend.app:app
   ```

2. Go to [dashboard.render.com](https://dashboard.render.com)
3. Click **New +** → **Web Service**
4. Connect your GitHub repository
5. Configure:
   - **Name:** `exohabitai-backend`
   - **Runtime:** Python 3
   - **Build Command:** `pip install -r backend/requirements.txt`
   - **Start Command:** `gunicorn backend.app:app`
6. Click **Create Web Service**
7. Copy the live URL (e.g., `https://exohabitai-backend.onrender.com`)

### **Phase 2: Deploy Frontend on Vercel**

1. Update `frontend/.env`:
   ```env
   VITE_API_URL=https://exohabitai-backend.onrender.com
   ```

2. Go to [vercel.com](https://vercel.com)
3. Click **Add New** → **Project**
4. Import your GitHub repository
5. Configure:
   - **Framework:** Vite
   - **Root Directory:** `frontend`
   - **Environment:** `VITE_API_URL`
6. Click **Deploy**

---

## 🧪 Testing

```bash
# Backend tests
cd backend && pytest test_api.py -v

# Frontend build
cd frontend && npm run build

# API health check
curl https://exohabitai-backend.onrender.com/status
```

---

## 📈 Dashboard Features

✅ 4 Key Metrics (Total, Habitable, Accuracy, Recall)  
✅ 3 Insights (Habitability Rate, Sensitivity, False Positives)  
✅ 4 Interactive Charts (Feature Importance, Score Distribution, Classification, Performance)  
✅ PDF/CSV Export with complete analysis  
✅ Real-time data fetching from backend  
✅ Glassmorphic UI with animations  

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| API Connection Error | Verify `VITE_API_URL` in `.env` matches Render backend |
| Port Already in Use | Kill existing process: `lsof -i :5000 && kill -9 <PID>` |
| Build Failure | Clear cache: `npm cache clean --force && rm -rf node_modules` |
| Model Load Error | Ensure model file exists and joblib version is compatible |

---

## 📚 Documentation

- **[Dashboard Module](docs/MODULE_7_VISUALIZATION_DASHBOARD.md)** - Complete dashboard guide
- **[Backend API](backend/QUICKSTART.md)** - API reference
- **[Frontend Docs](frontend/README.md)** - Frontend setup

---

## 🎯 Project Milestones

✅ Data Preprocessing & Feature Engineering  
✅ ML Model Development & Optimization  
✅ Backend API Implementation  
✅ Frontend UI/UX Design  
✅ 3D Visualization & Animations  
✅ Analytics Dashboard  
✅ **🚀 Production Deployment**

---

## 📝 License

MIT License - See [LICENSE](LICENSE) file

---

## 👨‍💻 Author

**Developed by:** [Your Name]  
**Internship:** Infosys Springboard  
**Last Updated:** February 2026

---

**🌌 Exploring the Universe, One Planet at a Time 🌌**
