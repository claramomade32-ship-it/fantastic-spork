# fantastic-spork
Machine learning project predicting Rossmann store sales with Random Forest &amp; XGBoost. End-to-end workflow: EDA → modeling → business insights.


# Rossmann Sales Forecasting

## Project Overview
Rossmann operates over 3,000 drug stores across Europe. Store managers must forecast **daily sales up to six weeks in advance** to make informed decisions on **inventory, staffing, and promotions**.  

This project applies **machine learning** to predict daily sales using historical sales and store-level data.

---

## Data Description
The dataset (from Kaggle’s Rossmann challenge) includes:  

- **Store**: Unique ID for each store  
- **Date**: Daily record  
- **Sales**: Target variable – daily sales (💡 prediction goal)  
- **Customers**: Number of customers visiting  
- **Promo**: Promotion flag (1 = running promo)  
- **StateHoliday / SchoolHoliday**: Holiday indicators  
- **StoreType / Assortment**: Store characteristics  
- **CompetitionDistance / Promo2**: Competition and ongoing promos  
- **Engineered features**: Month, DayOfWeek, etc.  

---

## Exploratory Data Analysis (EDA)
**Key insights:**

 **Seasonality** – Sales show weekly/monthly cycles, with end-of-month and holiday spikes.  
 **Promotions** – Stores in promotion weeks have noticeably higher sales.  
 **Competition**– Closer competition generally increases sales. This suggests that proximity to competitors may actually boost sales, likely because; 1.Customers prefer areas with multiple shopping options ("shopping clusters").
         2. More foot traffic in competitive zones.
         3.Stores closer to competition may invest more in promotions to attract/retain customers.

 **Customers** – Strong positive correlation with sales.  

<img width="1165" height="573" alt="output_5_2" src="https://github.com/user-attachments/assets/cac326a4-d91c-4a43-9d36-d96442468f36" />

<img width="1024" height="556" alt="output_8_0" src="https://github.com/user-attachments/assets/90698f47-928b-4851-9a0b-de5589b44273" />

<img width="1024" height="556" alt="output_8_1" src="https://github.com/user-attachments/assets/980ba70e-181a-49ae-a984-76ddad309423" />

<img width="1024" height="556" alt="output_10_0" src="https://github.com/user-attachments/assets/16122406-fd1e-4681-97e1-f2e2ee3e3c6b" />

<img width="1024" height="556" alt="output_10_1" src="https://github.com/user-attachments/assets/b230fc80-2de3-4856-8af9-c0de034ebf47" />

<img width="1033" height="556" alt="output_9_1" src="https://github.com/user-attachments/assets/d5986fae-536d-47e3-87cb-5c20643769ff" />


---

##  Modeling Approach
Three regression models were trained:  

1. **Linear Regression (baseline)**  
2. **Random Forest Regressor**  
3. **XGBoost Regressor**  

### Metrics
- **RMSE (Root Mean Squared Error)** – penalizes large errors.  
- **MAE (Mean Absolute Error)** – average absolute error.  
- **MAPE (Mean Absolute Percentage Error)** – interpretable % error.  

---

## Model Performance

| Model              | RMSE   | MAE   | MAPE   |
|--------------------|--------|-------|--------|
| Linear Regression  | 2716   | 1984  | –      |
| Random Forest      | 1091   | 731   | 10.80% |
| XGBoost            | 1089   | 758   | 11.89% |

---

## ✅ Best Model
- **Random Forest** performed best, with the lowest error rates.  
- **MAPE = 10.8%**, meaning predictions are within **±10.8% of actual sales**.  
 Example: If a store expects **6,000 units in sales**, the forecast is typically within **±650 units**.  

---

## 📈 Business Impact
- Reliable sales forecasts help Rossmann:  
  - Optimize **inventory** (avoid over/under-stocking).  
  - Improve **staff planning** for peak sales days.  
  - Maximize **promotion effectiveness**.  
- With ~90% accuracy, this model provides strong support for **data-driven decision-making**.  

---

## Tech Stack
- Python: Pandas, NumPy, Matplotlib, Seaborn  
- Scikit-learn, XGBoost  
- Jupyter Notebook  

---

## Next Steps
- Hyperparameter tuning for further accuracy gains.  
- Deploy the model in a **dashboard** for store managers.  
- Add external factors (e.g., weather, events, economy).  

---

 **Result**: Random Forest is the most reliable model, enabling Rossmann to forecast sales with **business-ready accuracy**.  

---
