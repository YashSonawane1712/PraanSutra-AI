# PraanSutra-AI 💓

## Project Description

This project is a **heart disease risk prediction platform** that identifies patients at high risk by analyzing historical medical records, diagnostic reports, and lifestyle data. Built on a **MongoDB data lake**, it consolidates diverse healthcare datasets—such as hospital records and national health surveys—into a unified, scalable repository. Machine learning models evaluate key risk factors for heart disease, enabling early detection, personalized interventions, and improved patient outcomes.

## Target Users 🎯

The platform is designed for:
- Cardiologists
- Healthcare providers
- Hospital administrators
- Public health researchers

  These users aim to proactively manage heart disease, optimize patient care, and reduce critical cardiac events.

  ## Problem Statement ⚠️

  Cardiovascular diseases (CVDs) are the leading cause of mortality in India, responsible for ~27% of all deaths. In 2022 alone, 32,457 people died from heart attacks, marking a 12.5% increase from the previous year.

Based on the Longitudinal Ageing Study in India (LASI):
- Prevalence of CVD among adults aged ≥45 years: **5.2%**
- Higher rates in men: **5.9%**
- Women: **4.6%**  

This study proposes the development of a **Predictive Patient Risk Data Lake** to identify individuals at high risk of heart-disease events within one year, leveraging integrated clinical and public-health data.  

**Target performance metric:** AUROC ≥ 0.70  
**Minimal sample size:** 2,000–4,000 patients (≈200 events for modeling)

## Data Lifecycle (Heart Disease Risk Project) 🔄

### 1️⃣ Capture – Collecting Data
We collect patient-related data from two main sources:
- **Kaggle datasets** – structured clinical data like age, BP, cholesterol, and heart disease labels.
- **NFHS (National Family Health Survey, India)** – semi-structured survey data on lifestyle, diet, smoking, and physical activity patterns.

Data is downloaded in CSV or Excel formats, cleaned using **Python + Pandas**, and converted into **JSON format** for MongoDB.

### 2️⃣ Store – Building a Patient-Centric Data Lake
Data is stored in **MongoDB**, with each patient represented as one document containing:
- **Demographics:** age, gender, region  
- **Clinical measurements:** BP, cholesterol, diabetes, BMI  
- **Survey info:** lifestyle, diet, alcohol, smoking habits  
- **Risk label:** heart disease presence  

This allows integration of structured Kaggle data and semi-structured NFHS data in one place.

### 3️⃣ Process – Cleaning & Transforming
- Standardize columns and handle missing values  
- Convert categorical survey answers into numeric form (e.g., smoking: Yes → 1, No → 0)  
- Categorize BMI and BP into normal, borderline, or high-risk groups  

All processing is done using **Python + PyMongo**, following **dbt-style transformation pipelines**.

### 4️⃣ Analyze – Predictive Modeling
Connect MongoDB data to **Python ML libraries**:
- Models: Logistic Regression, Random Forest, XGBoost  
- Predict probability of high-risk heart disease within one year  

Example: A 55-year-old diabetic patient with high BP and low physical activity may be flagged as high-risk.

### 5️⃣ Visualize – Decision-Maker Dashboards 📊
Use **Power BI** connected to MongoDB to display:
- Heart disease risk by **age group, gender, and region**  
- Top predictors: **cholesterol, BP, diabetes, lifestyle**  
- Survey insights: how **diet and exercise patterns** affect heart risk  

Enables healthcare providers to focus on preventive strategies for high-risk populations.

## Jury Takeaway Flow 🩺
**Data Capture (Kaggle + NFHS) → Store (MongoDB) → Process (Python/dbt) → Analyze (ML Models) → Visualize (Power BI)**
