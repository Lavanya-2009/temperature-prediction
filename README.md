# 🌡️ Next-Day Environmental Temperature Prediction

## 📌 Project Overview

This project was developed as part of the technical assessment for **Qute Electronics**.

The objective is to accurately predict environmental temperature using data generated from a virtual sensor system. A machine learning-based forecasting framework was developed using synthetic environmental data and evaluated through multiple experiments.

The project demonstrates:

* Virtual sensor design and simulation
* Synthetic environmental data generation
* Data visualization and exploratory analysis
* Feature engineering
* Machine learning-based temperature forecasting
* Performance comparison between single-sensor and multi-sensor approaches

---

## 🎯 Problem Statement

Predict the next environmental temperature using data generated from virtual sensors.

### Objectives

* Generate realistic environmental sensor data.
* Build a baseline temperature prediction model.
* Improve prediction accuracy using additional environmental factors.
* Analyze feature importance and model behavior.
* Achieve high forecasting accuracy (>90%).

---

## 🔧 Virtual Environmental Sensor System

A virtual sensing framework was developed to simulate environmental measurements over a period of 30 days with hourly sampling.

### Simulated Sensors

| Sensor               | Unit |
| -------------------- | ---- |
| Temperature          | °C   |
| Humidity             | %    |
| Atmospheric Pressure | hPa  |
| Light Intensity      | Lux  |

The generated data incorporates:

* Daily temperature cycles
* Day–night light variations
* Temperature-humidity relationships
* Atmospheric pressure fluctuations
* Random environmental noise

---

## 📊 Dataset Summary

| Attribute       | Description               |
| --------------- | ------------------------- |
| Timestamp       | Measurement timestamp     |
| Temperature     | Environmental temperature |
| Humidity        | Relative humidity         |
| Pressure        | Atmospheric pressure      |
| Light_Intensity | Simulated solar intensity |

### Dataset Statistics

* Duration: 30 Days
* Frequency: Hourly
* Total Records: 720

---

## 🧪 Experiment 1: Baseline Model

### Features

* Hour
* Day
* Temp_Lag_1
* Temp_Lag_24
* Temp_Rolling_24

### Model

Random Forest Regressor

### Results

| Metric   | Score     |
| -------- | --------- |
| MAE      | 0.772     |
| RMSE     | 0.997     |
| R² Score | **0.954** |

### Key Observation

Feature importance analysis showed that the model relied primarily on the previous day's temperature at the same hour (Temp_Lag_24), indicating strong periodic behavior in environmental temperature patterns.

---

## 🌍 Experiment 2: Multi-Sensor Model

Additional environmental information was incorporated to improve forecasting performance.

### Additional Features

* Humidity
* Pressure
* Light Intensity

### Model

Random Forest Regressor

### Results

| Metric   | Score     |
| -------- | --------- |
| MAE      | **0.694** |
| RMSE     | **0.867** |
| R² Score | **0.968** |

### Feature Importance

| Feature         | Importance |
| --------------- | ---------- |
| Humidity        | 58.89%     |
| Light Intensity | 19.61%     |
| Temp_Lag_1      | 18.29%     |
| Hour            | 1.44%      |

### Key Observation

The multi-sensor model leveraged environmental context rather than relying solely on historical temperature values, resulting in improved prediction performance.

---

## 📈 Model Performance Comparison

| Model                  | MAE       | RMSE      | R² Score  |
| ---------------------- | --------- | --------- | --------- |
| Temperature-Only Model | 0.772     | 0.997     | 0.954     |
| Multi-Sensor Model     | **0.694** | **0.867** | **0.968** |

### Improvement Achieved

✅ 10.1% reduction in MAE

✅ 13.0% reduction in RMSE

✅ Improved forecasting accuracy using multi-sensor data fusion

---

## 📷 Visualizations

The project includes:

* Temperature Variation Over Time
* Multi-Sensor Trend Analysis
* Correlation Heatmap
* Actual vs Predicted Temperature
* Feature Importance Analysis

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Jupyter Notebook

---

## 📂 Repository Structure

```text
temperature-prediction/
│
├── data/
│   ├── temperature_sensor_data.csv
│   └── environmental_sensor_data.csv
│
├── notebook/
│   └── temperature_prediction.ipynb
│
├── plots/
│   ├── temperature_variation.png
│   ├── sensor_plots.png
│   ├── correlation_matrix.png
│   └── actual_vs_predicted.png
│
├── requirements.txt
├── README.md
└── report.pdf
```

---

## 🚀 How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
temperature_prediction.ipynb
```

and execute all cells.

---

## ✅ Conclusion

A virtual environmental sensing system was successfully developed to generate realistic synthetic weather data. Two machine learning models were evaluated for temperature forecasting.

The baseline model achieved an R² score of **0.954**, while the enhanced multi-sensor model achieved an R² score of **0.968**.

The results demonstrate that integrating multiple environmental sensors significantly improves temperature prediction performance and provides a more robust forecasting framework.
