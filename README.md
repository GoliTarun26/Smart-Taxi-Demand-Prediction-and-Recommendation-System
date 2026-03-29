# 🚖 Smart Taxi Demand Prediction & Recommendation System

## 📌 Overview

This project implements a **Smart Taxi Demand Prediction and Recommendation System** that helps taxi drivers identify optimal pick-up locations based on predicted demand, travel time, and congestion.

The system combines **Machine Learning** and **Reinforcement Learning (DQN)** to provide intelligent and efficient taxi recommendations.

---

## 🎯 Objectives

* Predict taxi demand across different city zones
* Optimize driver decisions for pick-up locations
* Minimize passenger wait time and driver idle time
* Compare ML-based recommendations with Reinforcement Learning (DQN)

---

## 📊 Dataset

* NYC Taxi Trip Data (multiple large CSV files)
* Includes:

  * Pickup & Dropoff coordinates
  * Timestamps
  * Trip distance
  * Fare details

---

## ⚙️ Workflow

### 1. Data Loading & Cleaning

* Loaded large datasets in chunks for memory efficiency
* Removed null and invalid records
* Converted datetime columns properly
* Filtered unrealistic trips (zero distance, invalid coordinates)

---

### 2. Feature Engineering

Created meaningful features:

* `trip_duration`
* `pickup_hour`, `pickup_day`, `pickup_month`
* `speed`
* `traffic_congestion`

---

### 3. Zone Creation (K-Means Clustering)

* Applied K-Means clustering on pickup latitude & longitude
* Segmented city into multiple zones
* Each zone represents a demand region

---

### 4. Demand Aggregation

* Aggregated:

  * Demand per zone per hour
  * Taxi availability
  * Average congestion
* Merged all features into a single dataset

---

### 5. Machine Learning Models

Trained multiple models:

* Linear Regression
* Decision Tree
* Random Forest ✅ (Best Performer)

📌 **Why Random Forest?**

* Handles non-linearity
* Robust to noise
* Provides higher prediction accuracy

---

### 6. Recommendation System (ML-Based)

Given:

* User location
* Pickup hour
* Maximum wait time

The system:

1. Finds nearby taxis

2. Estimates travel time

3. Predicts demand using Random Forest

4. Computes a **Smart Score**:

   score = predicted_demand / (estimated_time + 1)

5. Ranks taxis based on score

---

### 7. Deep Q-Network (DQN) Model

* Implemented using **PyTorch**
* Learns optimal taxi selection policy

#### 🔹 State Space:

* Distance
* Estimated time
* Traffic congestion
* Predicted demand

#### 🔹 Reward Function:

* Rewards:

  * High demand areas
* Penalties:

  * Long travel time
  * High congestion
  * Large distance

#### 🔹 Output:

* Q-values used to rank taxis

---

## 🔍 ML vs DQN Comparison

| Feature       | ML (Random Forest) | DQN                    |
| ------------- | ------------------ | ---------------------- |
| Approach      | Supervised         | Reinforcement Learning |
| Learning Type | Static             | Dynamic                |
| Adaptability  | Low                | High                   |
| Complexity    | Moderate           | High                   |

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* PyTorch
* Matplotlib, Seaborn

---

## 📈 Key Benefits

* Reduces driver idle time
* Improves revenue opportunities
* Enables smarter urban mobility decisions
* Scalable for real-time systems

---

## 🚀 Future Improvements

* Real-time GPS integration
* Live traffic API integration
* Dynamic pricing model
* Deployment using cloud (Azure / AWS)

---

## 👨‍💻 Author

Tarun Goli

---

## 📌 Conclusion

This project demonstrates how **data science + reinforcement learning** can transform traditional taxi systems into intelligent, adaptive, and efficient mobility solutions.

---
