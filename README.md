
Name - Soumya
Degree - B.E
College - NCET Bangalore
Branch/yr. - CSE 3rd Year
Data science experience : No




Fronted image





Backend:












MILESTONE 1 – COMPLETED
(Module 1: Data Collection & Module 2: Data Cleaning and Feature Engineering)
Collected and finalized the exoplanet dataset from reliable scientific sources.
Performed missing value treatment using appropriate statistical techniques for numerical and categorical attributes.
Applied feature scaling and normalization to ensure uniform data distribution for machine learning models.
Engineered meaningful features related to planetary and stellar properties to enhance model learning.
Conducted Exploratory Data Analysis (EDA) using statistical summaries and visualizations to understand:
Data distribution
Feature relationships
Initial trends related to habitability
Prepared a clean, consistent, and model‑ready dataset.

 MILESTONE 2 –  COMPLETED
Implemented multiple baseline machine learning classifiers to establish initial performance benchmarks:
Logistic Regression
K‑Nearest Neighbors (KNN)
Naive Bayes
Compared baseline models using standard classification metrics.
Identified Logistic Regression as the strongest baseline model based on balanced performance.
Addressed severe class imbalance using SMOTE (Synthetic Minority Over‑sampling Technique) applied only to training data.
Re‑trained baseline models on the SMOTE‑balanced dataset to improve minority class prediction.
Performed dimensionality reduction and visualization using:
Principal Component Analysis (PCA).
Confusion matrix
[ [799  0  0 ]
  [0      3   1]
  [1      0    6] ]
“Initial column mismatches occurred due to schema differences in the NASA Exoplanet dataset. After aligning features with actual column names, the Random Forest model trained successfully with ~99.8% accuracy.”
“The trained machine learning model was serialized using Joblib and stored as a binary .pkl file. This format is optimized for fast loading during inference and is not intended for human readability.”


Milestone 3
I developed the Flask backend APIs to accept exoplanet input data and generate habitability predictions with ranking. The backend was connected to the database for dynamic data handling and returned secure JSON responses. A responsive frontend was built using HTML, CSS, and Bootstrap to allow users to enter planetary details and view results.
User can enter exoplanet parameters through the web interface.
The system displays the habitability prediction (habitable / non-habitable).
Habitability score and ranking of planets are shown.
Key features influencing habitability are visualized clearly on the UI.





Module 1: Data Collection and Management
Week 1 : Day 1
Data set link 1
https://www.kaggle.com/datasets/gauravkumar2525/kepler-exoplanet-dataset
The dataset mainly focuses on  Kepler Objects of Interest (KOIs)
There are total of 12 columns and 9565 rows.
The dataset appears uniform in structure
It is well-suited for exploratory analysis..
This dataset is good for basic classification but it cannot be used to study whether planets can support life or to understand their physical properties.
Question: Are there any outliers (extremely large or small values) that may affect model training?

Data set link 2:
 https://www.kaggle.com/datasets/chandrimad31/phl-exoplanet-catalog
The data set contains more than 50 columns and 4049 rows.
The dataset includes multi-source measurements.
Since the dataset is updated regularly, it supports long-term trend analysis and time-based studies.
It is suitable for research on detection techniques.
Question:How do planetary and stellar parameters differ across detection techniques?






Week 1 Day 2 : No Class 
Week 1 Day 3 : 03/12/2025
Data set link 3:https://www.kaggle.com/datasets/shivamb/all-exoplanets-dataset
Observations:
 Total Rows: 4048
Total Columns: 112
Type of Data: Planetary + Stellar + System Features
Data Source: University of Puerto Rico / PHL, published on Kaggle
Use Case: Habitability analysis, clustering, classification, feature study
Provides both planetary and star-level data.
Easier to use for ML because the dataset is structured and compact.
Ideal for computing habitability scores and performing EDA.
Performed an initial overview of:
Shape (rows × columns)
Data types
Missing values
Duplicate entries
Question: 
Will preprocessing be done inside the program? 
Does the dataset have a pre-labeled “Habitable” column?

Week 1 Day 4 : 05/12/2025
Our dataset is imbalanced because we have many non-habitable planets (0s) and very few habitable planets (1s and 2s).
To fix this, I explored different techniques that can help balance the classes and improve model performance.
1. Resampling Methods
a) Oversampling
Increases the number of samples in the minority class.
Random oversampling simply duplicates minority samples → this can cause overfitting and bias.
b) Undersampling
Reduces the number of samples in the majority class.
Works fast but may remove useful information.
 Comment:Just adding or removing data is a temporary fix. It may still create bias or make the model unstable.
2. SMOTE (Synthetic Minority Oversampling Technique)
Smote is an improved oversampling technique.
 Instead of copying samples, it:
Creates synthetic, new minority samples
Uses nearest neighbours
Generates samples that are similar but not identical


Why SMOTE is better than random oversampling?
It avoids exact duplicates
Reduces overfitting
Helps the model generalize better
Produces more realistic class balance


Limitation:
 Sometimes SMOTE may generate unrealistic samples if the dataset is noisy.
 3. Combination: SMOTE + Undersampling
