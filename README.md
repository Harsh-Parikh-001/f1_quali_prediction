# Formula 1 Qualifying Time and Grid Position Prediction (2025 Season)

This project explores the use of machine learning to predict Formula 1 qualifying times and, by extension, the starting grid position of drivers based on data collected during free practice sessions. The main goal was to assess whether insights from practice sessions could be leveraged to forecast driver performance in qualifying rounds (Q1, Q2, and Q3).

Due to the lack of publicly available datasets that combine free practice and qualifying data in a structured format, this project uses a custom data generation pipeline built using the [FastF1](https://github.com/theOehrly/Fast-F1) API.

---

## 📌 Project Motivation

Formula 1 teams and analysts are always looking for ways to extract performance trends and make early predictions. In this project, the question was simple:

> Can we predict a driver's qualifying time using only their free practice session data?

By generating detailed datasets and training machine learning models, this project attempts to answer that question.

---

## 🔍 What This Project Does

- Collects free practice data for all drivers across the 2025 F1 season using the FastF1 API.
- Aggregates lap-level data into driver-level summaries for each Grand Prix.
- Creates multiple datasets from the same sessions by filtering laps based on performance thresholds (e.g., top 75%, top 5%).
- Trains separate machine learning models for Q1, Q2, and Q3 qualifying sessions.
- Makes predictions for a selected Grand Prix (the Japanese GP) and evaluates model performance.

---

## 🧠 Machine Learning Models Used

Two main algorithms were used:

- **Support Vector Regression (SVR)**: Chosen for its robustness in handling small and medium-sized regression problems.
- **XGBoost Regressor**: A powerful gradient-boosting algorithm that handles non-linearities well and is widely used in tabular data problems.

The models are trained using different versions of the dataset to test how data filtering affects model accuracy.

---

## 📊 Dataset Details

Each file (file_Q1, file_Q2, file_Q3) contains aggregated information for each driver per Grand Prix:

- **Lap Time Statistics:**
  - Mean Lap Time
  - Median Lap Time
  - Standard Deviation
  - Minimum and Maximum Lap Time

- **Performance Metrics:**
  - Speed at various track segments (e.g., finish line)
  - Tyre compound
  - Tyre life

- **Track and Driver Grouping:** Each row represents a unique driver and GP combination.


**Additionally, the datasets were filtered to create:**
- A full dataset (all laps)
- A top 75% dataset (removing slowest 25% laps)
- A top 5% dataset (only best laps)

This allowed testing if training on higher-quality laps improves model accuracy.

---
There is a lot of refactoring to be done here. Which I will do in the future
Thanks for checking out the project feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/harshparikh001/)
