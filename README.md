# PHASE-2-PROJECT-KC-HOUSING
## Creating an automated system to estimate the sale price of houses/homes in King County

### BACKGROUND INFORMATION
The average sale price per square foot in King County is  481𝐾, up 3.2% since last year.
In August 2022, King County home prices were up 5.0% compared to last year, selling for a median price of $815K. On average, homes in King County sell after 15 days on the market compared to 6 days last year. There were 2,744 homes sold in August this year, down from 3,877 last year (https://www.redfin.com/county/118/WA/King-County/housing-market).

### PROBLEM STATEMENT
According to MaKe Realtors more houses are sitting on the market longer than previously observed, fewer people are buying homes and home prices in some areas are dropping. Clients are also backing out after viewing and inspecting units for sale. Could this be due to the condition of the units compared to the buying price quoted?
It is taking MaKe Realtors slightly longer to sell through all the homes for sale at current demand than it would have the previous months,pointing to a less frenzied market.
Sellers who correctly price their homes in today’s market get top-of-market prices. With this information, MaKe Realtors hope to optimize their pricing strategies based on the home features that potential home buyers deem crucial.
As the lead data scientist at MaKe, I have been tasked with creating an automated system to estimate the sale price of houses/homes, using information such as the house condition, square footage, number of bathrooms and bedrooms, waterfront and lot size. Estimates from the generated system will be used to predict the house sale prices by the real estate firm.

### DATA COLLECTION
Data was provided in csv format and we used the pd.read_csv function to load the data.


### DATA UNDERSTANDING
The dataset contains 21597 rows and 21 columns. Each row of the dataset contains information about one house.
Our objective is to find a way to estimate the value in the "price" column using the values in the other columns. By achieving this using this set of data, then we should able to estimate prices of other houses too, simply by asking for information like bedrooms', 'bathrooms', 'sqft_living', 'sqft_lot', 'floors', 'waterfront', 'view', 'condition', 'grade','sqft_above', 'sqft_basement' etc

### DATA PREPROCESSING
Methods such as df.info, df.describe, df.dtypes were used to get an overview of the underlying characteristics of the King County Housing Data.

### DATA CLEANING
Involved filling replacing the nan values in columns such as waterfront with no as we made the assumption that a NaN entry implied the houses were not located near a waterfront. The column sqft_basement contain a '?' at index 6 and this was replaced and the variable converted to float as it was observed it was entered as dtype 'object'.

### DATA VISUALIZATION
scatter plots were used to check for linearity, box plots to detect ouliers and distribution plots tto inspect if the variables have a normal dostribution or skewed.
A correlation matrix was also used to check for correlation between the variables and detect multicollinearity.

### DATA ANALYSIS
Multiple linear regression  and Random Forest techniques were employed to analyse the data.

### Observation and Conclusion
Results show that waterfront properties have the highest impact on price. This could be due to the lifestyle that is associated with such properties. The high significance could also be due to the fact Waterfront homes are often cited as "recession-resistant" because the property will usually grow in value and can be less prone to market downturns than nearby landlocked equivalent.

Houses in Very Good Condition had the largest positive impact on Price.Typically, homes that are newer appraise at a higher value.

A home’s usable space (above) however had much more significance than basement space.Livable space is what is most important to buyers and appraisers

### RECOMMENDATIONS
##### Consider increasing waterfront homes for sale in the portfolio.
Results show that waterfront properties have the highest impact on price. This could be due to the lifestyle that is associated with such properties. The high significance could also be due to the fact Waterfront homes are often cited as "recession-resistant" because the property will usually grow in value and can be less prone to market downturns than nearby landlocked equivalent

##### The bigger square foot the better.
The value of a home is roughly estimated in price per square foot(above and basement).A home’s usable space (above) however had much more significance than basement space.Livable space is what is most important to buyers and appraisers. In this case, incase the firm is constructing houses for sale, priority should be given to the space above over the basement space.

##### Condition of the House.
#### Model Precision
Model Precision
How precise is our model? When our linear regression model makes a prediction of the expected house prices, it is actually precise 69.1% while the Random Forest model is accurate 86.50%.


### Observation and Conclusion
Multiple Linear Regression gives us an adjusted R-squared (testing) score of 0.6903 while the Random Forest adjusted R-squared is 0.8649. A comparison of the two models shows that the Random Forest Regressor has a lower RMSE and higher adjusted R-squared, thus it outperforms the Linear Regression model.

