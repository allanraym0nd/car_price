# carPrice
####DATA CLEANING AND PREPROCESSING SECTION
### Missing Values
- The dataset was checked for missing values, and it was found that the columns `mileage`, `engine`, `max_power`, and `seats` each have a small number of missing entries (less than 3% of the data).
- No other columns contain missing values.
- Any rows where the target variable (selling price) is missing were dropped
- The missing values were filled using the mean and median.
### outliers in selling price column
- It was found that cats below 10,000 or above 5,000,000 were possible outliers so they were removed.
### price per kilometer
- A new column for “price per kilometer” was created by dividing the selling price by the mileage.

####EXPLORATORY DATA ANALYSIS
- Average selling price of cars: 501378.18
- Most common fuel type in the dataset: diesel
- Lower selling prices were found to average more sales.
- Cars that werent as old were found to have a higher selling price that older ones.
- - **Diesel** cars have the highest average selling price, while **LPG** cars have the lowest.
- The average prices are as follows:
  - **CNG**: $300,500
  - **Diesel**: $620,448
  - **LPG**: $200,421
  - **Petrol**: $363,717
- Most of the cars were found to be Manual Transmission.
- Based on the correlation heatmap, here's a brief interpretation of the relationships between the numerical variables:

   - Strong Negative Correlation: As car_age increases, the selling_price tends to decrease significantly (-0.49).
   - Moderate Positive Correlation: There's a notable positive relationship between engine size and selling_price (0.48), indicating that cars with larger engines       are generally more expensive.
  - Inverse Relationship: A strong inverse correlation exists between mileage and engine size (-0.58), suggesting that more fuel-efficient cars typically have          smaller engines.
  - Direct Relationships: selling_price is highly correlated with price_per_kilometer (0.95) and year (0.49), which is expected as newer cars tend to be more         expensive and the latter is a calculated feature.
- The average selling price for automatic cars were higher than manual cars.

####MACHINE LEARNING
### Assumptions of Linear Regression, and how can you check them using this dataset.
Here is the information on the three assumptions, each described in a single, clear sentence.

1. Linearity
This assumption states that a straight-line relationship exists between the features and the target variable, which is checked by looking for a random scatter of points around the zero line on a Residual Plot.

2. Normality of Residuals
This assumption holds that the model's errors are normally distributed, and it is checked by confirming that a histogram of these residuals resembles a bell-shaped curve.

3. No Multicollinearity
This assumption requires that the independent features are not highly correlated with each other, and it is checked by using a Correlation Heatmap to identify any strong relationships between features.

###Model Comparison
-The Polynomial Regression model's R² of 0.417 was a significant improvement over the other models (Linear, Lasso, and Ridge), which all performed similarly with an R² of around 0.35. The better performance suggests that the relationship between the selected features and the car's price is not strictly linear and has some curvature that the polynomial features were able to capture.
