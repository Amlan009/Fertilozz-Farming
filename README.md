# 🌱 Fertilozz — AI-Powered Agricultural Advisory & Forecasting Platform

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.x-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**Fertilozz** is an intelligent, full-stack decision-support system designed to empower farmers and agriculturalists with data-driven insights. By analyzing 7 crucial soil and climatic parameters, the platform delivers high-accuracy crop recommendations, tailored fertilizer guidance, agricultural equipment catalogs, and financial yield/revenue forecasting.

---

## 📌 Key Features

* **🌾 AI Crop Recommendation:** Accurately recommends the optimal crop among 22 varieties based on Nitrogen ($N$), Phosphorus ($P$), Potassium ($K$), Soil pH, Temperature, Humidity, and Rainfall.
* **🧪 Fertilizer Advisory:** Matches predicted crops with targeted primary fertilizers and provides complete application guides and purchasing links.
* **📈 Economic Yield & Revenue Forecasting:** Calculates estimated crop yield and gross revenue based on user-entered land acreage and real-world market pricing benchmarks.
* **🛠️ Farming Tools & Equipment Catalog:** Curated catalog of essential agricultural machinery and equipment with specifications and purchase references.
* **🔒 Secure Authentication:** Multi-user authentication system built with **Flask-Login** and **Flask-Bcrypt** with salted password hashing and CSRF protection.

---

## 🔬 Machine Learning Pipeline

```
[Soil & Climate Data] (N, P, K, pH, Temp, Humidity, Rainfall)
        │
        ▼
[Data Preprocessing & IQR Outlier Capping]
        │
        ▼
[Gaussian Naive Bayes Model (fert.pkl)]
        │
        ▼
[Predicted Crop Variety (22 Classes)] ──► [Database Lookup: Guidance & Forecasting]
```

* **Algorithm:** Gaussian Naive Bayes Classifier
* **Dataset:** 2,200 agricultural records (1,650 Train / 550 Test)
* **Training Accuracy:** **99.64%**
* **Testing Accuracy:** **99.27%**
* **Precision / Recall / F1-Score:** **0.99** (Macro & Weighted Average)
* **Target Crops (22):** Rice, Maize, Jute, Cotton, Coconut, Papaya, Orange, Apple, Muskmelon, Watermelon, Grapes, Mango, Banana, Pomegranate, Lentil, Blackgram, Mungbean, Mothbeans, Pigeonpeas, Kidneybeans, Chickpea, Coffee.

---

## 🛠️ Technology Stack

| Layer | Technologies |
| :--- | :--- |
| **Backend** | Python, Flask, Flask-SQLAlchemy, Flask-Login, Flask-WTF, Flask-Bcrypt, WTForms |
| **Machine Learning** | Scikit-learn, NumPy, Pandas, LazyPredict, Pickle |
| **Frontend** | HTML5, CSS3, JavaScript, Bootstrap 5, Jinja2 Templating |
| **Database** | SQLite3 (`user.db` for user accounts, `fertilizeDB.db` for agricultural data) |

---

## 📁 Repository Structure

```text
Farming/
├── app.py                     # Main Flask application & routing
├── fert.pkl                   # Serialized ML classification model
├── fertilizeDB.db             # SQLite database for crop & fertilizer data
├── requirements.txt           # Project dependencies
├── .gitignore                 # Ignored files & build artifacts
├── README.md                  # Project documentation
├── files/
│   ├── Crop_recommendation.csv        # Raw dataset
│   └── Fertilizer recommendation.ipynb # EDA & Model training notebook
├── static/
│   ├── css/                   # Custom stylesheets
│   ├── javascript/            # Frontend scripts
│   ├── images/                # App logos & background assets
│   ├── Pictures/              # Crop, fertilizer, and tool imagery
│   └── vendor/                # Bootstrap, Swiper, and AOS libraries
└── templates/                 # Jinja2 HTML templates
    ├── index.html             # Landing page
    ├── login.html             # User login
    ├── register.html          # User registration
    ├── main.html              # Soil & climate input form
    ├── output.html            # Prediction result & crop guide
    ├── fertilizer.html        # Fertilizer recommendations
    ├── fertilizerlist.html    # Full fertilizer catalog
    ├── forecast.html          # Acreage revenue calculator
    └── tools.html             # Agricultural machinery catalog
```

---

## 🚀 Quick Start Guide

### 1. Clone the repository
```bash
git clone https://github.com/your-username/fertilozz-farming.git
cd fertilozz-farming
```

### 2. Create and activate a virtual environment (Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the application
```bash
python app.py
```

### 5. Access the Web App
Open your browser and navigate to:
```
http://127.0.0.1:5000
```

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use and modify it for learning and personal projects.