A more balanced approach is to use SMOTE first and then light undersampling.
SMOTE → Adds new synthetic habitable planet samples
Undersampling → Removes a small number of non-habitable samples
But not too much, so important information is not lost
SMOTEENN
SMOTETomek
These methods:
Balance the dataset
Remove noisy or overlapping samples
Improve data quality and model accuracy
4. Class Weighting (Random Forest / XGBoost)
Instead of changing the dataset, some models allow us to adjust the importance of classes.
We can assign higher weight to the minority classes (1s and 2s)
Models like Random Forest and XGBoost can automatically handle imbalance
Helps the model focus more on rare classes without modifying the data
This is useful for datasets where habitable planets are naturally very rare
 5. Creating Labels Based on Features 
We could try creating the “habitable” label based on temperature, radius, gravity, etc.
 But this is risky because:
It may introduce wrong assumptions
We might create labels that don’t match real-world data
It can lead to model mistakes
So it’s better to use real labeled data.
                                              WEEK 2

Week 2 day 1:
Descriptive statistics help us understand and summarize a dataset.
They provide simple information about how the data is spread, how it behaves, and how each value compares to others.
Descriptive statistics mainly include:
1. Central Tendency
These show the center or average of the data.
• Mean:The average value of all numbers.
• Median:The middle value when data is arranged in order.
 Useful when data has extreme values (outliers).
2. Variability
These tell us how spread out the data is.
• Standard Deviation (SD)
Shows how far values are from the mean.
 High SD → data is widely spread
 Low SD → data is close together
• Range
Difference between the highest and lowest value.
 Gives a simple idea of spread.
3. Position
These show the relative standing of a value in a dataset.
• Percentiles
A percentile tells you the value below which a certain percent of data lies.
 Example:
 90th percentile = value below which 90% of observations fall.
Useful for:
Finding outliers
Ranking students
Measuring income levels
Understanding distribution shape

       Week 2  Data Cleaning and Feature Engineering

Day 1 – 08/12/2025
Work Done: Reading research papers
Read and studied research papers, articles, and Kaggle notebooks related to exoplanet detection using machine learning. Learned how light curve data is cleaned and transformed before modeling. Understood the use of PCA, FFT, and TSFresh for feature extraction. Observed that SMOTE is commonly used to handle imbalanced data and that models like SVM, LightGBM, Random Forest, CNN, and ANN give good results when features are properly engineered.

Day 2 – 09/12/2025
Work Done: Planning ML process
Created a step-by-step machine learning workflow. The steps include data cleaning, feature transformation, dimensionality reduction, handling class imbalance, model training, and evaluation. Learned the importance of using metrics like recall, PR curves, and cross-validation for imbalanced datasets.

Day 3 – 10/12/2025
Work Done: Git/GitHub and dataset overview
Learned how to use Git and GitHub for collaboration. Forked and cloned the repository and made the first commit. Loaded the PHL Exoplanet dataset and checked its shape, columns, data types, memory usage, and basic statistics.

Day 4 – 11/12/2025
Work Done: Data cleaning
Checked missing values in all columns and calculated their percentages. Removed columns with more than 75% missing values to reduce noise. Visualized missing data using heatmaps and separated numerical and categorical columns. Created a cleaner dataset for further work.



Week 3 Checkpoints 
Cleaned the dataset by handling missing values, outliers, and inconsistent entries.
Encoded categorical variables and performed exploratory data analysis (EDA).
Applied feature scaling and Principal Component Analysis (PCA).
Split the dataset into training and testing sets for modeling.
Evaluated baseline models to understand model flow and performance.

Module 4: AI Model for Habitability Prediction 

Week 4 Day 1 : 22/12/2025
Work Done: Baseline Model Training
On this day, I trained baseline machine learning models on the cleaned and preprocessed exoplanet dataset. The dataset was still imbalanced at this stage.
Models used:
Logistic Regression


K-Nearest Neighbors (KNN)


Naive Bayes


The purpose of using baseline models was to understand the basic model flow and initial   performance.
 Model evaluation was done using accuracy, precision, recall, and F1-score.
Observation:
High accuracy was observed for all models.


Recall for the minority (habitable) class was low.


Logistic Regression performed better compared to KNN and Naive Bayes.



Week 4 Day 2 : 23/12/2025
Work Done: Applying SMOTE and Model Retraining
To handle class imbalance, SMOTE was applied only to the training dataset after splitting.
 This helped balance the number of habitable and non-habitable samples.
After applying SMOTE:
The same baseline models were retrained.


Model performance was re-evaluated using classification metrics.


Observation:
Recall for the minority class improved.


Logistic Regression continued to perform better among baseline models.



Week 4 Day 3 : 24/12/2025
Work Done: Dimensionality Reduction and Visualization
Performed dimensionality reduction techniques to understand the structure of the dataset.
Techniques used:
Principal Component Analysis (PCA)


t-SNE visualization


Findings:
Habitable planets were rare and showed similar feature patterns.


Non-habitable planets were more diverse.


