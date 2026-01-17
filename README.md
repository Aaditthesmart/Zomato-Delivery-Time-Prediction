# 🍽️ Zomato Delivery Time Prediction

## 📌 Project Overview
This project focuses on predicting **food delivery time (in minutes)** using machine learning techniques.  
The objective is to model how operational and human factors such as traffic, weather, city, delivery partner attributes, and order characteristics influence delivery duration.

The project is based on a **real-world Zomato delivery operations dataset** and emphasizes building an **end-to-end applied machine learning workflow**, not just training a model.

---

## 🧠 Problem Statement
Given order-level and delivery-partner information, predict the expected time taken to deliver a food order.

**Target Variable:**
- `Time_taken (min)`

This is a **regression problem** relevant to food delivery platforms such as Zomato, Swiggy, Zepto, and Blinkit.

---

## 📊 Dataset Description
The dataset contains information related to:
- Delivery partner details (age, ratings)
- Order characteristics
- Traffic and weather conditions
- City and festival indicators
- Vehicle type
- Number of deliveries handled simultaneously

The dataset includes missing values, making it realistic and suitable for practicing real-world ML data handling.

---

## 🔧 What I Did in This Project

### 1️⃣ Data Inspection & Cleaning
- Loaded the dataset using Pandas
- Checked data types, shape, and missing values
- Handled missing values using:
  - **Median imputation** for numerical features
  - **Mode imputation** for categorical features
- Dropped a highly incomplete time-related column after evaluation

This ensured the dataset was **model-ready without dropping rows unnecessarily**.

---

### 2️⃣ Exploratory Data Analysis (EDA)
Performed targeted EDA to understand relationships between features and delivery time:

- Distribution of delivery time
- Impact of traffic density on delivery duration
- Effect of weather conditions
- City-wise delivery behavior
- Relationship between delivery partner ratings and delivery time
- Vehicle type vs delivery time

EDA confirmed that delivery time depends on **non-linear interactions**, motivating the use of tree-based models.

---

### 3️⃣ Feature Selection
Explicitly selected meaningful features to avoid data leakage and noise:

**Features Used:**
- `Delivery_person_Age`
- `Delivery_person_Ratings`
- `Weather_conditions`
- `Road_traffic_density`
- `Vehicle_condition`
- `Type_of_order`
- `Type_of_vehicle`
- `multiple_deliveries`
- `Festival`
- `City`

**Target:**
- `Time_taken (min)`

---

### 4️⃣ Data Preprocessing
- Converted categorical variables using **one-hot encoding**
- Performed a **train–validation split** to evaluate generalization

---

### 5️⃣ Model Training
- Trained a **Random Forest Regressor**
- Random Forest was chosen because it:
  - Handles non-linear relationships well
  - Performs effectively on mixed numerical and categorical data
  - Reduces overfitting compared to a single decision tree

---

### 6️⃣ Model Evaluation
Evaluated performance using **Mean Absolute Error (MAE)**.

**Results:**
- **Training MAE:** ~1.78 minutes  
- **Validation MAE:** ~4.23 minutes  

This means that on unseen data, the model predicts delivery time with an average error of approximately **4 minutes**, which is considered good for real-world logistics problems.

The gap between training and validation error is moderate and expected due to noise in traffic, weather, and human behavior.

---

## 📈 Key Inferences
- Delivery time prediction is a **non-linear problem**
- Traffic density, city, and delivery partner factors significantly affect delivery duration
- Random Forest generalizes well compared to a single decision tree
- Explicit feature selection and proper data cleaning are critical for realistic ML performance

---

## 🛠️ Tools & Technologies Used
- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- scikit-learn

---

## 🎯 Learning Outcomes
- Built a complete machine learning workflow from raw data to evaluation
- Learned to handle missing values in real datasets
- Performed meaningful EDA for business understanding
- Trained and evaluated a Random Forest regression model
- Interpreted model performance using appropriate metrics

---

## 🚀 Future Improvements
- Feature engineering using geographical distance
- Hyperparameter tuning using cross-validation
- Comparing Random Forest with other regression models
- Packaging preprocessing and modeling into a formal sklearn Pipeline

---

## ✅ Conclusion
This project demonstrates an applied machine learning approach to a real-world delivery operations problem.  
It focuses on **understanding data, building robust models, and drawing meaningful conclusions**, making it suitable for an early-stage ML portfolio.

