## 🚀 Project Progress & Milestones

### ✅ Milestone 1 — Data Collection, Cleaning & Feature Engineering

* Collected and finalized exoplanet datasets from reliable scientific sources.
* Performed missing-value treatment for numerical and categorical attributes.
* Removed highly incomplete columns and handled inconsistent entries.
* Applied feature scaling and normalization.
* Engineered meaningful planetary and stellar features to improve model learning.
* Conducted Exploratory Data Analysis (EDA) using statistical summaries and visualizations.
* Analyzed data distributions, feature relationships, and initial habitability trends.
* Prepared a clean, consistent, and machine-learning-ready dataset.

---

### ✅ Milestone 2 — Machine Learning Model Development

Implemented and evaluated multiple baseline classification models:

* **Logistic Regression**
* **K-Nearest Neighbors (KNN)**
* **Naive Bayes**

#### Class Imbalance Handling

The dataset contained a severe imbalance between habitable and non-habitable planets. To address this:

* Applied **SMOTE (Synthetic Minority Over-sampling Technique)** only to the training data.
* Retrained baseline models using the balanced dataset.
* Compared model performance using **Accuracy, Precision, Recall, and F1-score**.
* Observed improved minority-class recall after applying SMOTE.
* Logistic Regression demonstrated the strongest baseline performance.

#### Dimensionality Reduction & Visualization

* **Principal Component Analysis (PCA)**
* **t-SNE**

These techniques were used to understand feature structure, class overlap, and the distribution of habitable and non-habitable planets.

#### Model Pipeline

Built an end-to-end ML pipeline incorporating:

```text
Data Cleaning
     ↓
Feature Engineering
     ↓
Feature Scaling
     ↓
Train/Test Split
     ↓
SMOTE
     ↓
Model Training
     ↓
Model Evaluation
     ↓
Prediction
```

SMOTE was applied only to training data to prevent data leakage.

---

### ✅ Milestone 3 — Backend, API & Frontend Integration

Developed the application layer for real-time habitability prediction.

#### Backend

* Developed **Flask REST APIs**.
* Integrated the trained machine learning model with the backend.
* Implemented endpoints for receiving exoplanet parameters.
* Generated habitability predictions through model inference.
* Returned standardized **JSON responses**.
* Connected backend services with frontend components.

#### Frontend

Built a responsive web interface using:

* HTML
* CSS
* Bootstrap

Users can:

* Enter exoplanet and stellar parameters.
* Generate habitability predictions.
* View **Habitable / Non-Habitable** classification.
* View habitability scores and planet rankings.
* Visualize key features influencing habitability.

---

### ✅ Milestone 4 — Documentation

Created comprehensive technical documentation covering:

* Project overview and objectives
* Technology stack
* Dataset description
* Data preprocessing
* Feature engineering
* Machine learning pipeline
* Model workflow
* System architecture
* Backend–frontend integration
* API workflow
* Deployment process
* Setup and usage instructions

The documentation was reviewed to ensure consistency with the implemented system.

---

## 📊 Current Status

| Component                 | Status      |
| ------------------------- | ----------- |
| Dataset Collection        | ✅ Completed |
| Data Cleaning             | ✅ Completed |
| Feature Engineering       | ✅ Completed |
| Exploratory Data Analysis | ✅ Completed |
| Class Imbalance Handling  | ✅ Completed |
| Baseline ML Models        | ✅ Completed |
| PCA & t-SNE               | ✅ Completed |
| ML Pipeline               | ✅ Completed |
| Flask REST API            | ✅ Completed |
| ML Model Integration      | ✅ Completed |
| Frontend Integration      | ✅ Completed |
| Documentation             | ✅ Completed |