Significant overlap between classes explained the difficulty in classification.



Week 4 Day 4 : 25/12/2025
Christmas Holiday

Week 4 Day 5 : 26/12/2025
Work Done: ML Pipeline Development
Built a complete machine learning pipeline that includes:
Feature scaling


Sampling techniques


Model training


Used stratified splitting to ensure class balance during validation.
 Ensured that SMOTE was applied only on training data to avoid data leakage.


Week 4 Checkpoint
Baseline models were trained and evaluated


Class imbalance was handled using SMOTE


PCA and t-SNE were used for data visualization


ML pipeline was successfully built


Logistic Regression identified as the best baseline model.




 Current Status
Foundational data processing and baseline modeling stages are complete.
Dataset imbalance has been effectively addressed.
The project is now well‑prepared for advanced model pipelines and deployment stages.

1. What is a REST API?
A REST API (Representational State Transfer Application Programming Interface) acts as a communication layer between a client and a server. When a user performs an action, the client sends an HTTP request (GET, POST, PUT, DELETE) to the server through the REST API. The server processes the request, retrieves or updates data, and returns a response, usually in JSON format.
REST APIs are stateless, meaning each request contains all the required information. This makes them fast, scalable, and suitable for web, mobile, and AI-based applications.

2. What is a Synchronous Request and an Asynchronous Request?
Synchronous Request:
In a synchronous request, the client waits until the server completes processing and sends a response. During this time, the execution is blocked and no other tasks can be performed.
Asynchronous Request:
In an asynchronous request, the client does not wait for the server response. It continues executing other tasks while the request is being processed. Once the response is ready, it is handled using callbacks, promises, or async/await mechanisms.

3. Difference between Multithreading and Concurrency
Multithreading:
Multithreading allows a program to execute multiple threads simultaneously within a single process. Each thread performs a part of the task independently, enabling parallel execution on multi-core systems.
Concurrency:
Concurrency refers to the ability of a system to manage multiple tasks at the same time by switching between them. Tasks may not execute simultaneously but appear to run together due to rapid context switching.

4. How Many Threads Can Run in Parallel?
The number of threads that can run truly in parallel depends on the number of CPU cores (or logical cores with hyperthreading).
Example:
On a 16-core processor, a maximum of 16 threads can run in parallel.


Additional threads are time-sliced by the operating system.



5. How Many Concurrent Tasks Can Run?
A system can manage a very large number of concurrent tasks. However, only a limited number can execute in parallel based on available CPU cores.
Tasks may be waiting for I/O, network, or timers


The OS scheduler switches between tasks


This enables thousands or even millions of concurrent tasks



6. Difference Between Flask and FastAPI
Flask:
Flask is a lightweight, synchronous Python web framework used to build web applications and REST APIs. It follows a minimal and flexible design, requiring manual setup for validation, authentication, and documentation.
FastAPI:
FastAPI is a modern, high-performance Python framework designed for building asynchronous REST APIs. It uses ASGI and supports native async/await, making it efficient for handling high traffic and I/O-bound operations.
Feature
Flask
FastAPI
Type
Micro framework
Modern async framework
Execution
Synchronous
Asynchronous
Performance
Moderate
Very high
Async support
Limited
Native
Data validation
Manual
Automatic
API docs
Manual
Auto (Swagger)
Best suited for
Small apps
High-performance APIs

Why FastAPI over Flask?
 FastAPI provides better performance, built-in async support, automatic validation, and auto-generated API documentation.
7. What is Throughput?
Throughput is the number of tasks, requests, or transactions a system can successfully process in a given time period.
Examples:
A REST API handling 1000 requests per second → 1000 RPS


A database completing 500 transactions per minute → 500 TPM


In web applications, throughput indicates system efficiency under load.
8. What is Inference Speed?
Inference speed is the time taken by a trained machine learning model to generate an output for a given input. It measures how fast predictions are produced after training.
Inference speed is critical for real-time applications such as recommendation systems, fraud detection, and AI-based web services.

Milestone 3 : Week 5-6
Module 5: Flask Backend API
Work Done: Backend API Development and ML Integration
Developed backend APIs and integrated the machine learning model with the application. Implemented RESTful endpoints to accept user input data and return prediction results in JSON format. Established initial integration between the backend services and the frontend interface.
Key Activities:
Designed and implemented REST API endpoints for data input and prediction


Integrated trained ML model with backend for inference


Implemented standardized JSON response structure


Connected backend APIs with frontend components


Observation:
APIs successfully processed requests and returned predictions


JSON responses were structured correctly and consistently


Initial frontend–backend integration functioned as expected

Milestone 4
a comprehensive README file was created for the project. The README clearly explains the project overview, objectives, technology stack, setup instructions, usage steps, and key features of the application.
In addition to the README, detailed technical documentation was prepared, covering:
System architecture


Dataset description and preprocessing steps


Machine learning pipeline and model workflow


Backend–frontend integration


Deployment process
All documentation was carefully reviewed to ensure it is accurate, well-structured, and consistent with the implemented system.








                   
