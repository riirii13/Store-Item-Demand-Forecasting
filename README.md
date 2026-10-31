# Store Item Demand Forecasting Using Machine Learning

## 1. Project Overview

Store Item Demand Forecasting is a machine learning project that predicts future product sales using historical sales data. Accurate demand forecasting helps businesses understand customer demand, manage inventory and reduce overstocking or shortages.

This project uses historical sales records from 10 stores and 50 different items between 2013 and 2017. Two machine learning algorithms are implemented and compared to identify the better-performing model. The selected model is then used to forecast sales for January 2018.

## 2. Project Objectives

- Analyse historical store sales data.
- Identify sales patterns and trends.
- Apply machine learning algorithms for demand prediction.
- Compare model performance using evaluation metrics.
- Generate future sales predictions.

## 3. Dataset Description

The dataset is obtained from the Kaggle Store Item Demand Forecasting competition.

| Attribute | Description |
|---|---|
| Date | Sales transaction date |
| Store | Store identification number |
| Item | Product identification number |
| Sales | Number of units sold |

- Training records: 913,000
- Test records: 45,000
- Stores: 10
- Products: 50
- Training period: 2013–2017

## 4. Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook / Kaggle Notebook
- GitHub

## 5. Data Preprocessing

The dataset was checked for missing values, duplicate records and incorrect data types. The date column was converted into datetime format.

Additional calendar features such as year, month, day and day of the week were extracted. These steps prepared the dataset for analysis and model training.

## 6. Exploratory Data Analysis

Exploratory Data Analysis was performed using graphs and visualisations to understand sales behaviour.

Key observations included:

- Store 2 recorded the highest total sales, while Store 7 recorded the lowest.
- Item 15 had the highest total sales, while Item 5 had the lowest.
- Weekend sales were generally higher than weekday sales.
- Sales varied across different months, with July showing relatively high sales.
- Overall sales showed an increasing trend from 2013 to 2017.

## 7. Feature Engineering

Additional features were created to improve prediction accuracy:

- Lag 1: Sales from the previous day.
- Lag 7: Sales from seven days earlier.
- Lag 14: Sales from fourteen days earlier.
- Rolling Mean 7: Average sales over the previous seven days.
- Calendar features: Year, month, day and day of the week.
- Weekend indicator: Identifies Saturdays and Sundays.

After feature engineering and removing rows with unavailable historical values, 906,000 records remained.

## 8. Machine Learning Algorithms

Two algorithms were implemented:

**1. Linear Regression**

Linear Regression was used as the baseline model. It learns the relationship between input features and sales values to predict future demand.

**2. Random Forest Regressor**

Random Forest is an ensemble learning algorithm that combines multiple decision trees. It captures complex relationships in the data and was used as the primary forecasting model.

## 9. Model Training and Evaluation

The dataset was divided chronologically into training and testing sets to evaluate the models on later dates.

The following evaluation metrics were used:

- MAE: Measures the average absolute prediction error.
- RMSE: Measures prediction error while giving higher weight to larger errors.
- R² Score: Measures how well the model explains variations in sales.

### Model Performance

| Algorithm | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | 6.981 | 9.131 | 0.916 |
| Random Forest | 6.480 | 8.445 | 0.928 |

Random Forest performed better across all three evaluation metrics and was selected for future sales forecasting.

## 10. Key Findings

- Random Forest achieved an R² score of 0.928.
- Rolling Mean 7 was the most important feature, contributing approximately 66.48% to feature importance.
- Lag 7 contributed approximately 25.92%.
- Historical sales patterns played a major role in predicting future demand.
- Weekend and seasonal patterns influenced sales behaviour.

## 11. Future Sales Prediction

The trained Random Forest model was used to generate future sales predictions for the test dataset.

A recursive prediction approach was applied, where previously predicted values were used to calculate subsequent predictions.

The final output contains **45,000 predicted sales records**, saved in `submission.csv`.

## 12. Project Files

- [Complete Jupyter Notebook](./Store_Item_Demand_Forecasting.ipynb) – Complete implementation and visualisations.
- [Future Sales Predictions](./submission.csv) – 45,000 predicted sales records.
- [Requirements](./requirements.txt) – Required Python libraries.
- [Dataset Information](./data/README.md) – Dataset details and source.

## 13. Conclusion

This project demonstrates how machine learning can be applied to historical retail sales data to forecast future product demand. Data preprocessing, exploratory analysis and feature engineering helped identify important sales patterns.

Among the two implemented algorithms, Random Forest achieved better results than Linear Regression, with an R² score of 0.928. The model successfully generated 45,000 future sales predictions.

Overall, the project highlights the usefulness of machine learning in demand forecasting and its potential to support better inventory planning and business decisions.

## 14. References

1. Kaggle – [Store Item Demand Forecasting Challenge](https://www.kaggle.com/competitions/demand-forecasting-kernels-only)
2. Scikit-learn Documentation – https://scikit-learn.org/
3. Pandas Documentation – https://pandas.pydata.org/docs/
4. Matplotlib Documentation – https://matplotlib.org/stable/
