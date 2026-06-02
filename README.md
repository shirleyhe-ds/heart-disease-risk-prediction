# Heart Disease Risk Prediction

A machine learning project that predicts the likelihood of heart disease using patient clinical and demographic data.

---

## Project Overview

Heart disease is one of the leading causes of death worldwide. Early identification of high-risk patients can help healthcare professionals make more informed decisions and improve patient outcomes.

In this project, we developed a machine learning pipeline to predict heart disease based on patient health indicators. The workflow includes:

- Data Cleaning
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Machine Learning Model Development
- Model Evaluation

---

## Objective

Build a predictive model that accurately classifies whether a patient has heart disease based on clinical measurements and demographic information.

---

## Dataset

The dataset contains patient cardiovascular health records, including:

- Age
- Sex
- Chest Pain Type
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Resting ECG Results
- Maximum Heart Rate
- Exercise-Induced Angina
- ST Depression
- Number of Major Vessels
- Thalassemia

### Target Variable

| Value | Meaning |
|---------|---------|
| 0 | No Heart Disease |
| 1 | Heart Disease Present |

---

## 🛠️ Technologies Used

### Programming Language

- Python

### Libraries

- pandas
- NumPy
- scikit-learn
- Matplotlib
- Seaborn

### Machine Learning Model

- Random Forest Classifier

---

## 🔍 Methodology

### 1. Data Preprocessing

- Checked for missing values
- Cleaned and transformed data
- Prepared features for model training
- Performed feature selection

### 2. Exploratory Data Analysis (EDA)

- Analyzed feature distributions
- Investigated relationships between variables
- Generated correlation heatmaps
- Explored trends associated with heart disease

### 3. Model Training

- Split data into training and testing sets
- Trained a Random Forest Classifier
- Generated predictions on unseen data

### 4. Model Evaluation

Performance was evaluated using:

- Accuracy
- Confusion Matrix
- Classification Report
- Feature Importance Analysis

---

## Results

### Model Performance

Accuracy: **91%**

### Key Findings

- Several cardiovascular indicators showed strong predictive power.
- Feature importance analysis identified the most influential health risk factors.
- The Random Forest model achieved strong performance on unseen data.

---

## Visualizations

### Correlation Heatmap

Add screenshot here:

```markdown
![Correlation Heatmap](images/correlation_heatmap.png)
```

### Feature Importance Plot

```markdown
![Feature Importance](images/feature_importance.png)
```

### Confusion Matrix

```markdown
![Confusion Matrix](images/confusion_matrix.png)
```

---

## Project Structure

```text
heart-disease-risk-prediction/
│
├── DDSC_heartdiseaseml.ipynb
├── README.md
└── requirements.txt
```

---

## Future Improvements

- Compare additional machine learning models
- Perform hyperparameter tuning
- Implement cross-validation
- Deploy as a web application
- Train on larger healthcare datasets

---

## Disclaimer

This project was created for educational purposes only and should not be used as a medical diagnostic tool.

---

## Author

Chenfei, Shirley, Jocelyn, Carolene, Toyin, Judith
