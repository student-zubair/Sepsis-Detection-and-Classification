# 🩺 Sepsis Management System — Machine Learning + FastAPI + Streamlit

A complete end-to-end system for **sepsis subtype prediction**, **cluster-based interpretation**, and **interactive visualization**, combining:

* **ML Models (KMeans + key components)**
* **FastAPI Backend**
* **Streamlit Frontend**
* **LLM-powered interpretation**
* **Docker support**

---

## 🚀 Project Overview

This project provides a scalable ML-driven framework for **Sepsis Subtype Prediction**.
It enables:

* Predicting sepsis subtype using trained ML models
* Displaying patient risk factors and comparisons
* Explaining subtype behaviour using LLM-based narratives
* Interactive visual dashboards using Streamlit
* API-driven backend using FastAPI

This repository is structured as a production-ready system with decoupled **frontend**, **backend**, and **model pipeline**.

---

## 🏗 System Architecture

```
┌─────────────────┐         ┌──────────────────────┐
│  Streamlit UI   │◄──────►│  FastAPI Backend      │
│ (Frontend)      │ API     │ (Model Inference)     │
└─────────────────┘         └──────────────────────┘
           │                            │
           ▼                            ▼
   User Inputs                    ML Models (.pkl)
           │                            │
           └──────────────►─────────────┘
```

---

## 📁 Folder Structure

```
Sepsis-Project-main/
│
├── data/                          # Visualization & clustered data
├── models/                        # Trained ML models
│   ├── kmeans_sepsis_model.pkl
│   └── model_and_key_components.pkl
│
├── src/
│   ├── FastAPI/
│   │   └── main.py                # Backend API
│   │
│   ├── Streamlit_App/
│       ├── app.py                 # Main frontend UI
│       ├── results.py             # Subtype comparison & visualization
│       └── Dockerfile             # Streamlit container image
│
├── dev/
│   └── sepsis_analysis.ipynb      # Notebook for data exploration
│
├── requirements.txt
└── README.md
```

---

# ⚙️ Installation & Setup

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/student-zubair/Sepsis-Detection-and-Classification.git
cd Sepsis-Project-main
```

## 2️⃣ Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate    # Mac/Linux
venv\Scripts\activate       # Windows
```

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🌐 FastAPI Backend

The backend exposes endpoints for:

* Loading ML models
* Preprocessing inputs
* Returning sepsis cluster predictions
* Generating explanations

### ▶️ Run FastAPI Server

```bash
cd src/FastAPI
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

### 📍 Main Files

#### `main.py` includes:

* Loading ML model & PCA/scaler
* Endpoint:

  ```
  POST /predict
  ```
* Returns:

  ```json
  {
    "cluster": 2,
    "interpretation": "LLM generated explanation..."
  }
  ```

---

# 🖥 Streamlit Frontend

The Streamlit application provides:

* Patient data input UI
* API-based subtype prediction
* Cluster comparison plots
* LLM explanation panel
* Risk visualization

### ▶️ Run Streamlit

```bash
cd src/Streamlit_App
streamlit run app.py
```

Streamlit will automatically communicate with the FastAPI backend.

---

## 🐳 Docker Support (Frontend)

Inside `src/Streamlit_App/`:

#### Build image:

```bash
docker build -t sepsis-streamlit .
```

#### Run container:

```bash
docker run -p 8501:8501 sepsis-streamlit
```

---

# 🧠 Machine Learning Model

Model files:

### 1. `kmeans_sepsis_model.pkl`

* KMeans model used to identify sepsis phenotypes
* Trained using engineered features

### 2. `model_and_key_components.pkl`

Contains:

* Scaler
* PCA transformer
* KMeans
* Feature set

### Process:

```
Raw Features
   ↓
Scaling
   ↓
PCA dimensionality reduction
   ↓
KMeans clustering
   ↓
Cluster Label + Interpretation
```

---

# 🔗 API Documentation

### **POST /predict**

**Request:**

```json
{
  "HR": 89,
  "Temp": 38.1,
  "Platelets": 142,
  "Resp": 21
}
```

**Response:**

```json
{
  "cluster": 1,
  "interpretation": "This subtype shows moderate organ instability..."
}
```

---

# 📊 Streamlit Features

### ✔ Live patient input

### ✔ Backend-powered prediction

### ✔ Cluster comparison table

### ✔ LLM-powered subtype narrative

### ✔ Visualization using CSV files:

* `Visualization_Data_Train.csv`
* `Visualization_Data_Test.csv`

---

# 📘 Development Notebook

`dev/sepsis_analysis.ipynb` includes:

* Exploratory Data Analysis (EDA)
* Preprocessing
* PCA visualization
* Cluster analysis
* Model saving workflow

---

# 🛠 Technologies Used

### **Frontend**

* Streamlit

### **Backend**

* FastAPI
* Uvicorn

### **Machine Learning**

* Scikit-learn
* KMeans
* PCA
* StandardScaler

### **LLM Integration**

* Google GenAI

### **Containers**

* Docker

---

# 🧪 Testing

### Test Backend:

```bash
curl -X POST http://localhost:8000/predict \
-H "Content-Type: application/json" \
-d '{"HR":80,"Resp":20,"Platelets":130,"Temp":38}'
```

### Test Frontend:

```bash
streamlit run app.py
```

---



# 🙌 Acknowledgements

* Public sepsis datasets
* Streamlit and FastAPI communities

---

