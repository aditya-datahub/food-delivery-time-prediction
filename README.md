# 🍔 Food Delivery Time Prediction

Predicting food delivery time using regression models, with exploratory data analysis on 1,000 orders to understand what actually drives delivery delays.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Objective

Understand what factors affect food delivery time and build a regression model that predicts delivery time (in minutes) for a new order, based on features like distance, weather, traffic, vehicle type, and courier experience.

## 📂 Dataset

| Detail       | Info                                                              |
|--------------|--------------------------------------------------------------------|
| Source       | `Food_Delivery_Times.csv`                                          |
| Rows         | 1,000 orders                                                        |
| Target       | `Delivery_Time_min`                                                  |
| Features     | Distance, Weather, Traffic, Vehicle, Preparation Time, Experience   |
| Task         | Regression (predict delivery time in minutes)                       |

## 🔍 Approach

1. **Data Cleaning** — handled missing values, removed duplicates, dropped non-informative columns (`Order_ID`)
2. **Exploratory Data Analysis** — distribution of delivery times, feature relationships, correlation heatmap
3. **Encoding** — categorical variables converted using `LabelEncoder`
4. **Modeling** — trained and compared two regression models:
   - Linear Regression
   - Random Forest Regressor
5. **Evaluation** — compared models using MAE, RMSE, and R²
6. **Feature Importance** — identified which features most influence delivery time

## 📊 Results

| Model              | MAE  | RMSE  | R²    |
|---------------------|------|-------|-------|
| Linear Regression    | 7.29 | 10.45 | 0.756 |
| **Random Forest**    | **7.06** | **10.01** | **0.777** |

**Random Forest** outperformed Linear Regression across all metrics. Feature importance analysis showed that **Distance** and **Preparation Time** are the strongest predictors of delivery time.

## 🛠️ Tech Stack

- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

## 🚀 How to Run

```bash
# Clone the repo
git clone https://github.com/aditya-datahub/food-delivery-time-prediction.git
cd food-delivery-time-prediction

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# Launch the notebook
jupyter notebook delivery_time_prediction.ipynb
```

## 📁 Project Structure

```
food-delivery-time-prediction/
├── delivery_time_prediction.ipynb   # Full analysis & modeling notebook
├── Food_Delivery_Times.csv          # Raw dataset
├── LICENSE
└── README.md
```

## 📈 Future Improvements

- Hyperparameter tuning (GridSearchCV) for Random Forest
- Try gradient boosting models (XGBoost, LightGBM)
- Deploy as a simple API/web app for live predictions

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
