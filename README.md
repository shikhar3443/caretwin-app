# CareTwin — Personal Healthcare Intelligence & Emergency Platform 🏥🤖

[![Live Web App](https://img.shields.io/badge/Live_App-caretwin--frontend.vercel.app-0070F3.svg?style=for-the-badge&logo=vercel)](https://caretwin-frontend.vercel.app/)
[![Live API Docs](https://img.shields.io/badge/Live_API-FastAPI_Swagger-009688.svg?style=for-the-badge&logo=fastapi)](https://caretwin-backend-qkql.onrender.com/docs)
[![Next.js](https://img.shields.io/badge/Frontend-Next.js%2015-black.svg?style=flat&logo=next.js)](https://nextjs.org/)
[![FastAPI](https://img.shields.io/badge/Backend-FastAPI%200.110-009688.svg?style=flat&logo=fastapi)](https://fastapi.tiangolo.com/)
[![XGBoost](https://img.shields.io/badge/ML-XGBoost%20Mortality%20Model-EB5424.svg?style=flat&logo=scikitlearn)](https://xgboost.readthedocs.io/)
[![Tesseract OCR](https://img.shields.io/badge/Vision-Tesseract%205.x-blue.svg?style=flat)](https://github.com/tesseract-ocr/tesseract)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 🌟 Overview

**CareTwin** is an AI-powered Personal Healthcare Record (PHR) and Clinical Intelligence platform designed to bridge the gap between fragmented medical paper reports and actionable patient health history. 

It provides automated multi-scale OCR parsing of medical documents, longitudinal biomarker tracking, statistical anomaly detection, instant emergency QR resuscitation profiles, and integrated machine learning mortality/clinical risk scoring.

---

## 📁 Repository Structure (Monorepo)

```text
CareTwin/
├── caretwin-backend/        # FastAPI REST API, ML Inference & OCR Pipeline
│   ├── app/
│   │   ├── api/v1/          # Modular endpoints (Auth, Family, Records, OCR, Timeline, Trends, QR, ML)
│   │   ├── core/            # Security, JWT, settings & database connections
│   │   ├── ml_assets/       # Trained XGBoost models & OneHotEncoder preprocessors
│   │   ├── models/          # SQLAlchemy ORM database models
│   │   ├── schemas/         # Pydantic request/response validation schemas
│   │   └── services/        # OCR Engine, Medical NLP, Trend Engine & Prediction Service
│   ├── tests/               # 6 automated Pytest test suites (100% passing)
│   ├── Dockerfile           # Production container with Linux Tesseract & OpenCV
│   └── requirements.txt     # Python dependencies
│
└── caretwin-frontend/       # Modern Next.js 15 App Router Dashboard
    ├── app/
    │   ├── (auth)/          # JWT Login & Registration pages
    │   ├── dashboard/       # Protected Patient & Family Portal
    │   │   ├── medical-records/ # File upload & OCR result inspector
    │   │   ├── mortality-risk/  # Interactive XGBoost ML risk predictor
    │   │   ├── emergency/       # Emergency QR code generator
    │   │   ├── family/          # Family member management
    │   │   └── reports/         # Longitudinal biomarker trend analysis
    │   └── emergency/       # Public paramedic / first-responder triage view
    ├── components/          # Modular UI widgets, cards, and trend charts
    ├── lib/                 # Type-safe API client, state provider & date utilities
    └── package.json         # Dependencies & Next.js build scripts
```

---

## 🚀 Key Features

1. **🔐 Multi-Profile Family Locker**: Secure JWT authentication supporting multiple dependents (self, parents, children) under a single master account.
2. **🔬 Multi-Scale Medical OCR & Quality Inspection**: Ingests PDFs, photos, and scans. Gated by image quality validation, extracts 25+ parameters across CBC, LFT, KFT, Metabolic, and Lipid panels, plus primary diagnosis and medications.
3. **📈 Longitudinal Health Timeline**: Chronological tracking of biometric trajectories with min/max/average stats.
4. **⚠️ Biomarker Trend Anomaly Detection**: Statistical trajectory rules identifying critical deviations and alerting patients.
5. **🚨 Emergency QR Resuscitation Access**: High-resolution scannable QR tokens enabling first-responders to access life-saving allergies, blood group, and emergency contacts in under 5 seconds without authentication.
6. **🤖 Embedded Machine Learning Risk Scoring**: Pre-trained XGBoost clinical risk assessment model evaluated in-process via demographic parameters and real-time lab test results.

---

## 🛠️ Tech Stack

- **Frontend**: Next.js 15 (App Router), React 19, TypeScript, Tailwind CSS, Framer Motion, Lucide Icons.
- **Backend**: FastAPI, Uvicorn (ASGI), Python 3.11+, SQLAlchemy 2.0.
- **Database**: PostgreSQL (Production) / SQLite (Local Dev).
- **Machine Learning**: XGBoost 3.x, Scikit-Learn, Joblib, NumPy, SciPy.
- **Computer Vision**: Tesseract OCR 5.x, PyTesseract, OpenCV, Pillow.
- **Cloud Deployment**: Vercel (Frontend Global CDN) & Render (Docker Web Service & PostgreSQL).

---

## ⚡ Quick Start Guide

### 1. Run Backend
```bash
cd caretwin-backend
python -m venv venv
# Windows:
.\venv\Scripts\activate
# Linux/macOS:
source venv/bin/activate

pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```
- Backend Docs: `http://localhost:8000/docs`

### 2. Run Frontend
```bash
cd caretwin-frontend
npm install
npm run dev
```
- Web App: `http://localhost:3000`

---

## 👥 Contributors & Team
- **System Architecture & Full-Stack Integration**: [@shikhar3443](https://github.com/shikhar3443)
- **Computer Vision & OCR Pipeline**: [@Amit-11-Yadav](https://github.com/Amit-11-Yadav)
- **Machine Learning & Risk Modeling**: [@dheerajpatel003300-svg](https://github.com/dheerajpatel003300-svg)
- **UI Design & Upstream Collaboration**: [@rohitsingh15072005](https://github.com/rohitsingh15072005)
