# **Enhancing House Price Prediction using ZIP Code Sociodemographic Data: A Case Study in King County, WA**

## **PROJECT SUMMARY**

The objective of this project was to develop and compare different machine learning algorithms for predicting residential house prices in **King County, Washington**. The primary dataset, which covered housing sales between **May 2014 and May 2015**, included house-specific attributes, such as the number of bedrooms and bathrooms, living area square footage, and lot size.  

Several prediction models were fitted and compared, including:  

- Decision Tree Regression (**Tree**)
- Random Forest (**RF**)
- Extreme Gradient Boosting (**XGBoost**)  
- Artificial Neural Networks (**ANN**)  
- K-Nearest Neighbors (**KNN**)
- Gamma Regression (**Gamma**)
- Linear Regression (**Ridge**)
- Stochastic Gradient Boosting (**SGB**)  

The dataset was split into **training** and **test** subsets, with the former used for model training and hyperparamter tuning, and the latter reserved for performance evaluation. Predictive accuracy was assessed using three widely adopted metrics:  

- **Root Mean Squared Error (RMSE)**  
- **Mean Absolute Error (MAE)**  
- **Coefficient of Determination (R²)**  

The comparative analysis demonstrated that **XGBoost achieved the highest predictive performance**, closely followed by **ANN** and **Random Forest** models, highlighting the effectiveness of ensemble and deep learning approaches for this regression task.  

<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/cdb2a118-f537-4477-9251-584ca8e7f592" />

<img src="https://github.com/user-attachments/assets/ae9e170d-0edb-4dce-90b6-d08f6ab80b53" width="800" />

---

## **Project Merit**
A key contribution of this work lies in the **integration of sociodemographic features at the ZIP code level**, which distinguishes it from many prior studies that relied primarily on house-specific attributes. In addition to traditional housing characteristics, this project incorporated:  

- **Median household income**  
- **Percentage of families below the poverty line**  
- **Percentage of the population with a bachelor’s degree or higher**  

These ZIP code-level features were sourced from the **[U.S. Census Bureau (2014)](https://data.census.gov/)**.  

The inclusion of these sociodemographic indicators enhanced the richness of the dataset and, on average, improved model predictive performance by **approximately 16%**. This demonstrates the substantial value of combining **geospatial and demographic information** with property-level features in housing market prediction models.  

<img width="768" height="448" alt="image" src="https://github.com/user-attachments/assets/fab44b51-dcfd-47d0-b556-303ae8de16f9" />


---

### **Feature Importance Analysis**

An analysis of feature importance revealed that both house-specific and ZIP code-level sociodemographic variables significantly contributed to housing prices. Among the predictors, **grade**, which was based on King County grading system reflecting construction quality and design standards, found as the most contributing factor. This was followed by **target-encoded ZIP code** (where ZIP codes were replaced with their average house prices), **living area square footage (sqft_living)**, **waterfront indicator**, and **percentage of the population with a bachelor’s degree or higher (zipc_bsc_rate)**. Other variables, such as **median household income**, **house age**, and **percentage of families below the poverty line (poverty rate)** had relatively smaller effects.  

<img width="690" height="390" alt="image" src="https://github.com/user-attachments/assets/1bf62090-b701-45a7-9e8c-e3a71e5e5714" />


---
---
## **## **Dataset Description**

| Variable          | Description                                                                                  | Variable Type   |
|:------------------|:---------------------------------------------------------------------------------------------|:----------------|
| id                | Unique identifier for each house sale                                                         | Identifier      |
| date              | Date the house was sold (YYYYMMDD format)                                                     | Date/Time       |
| price             | Sale price of the house (target variable)                                                     | Continuous      |
| bedrooms          | Number of bedrooms                                                                            | Discrete        |
| bathrooms         | Number of bathrooms (0.5 = half-bathroom)                                                     | Continuous      |
| sqft_living       | Living area of the house (square feet, above ground + basement)                               | Continuous      |
| sqft_lot          | Lot size (square feet)                                                                        | Continuous      |
| floors            | Number of floors (levels) in the house                                                        | Discrete        |
| waterfront        | Indicator variable: 1 = house with waterfront view, 0 = no                                    | Indicator (0/1) |
| view              | Index from 0–4 indicating quality of the view                                                 | Ordinal         |
| condition         | Condition of the house (scale 1–5, from poor to excellent)                                    | Ordinal         |
| grade             | Construction and design quality (scale 1–13, higher = better quality)                         | Ordinal         |
| sqft_above        | Square footage of the house above ground level (excluding basement)                           | Continuous      |
| sqft_basement     | Square footage of the basement area                                                           | Continuous      |
| yr_built          | Year the house was built                                                                      | Discrete/Year   |
| yr_renovated      | Year the house was last renovated (0 if never renovated)                                      | Discrete/Year   |
| lat               | Latitude coordinate                                                                          | Continuous      |
| long              | Longitude coordinate                                                                         | Continuous      |
| sqft_living15     | Living area (sqft) of the 15 nearest neighbors                                                | Continuous      |
| sqft_lot15        | Lot size (sqft) of the 15 nearest neighbors                                                   | Continuous      |
| zipcode           | Postal ZIP code where the house is located                                                    | Categorical     |
| zipc_income       | ZIP code-level household median income                                                        | Continuous      |
| zipc_bsc_rate     | ZIP code-level percentage of the population with a bachelor’s degree or higher                | Continuous (%)  |
| zipc_poverty_rate | ZIP code-level percentage of families below the poverty line                                  | Continuous (%)  |
