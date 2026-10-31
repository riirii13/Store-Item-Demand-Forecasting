# Store Item Demand Forecasting Using Machine Learning

## Project Overview
This project uses machine learning techniques to analyse historical retail sales data and predict future product demand across multiple stores.

## Dataset
The project uses the Store Item Demand Forecasting dataset from Kaggle.

- 913,000 historical training records
- 10 stores
- 50 products
- Historical sales data from 2013 to 2017
- 45,000 records for future demand prediction

**Dataset Source:** [Kaggle Store Item Demand Forecasting Challenge](https://www.kaggle.com/competitions/demand-forecasting-kernels-only/data)

## Technologies Used
- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Kaggle Notebooks

## Methodology
1. Data loading and preprocessing
2. Exploratory Data Analysis
3. Feature engineering using lag features and rolling averages
4. Chronological train-test splitting
5. Linear Regression model implementation
6. Random Forest Regressor implementation
7. Model evaluation and comparison
8. Future sales prediction

## Model Performance

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 6.981 | 9.131 | 0.916 |
| Random Forest | 6.480 | 8.445 | 0.928 |

Random Forest performed better across all three evaluation metrics.

## Results
The final Random Forest model generated 45,000 future sales predictions. Feature importance analysis identified the seven-day rolling average as the most influential feature.

## Project Files

- [Complete Jupyter Notebook](./Store_Item_Demand_Forecasting.ipynb) – Complete Python implementation, data preprocessing, visualisations, feature engineering, model training and evaluation.
- [Future Sales Predictions](./submission.csv) – CSV file containing 45,000 predicted sales records.
- [Requirements](./requirements.txt) – Python libraries required to run the project.
- [Dataset Information](./data/README.md) – Dataset details and original Kaggle source.

## Conclusion
This project demonstrates how machine learning can support retail demand forecasting and help businesses improve inventory planning and reduce stock shortages.
