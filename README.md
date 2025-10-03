# **Enhancing House Price Prediction using ZIP Code Sociodemographic Data: A Case Study in King County, WA**
<img width="800" height="450" alt="06032025_1_205220" src="https://github.com/user-attachments/assets/a49bd494-b686-4cb9-a2a2-97d51e90bbb3" />


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

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/cdb2a118-f537-4477-9251-584ca8e7f592" />

<p align="left" style="margin-left:400;">
  <img src="https://github.com/user-attachments/assets/ae9e170d-0edb-4dce-90b6-d08f6ab80b53" width="600" />
</p>

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
**## **Dataset Description**

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

---
---

# **RECOMMENDATIONS FOR FUTURE WORK**

As stated earlier, in addition to house-specific features, this project incorporated the following ZIP code-level characteristics when developing the machine learning models:

- **Median household income**  
- **Percentage of families below the poverty line**  
- **Percentage of the population with a bachelor’s degree or higher**  

However, other potentially valuable ZIP code- or area-specific features (**such as access to public transit, availability of amenities, and school quality**) were not available. Although this limitation was partially accounted for through target-encoded 'zipcode', adding such additional features could further enhance predictive accuracy. **Future work is therefore recommended to integrate richer geographic and socioeconomic data sources.**

Another promising direction is to apply **prediction models with spatial effects**, such as **conditional autoregressive (CAR)** or **multi-level hierarchical** models. These models assume that properties located within the same geographical unit (e.g., ZIP code, municipality, area) often share similar spatial and sociodemographic characteristics. I have previously applied and published such spatial prediction models in the context of road crash prediction (see Hosseinpour et al. (2018), Hosseinpour et al. (2021) for more details). **Incorporating spatial dependencies into machine learning models could further enhance their predictive performance.**

Finally, the dataset used in this project covered house sales from 2014–2015. To validate and strengthen the findings, **future projects should apply the ML prediction models applied in this work to more recent data.**

---

# **REFERENCES**

Campesato, O. (2023). Python 3 and Feature Engineering.

Galli, S. (2020). Python feature engineering cookbook. Packt Publishing.

Hosseinpour, M., Sahebi, S., Zamzuri, Z. H., Yahaya, A. S., & Ismail, N. (2018). Predicting crash frequency for multi-vehicle collision types using multivariate Poisson-lognormal spatial model: A comparative analysis. *Accident Analysis & Prevention, 118*, 277–288. [Link](https://www.sciencedirect.com/science/article/abs/pii/S0001457518301878)


Hosseinpour, M., Madsen, T. K. O., Olesen, A. V., & Lahrmann, H. (2021). An in-depth analysis of self-reported cycling injuries in single and multiparty bicycle crashes in Denmark. *Journal of Safety Research, 77*, 114–124. [Link](https://www.sciencedirect.com/science/article/abs/pii/S0022437521000244)


Müller, A. C., & Guido, S. (2016). Introduction to machine learning with Python: A guide for data scientists. O’Reilly Media.
