# 🍔 Food Delivery Time Prediction

Predicting how long a food delivery will take, using regression models trained on 1,000 real order records — with a full exploratory analysis of what actually causes delays.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📖 Overview

Food delivery apps need to give customers an accurate ETA. This project explores a real-world-style delivery dataset to answer two questions:

1. **What factors actually slow deliveries down?** (distance, traffic, weather, courier experience, etc.)
2. **Can we predict delivery time in minutes, given an order's details?**

The notebook walks through the full pipeline — cleaning the data, exploring it visually, and training/comparing two regression models to make that prediction.

## 📂 Dataset

| Detail    | Info                                                               |
|-----------|---------------------------------------------------------------------|
| File      | `Food_Delivery_Times.csv`                                            |
| Size      | 1,000 orders                                                          |
| Target    | `Delivery_Time_min` — total delivery time in minutes                   |
| Features  | Distance, Weather, Traffic Level, Vehicle Type, Preparation Time, Courier Experience |

## 🔍 Workflow

| Step                          | What happens                                                                 |
|--------------------------------|-------------------------------------------------------------------------------|
| 1. Data Cleaning                | Handle missing values, remove duplicates, drop the non-predictive `Order_ID` column |
| 2. Exploratory Data Analysis    | Visualize the distribution of delivery times and how each feature relates to it, plus a correlation heatmap |
| 3. Encoding                     | Convert categorical columns (Weather, Traffic, Vehicle) into numbers using `LabelEncoder` |
| 4. Model Training                | Train a **Linear Regression** model and a **Random Forest Regressor**, using an 80/20 train-test split |
| 5. Evaluation                    | Compare both models on MAE, RMSE, and R² |
| 6. Feature Importance            | Use the Random Forest model to rank which features matter most |

## 📊 Results

| Model                | MAE      | RMSE      | R²        |
|------------------------|----------|-----------|-----------|
| Linear Regression        | 7.29     | 10.45     | 0.756     |
| **Random Forest**        | **7.06** | **10.01** | **0.777** |

**Random Forest wins** on every metric. Its feature importance ranking also shows that **Distance** and **Preparation Time** are by far the biggest drivers of delivery time — more than traffic or weather.

## 🛠️ Tech Stack

`Python` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` · `Jupyter Notebook`

## 🚀 Running it locally

```bash
# 1. Clone the repo
git clone https://github.com/aditya-datahub/food-delivery-time-prediction.git
cd food-delivery-time-prediction

# 2. Install the dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# 3. Open the notebook
jupyter notebook delivery_time_prediction.ipynb
```

## 📁 Repository Structure

```
food-delivery-time-prediction/
├── delivery_time_prediction.ipynb   # Cleaning, EDA, modeling, evaluation — all in one notebook
├── Food_Delivery_Times.csv          # Raw dataset used in the notebook
├── LICENSE
└── README.md
```

## 📈 Possible Next Steps

- Tune the Random Forest with `GridSearchCV` to squeeze out a better R²
- Try gradient-boosted models like XGBoost or LightGBM for comparison
- Wrap the trained model in a simple API so it can return live predictions

## 📄 License

Released under the [MIT License](LICENSE).
