# 🚀 Insurance Premium Category Prediction API

A Machine Learning powered web application that predicts **Insurance Premium Category** based on user demographics, lifestyle, and financial details.

This project demonstrates:

* ML model deployment using **FastAPI**
* Data validation using **Pydantic**
* Interactive frontend using **Streamlit**
* End-to-end ML workflow integration

---

## 📌 Project Overview

The system takes user inputs such as:

* Age
* Height & Weight
* Annual Income (LPA)
* Smoking Status
* City
* Occupation

It then computes additional derived features like:

* BMI
* Lifestyle Risk
* Age Group
* City Tier

These features are passed to a trained ML model which predicts the **Insurance Premium Category**.

---

## 🏗️ Project Architecture

```
User (Streamlit UI)
        ↓
   FastAPI Backend
        ↓
  ML Model (model.pkl)
        ↓
  Prediction Response
```

---

## 🧠 Key Features

### ✅ 1. FastAPI Backend

* REST API endpoint: `/predict`
* Structured data validation using Pydantic
* Automatic feature engineering (BMI, risk level, etc.)
* Loads trained ML model using pickle

Reference: 

---

### ✅ 2. Streamlit Frontend

* Simple interactive UI
* Sends POST request to FastAPI
* Displays prediction result dynamically

Reference: 

---

### ✅ 3. Feature Engineering Logic

Automatically computed features:

| Feature        | Logic                                |
| -------------- | ------------------------------------ |
| BMI            | weight / height²                     |
| Lifestyle Risk | Based on smoker + BMI                |
| Age Group      | young / adult / middle_aged / senior |
| City Tier      | Tier 1 / Tier 2 / Tier 3             |

---

## 📂 Project Structure

```
├── app.py                 # FastAPI backend
├── frontend.py            # Streamlit UI
├── model.pkl              # Trained ML model
├── requirements.txt       # Dependencies
└── fastapi_ml_model.ipynb # Model training notebook
```

Dependencies: 

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/insurance-premium-predictor.git
cd insurance-premium-predictor
```

### 2️⃣ Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Application

### Start FastAPI Server

```bash
uvicorn app:app --reload
```


### Start Streamlit Frontend

```bash
streamlit run frontend.py
```

---

## 📬 API Usage Example

### POST `/predict`

#### Request Body (JSON)

```json
{
  "age": 30,
  "weight": 70,
  "height": 1.75,
  "income_lpa": 12,
  "smoker": false,
  "city": "Mumbai",
  "occupation": "private_job"
}
```

#### Response

```json
{
  "predicted_category": "Medium"
}
```

---

## 🛠️ Tech Stack

* **Python**
* **FastAPI**
* **Pydantic**
* **Scikit-learn**
* **Pandas**
* **Streamlit**
* **Uvicorn**

---

## 📈 What This Project Demonstrates

* ML model deployment
* Backend API development
* Input validation & feature engineering
* Full-stack ML integration
* Real-world insurance risk modeling logic