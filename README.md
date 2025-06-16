# 🛡️ Phishing Website Detection Tool

This project is a hybrid **Phishing Website Detection Tool** that leverages both **rule-based heuristics** and a **machine learning model** to accurately classify URLs as **Legitimate** or **Phishing**.

---

## 📌 Features

- 🔍 Rule-based detection for obvious phishing indicators:
  - Shortened URLs (e.g., `bit.ly`)
  - IP addresses instead of domain names
  - `@` symbols in URLs

- 🤖 Machine Learning model (Random Forest) trained on a dataset of phishing features
- 📂 Logging of predictions into a CSV file (`scan_results.csv`) with timestamp
- 🛠️ Command-line interface for manual input and testing
- 🧠 Real-time feature-based prediction using `.pkl` model

---

## 🧾 Dataset Used

The dataset was downloaded from the UCI Machine Learning Repository:

🔗 [UCI Phishing Websites Dataset](https://archive.ics.uci.edu/dataset/327/phishing+websites)

---

## ⚙️ How It Works

### 1. **Load and Preprocess the Dataset**
- Dataset was converted from `.arff` to `.csv` using `liac-arff`
- Data was cleaned and separated into features (X) and label (y)

### 2. **Model Training**
```python
from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier()
model.fit(X_train, y_train)

Step 1: Install Required Libraries

pip install pandas scikit-learn joblib liac-arff
▶️ Step 2: Train the Model

python train_model.py
🔍 Step 3: Predict

python optional.py            # Manual input
python url_predictor.py       # Automatic URL check
📌 Output:
🔗 Enter a URL to check: https://bit.ly/pay-now

🚨 Rule-Based Alert: Suspicious URL detected. Likely Phishing ⚠️

✅ Scan result saved to scan_results.csv
