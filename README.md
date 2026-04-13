
# 🚖 Smart Taxi Demand Prediction and Recommendation System

This project develops a smart system to predict taxi demand and recommend the best available taxis to users based on various factors like estimated time of arrival (ETA), predicted demand, and congestion.

---

## 📌 Project Overview

The system processes large volumes of NYC taxi trip data, extracts meaningful features, builds predictive models using Machine Learning (ML) and Reinforcement Learning (RL) techniques (DQN, A2C, PPO), and provides an interactive recommendation interface with map visualization.

---

## ⚙️ Features

- 📂 **Data Loading & Cleaning:** Efficiently reads and cleans multiple large CSV files using chunk processing.  
- 🧠 **Feature Engineering:** Creates relevant features such as trip duration, time-based features (hour, day, month), speed, and traffic congestion.  
- 🗺️ **Zone Creation:** Uses K-Means clustering to divide the city into geographical zones for localized analysis.  
- 📊 **Demand Aggregation:** Aggregates taxi demand and availability per zone and hour.  
- 🤖 **Machine Learning Models:** Trains and evaluates Linear Regression, Decision Tree, and Random Forest models for demand prediction.  
- 🧪 **Deep Reinforcement Learning Models:** Implements and trains DQN, A2C, and PPO agents for optimal taxi recommendations.  
- 🔗 **Hybrid Recommendation System:** Combines insights from both ML and RL models for robust recommendations.  
- 📍 **Interactive Map Visualization:** Displays recommended taxis and user location on an interactive Folium map.  

---

## 🧮 Models Used

### 📈 Supervised Learning for Demand Prediction
- Linear Regression  
- Decision Tree Regressor  
- Random Forest Regressor (chosen as best_model)  

### 🎯 Reinforcement Learning for Taxi Recommendation
- Deep Q-Network (DQN)  
- Advantage Actor-Critic (A2C)  
- Proximal Policy Optimization (PPO)  

### 🔀 Hybrid Model
A weighted combination of Random Forest and DQN scores for a comprehensive recommendation.

---

## 🛠️ Setup and Usage

### 1️⃣ Data Preparation

Mount Google Drive:
```python
from google.colab import drive
drive.mount('/content/drive')
````

Create Data Folder: Ensure your Google Drive has a folder named `NYC_DATA` containing the `yellow_tripdata_YYYY-MM.csv` files.

Example structure:

```
/content/drive/MyDrive/NYC_DATA/yellow_tripdata_2015-01.csv
```

---

### 2️⃣ Run the Notebook

Execute all cells in the Colab notebook sequentially. The notebook will:

* Import necessary libraries
* Load and clean taxi trip data
* Engineer features
* Create zones using K-Means clustering
* Aggregate demand and availability
* Train ML models (Linear Regression, Decision Tree, Random Forest)
* Train RL models (DQN, A2C, PPO)
* Take user input
* Generate taxi recommendations (RF, DQN, Hybrid)
* Visualize results on a map

---

### 3️⃣ User Input

When prompted, enter:

* 📍 Latitude (e.g., 40.7851)
* 📍 Longitude (e.g., -73.9683)
* ⏱️ Max wait time (minutes) (e.g., 10)
* 🕒 Pickup hour (0–23) (e.g., 10)

---

### 4️⃣ Output

The system displays top 10 recommended taxis based on Random Forest, DQN, and Hybrid models:

* 🏆 Rank
* 📍 Latitude
* 📍 Longitude
* ⏱️ ETA (minutes)
* 📊 Demand
* ⭐ Score

An interactive map is also shown with user location and recommended taxis connected visually.

---

## 📁 File Structure

* 📄 `yellow_tripdata_YYYY-MM.csv` – Raw NYC taxi data
* 📄 `cleaned_taxi.csv` – Processed dataset
* 📄 `kmeans_model.pkl` – K-Means model
* 📄 `random_forest_model.pkl` – Random Forest model
* 📄 `minmax_scaler.pkl` – Feature scaler
* 📄 `preprocessed_data.csv` – Final dataset
* 📄 `availability_data.csv` – Availability data
* 📄 `dqn_model_state.pth` – DQN model
* 📄 `a2c_model_state.pth` – A2C model
* 📄 `ppo_model_state.pth` – PPO model

---

## 💻 Technologies

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy
* 🤖 Scikit-learn
* 🔥 PyTorch
* 📊 Matplotlib
* 🎨 Seaborn
* 🗺️ Folium

```
```
