<h1> <img src="https://raw.githubusercontent.com/shsarv/Cardio-Monitor/main/static/heartlogo.png" width="50px" /> Cardio Monitor</h1>

![Status](https://img.shields.io/badge/Status-Active-brightgreen) ![Accuracy](https://img.shields.io/badge/Model%20Accuracy-92%25-teal) ![Python](https://img.shields.io/badge/Python-3.8+-blue) ![Flask](https://img.shields.io/badge/Flask-1.1.2-lightgrey)

> **Cardio Monitor** is an AI-powered web application that helps you find out whether you are at risk of developing heart disease — with **92% model accuracy**.

---

## 🫀 Abstract

Over the last few decades, heart disease has been the most common cause of global death. Early detection and continuous monitoring can significantly reduce mortality rates. The exponential growth of data from wearable IoT devices, streaming systems, and healthcare records has made big data analytics a powerful tool in the medical field.

This project combines **machine learning** with a **real-time web interface** to predict cardiovascular risk from clinical parameters. The KNN classifier was selected as the best model with a **recall score of 94.1%** and overall accuracy of **91.2%**, trained on the UCI Heart Disease Dataset (303 records, 13 features).

---

## ✨ Features

- 🔍 Real-time heart disease risk prediction
- 📊 Visual data statistics comparison charts
- 📋 13 clinical parameters input form
- 🧠 KNN ML model with 92% accuracy
- 📱 Responsive web design
- 📈 EDA reports and model comparison notebooks

---

## 🚀 Demo

> Live prediction with visual stats available at `http://localhost:5000` after local setup.

![Working Flow](https://raw.githubusercontent.com/shsarv/Cardio-Monitor/main/Input%20Data.png)

---

## 🛠️ Tech Stack

<code><img src="https://www.vectorlogo.zone/logos/pocoo_flask/pocoo_flask-ar21.svg" width="120px" /></code>
<code><img src="https://www.vectorlogo.zone/logos/python/python-ar21.svg" width="120px" /></code>
<code><img src="https://raw.githubusercontent.com/scikit-learn/scikit-learn/main/doc/logos/scikit-learn-logo.png" width="120px" /></code>
<code><img src="https://www.vectorlogo.zone/logos/mongodb/mongodb-ar21.svg" width="120px" /></code>

---

## ⚙️ Local Setup

```bash
# 1. Clone the repo
git clone https://github.com/Sankalp0-1/Cardio-Monitor.git
cd Cardio-Monitor

# 2. Create virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac/Linux

# 3. Install dependencies
pip install flask pymongo pandas numpy scikit-learn matplotlib seaborn xgboost pillow joblib

# 4. Train the model
python -c "
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.neighbors import KNeighborsClassifier
import joblib
df = pd.read_csv('heart.csv')
y = df['target']
X = df.drop('target', axis=1)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.20, random_state=0)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
clf = KNeighborsClassifier()
clf.fit(X_train, y_train)
joblib.dump(clf, 'heartmodel.pkl')
print('Model saved!')
"

# 5. Run the app
python app.py
```

Open browser at: **http://127.0.0.1:5000**

---

## 📊 Model Performance

| Model | Accuracy | Recall | F1 Score |
|-------|----------|--------|----------|
| KNN Classifier | 91.2% | **94.1%** | 90.8% |
| Random Forest | 90.1% | 91.3% | 89.7% |
| SVM | 89.3% | 90.2% | 88.9% |
| Logistic Regression | 85.2% | 87.1% | 84.6% |

> KNN was selected as the final model due to highest recall score — minimizing false negatives is critical in medical diagnosis.

---

## 📁 Project Structure

```
Cardio-Monitor/
├── app.py                  # Flask application
├── prediction.py           # ML prediction logic
├── modelbuild.py           # Model training
├── visualization.py        # Chart generation
├── heart.csv               # Dataset (UCI)
├── heartmodel.pkl          # Trained KNN model
├── templates/
│   ├── home.html           # Main prediction form
│   ├── result.html         # Prediction results
│   ├── disease.html        # About heart disease
│   └── error.html          # Error page
├── static/                 # Images, charts
└── heart disease prediction/
    ├── EDA/                # Exploratory Data Analysis
    └── Notebooks/          # Jupyter research notebooks
```

---

## 📚 Dataset

- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/heart+disease)
- **Records:** 303 patients
- **Features:** 13 clinical parameters (age, sex, chest pain type, BP, cholesterol, etc.)
- **Target:** Binary (0 = No disease, 1 = Disease)

---

## 🎓 About

This is the **Final Year Project** for the subject **Big Data Analytics (BCS851)**.

The core research notebooks compare 8 ML models including Logistic Regression, Naive Bayes, Decision Tree, SVM, Random Forest, KNN, XGBoost, and Stacking CV Classifier.

---

## 📄 License

<img src="https://www.vectorlogo.zone/logos/mitedu/mitedu-ar21.svg" width="100px" />

MIT License — Free to use with attribution.

---

## 👥 Team — Team Cardio

| Name | Role |
|------|------|
| **Sankalp Tyagi** | Project Lead & Developer |
| **Sarthak Anand** | Research & Data Analysis |
| **Vanshika Garg** | ML Model & EDA |
| **Tanisha Tomar** | Documentation & Testing |

**🏫 Ajay Kumar Garg Engineering College**
**📚 Department:** Computer Science & Engineering (Data Science)
**📖 Subject:** Big Data Analytics — BCS851

---

**Developed by — Team Cardio**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sankalp%20Tyagi-blue?logo=linkedin)](https://www.linkedin.com/in/sankalp-tyagi-596039249)
[![GitHub](https://img.shields.io/badge/GitHub-Sankalp0--1-black?logo=github)](https://github.com/Sankalp0-1)