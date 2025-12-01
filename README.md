# 🩺 Sepsis Detection and Classification System

This project is a **Machine Learning–powered healthcare tool** designed to:

* Detect potential **Sepsis risk** based on patient clinical data
* Predict the **Sepsis subtype (phenotype)** using clustering (K-Means)
* Provide **treatment recommendations** using a Generative AI model
* Provide an interactive UI for clinicians using **Streamlit**
* Serve predictions programmatically via a **FastAPI backend**

---

## 🚀 Features

| Feature                   | Description                                                           |
| ------------------------- | --------------------------------------------------------------------- |
| 🔍 Sepsis Prediction      | ML model predicts risk based on vitals & lab data                     |
| 🧬 Subtype Classification | KMeans clustering assigns patient subtype                             |
| 🤖 AI-Generated Treatment | Google Gemini suggests treatment plan                                 |
| 🖥 Interactive UI         | User-friendly Streamlit interface                                     |
| 🌐 REST API               | FastAPI backend for integration                                       |
| 📦 Virtual Environment    | Reproducible environment using `requirements.txt` and `.devcontainer` |

---

## 🧰 Tech Stack

| Category     | Tools                             |
| ------------ | --------------------------------- |
| Language     | Python 3.12                       |
| ML Libraries | Scikit-Learn, Pandas, NumPy       |
| Frontend     | Streamlit                         |
| Backend      | FastAPI, Uvicorn                  |
| Deployment   | Docker / DevContainer (optional)  |
| LLM Support  | Google Generative AI API (Gemini) |

---

## 📂 Project Structure

```
Sepsis-Detection-and-Classification/
│
├── .devcontainer/            # VS Code dev environment config
├── data/                     # Dataset (optional)
├── models/                   # Trained ML model files (.pkl)
├── src/
│   ├── FastAPI/              # Backend API
│   │   └── main.py
│   │
│   └── Streamlit_App/        # Frontend UI
│       └── app.py
│
├── requirements.txt          # Python dependencies
├── README.md                 # You're reading this :)
└── .gitignore                # Ignored files
```

---

## 🛠 Installation & Setup

### 1️⃣ Clone the Repository

```
git clone https://github.com/student-zubair/Sepsis-Detection-and-Classification.git
cd Sepsis-Detection-and-Classification
```

---

### 2️⃣ Create and Activate Virtual Environment

```
python -m venv venv
```

#### Windows:

```
venv\Scripts\activate
```

---

### 3️⃣ Install Dependencies

```
pip install -r requirements.txt
```

---

## ▶️ Running the Application

### 🔹 Start FastAPI Backend:

```
cd src/FastAPI
uvicorn main:app --reload
```

It will start at:

👉 [http://localhost:8000/docs](http://localhost:8000/docs)

---

### 🔹 Start Streamlit Frontend (in a new terminal):

```
cd src/Streamlit_App
streamlit run app.py
```

App opens automatically at:

👉 [http://localhost:8501/](http://localhost:8501/)

---

## 🔑 Environment Variables

Create a `.env` file in project root and add:

```
GOOGLE_API_KEY=your_key_here
```

(Used for LLM-based treatment generation)

---

## 📊 Model Details

| Component        | Method              |
| ---------------- | ------------------- |
| Prediction Model | Logistic Regression |
| Feature Scaling  | StandardScaler      |
| Clustering       | KMeans              |
| AI Treatment     | Google Gemini API   |

---

## 🛳 Optional: Run in Dev Container

If using VS Code:

1. Install the **Dev Containers** extension
2. Open the project
3. Click:

```
Reopen in Container
```

This automatically builds the environment.

---

## 🤝 Contributions

Contributions, improvements, bug fixes, and feature requests are welcome.

---

## 📜 License

This project is for educational and research use.
Please consult healthcare professionals before clinical application.

---

## ✨ Developed By

👤 **Mohammed Zubair**
📌 Machine Learning & Data Science Enthusiast

---

---

