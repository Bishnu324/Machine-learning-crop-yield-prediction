
Overview:

The notebook is focused on crop yield prediction using various datasets including yield, rainfall, temperature, and pesticide data from free source that is kaggle data source  The analysis involves data loading, preprocessing, exploration, and merging of multiple datasets to create a comprehensive dataset for potential modeling.

Key Steps Performed
1. Data Loading and Initial Exploration
Loaded four datasets:

yield.csv: Crop yield data by country, year, and crop type

rainfall.csv: Average rainfall data by country and year

temp.csv: Average temperature data by country and year

pesticides.csv: Pesticide usage data by country and year

2. Data Cleaning and Preprocessing
For each dataset:

Selected relevant columns.
Renamed columns for consistency.
Removed duplicate rows.
Converted data types to numeric where needed.

For temperature data;
#Sort by country and year,Since it's one temperature value per country per year,so sort 1st and then group by country
#Group by country (to ensure you fill within each country)

#Use .transform() (to ensure it applies to each column correctly)

#Apply .ffill() and .bfill() to multiple columns at once
#cross check the missing value

Then Handled missing values (filling with mean/zero where appropriate).


3. Data Merging
Created a merged dataset combining all four sources on 'Area' and 'Year' keys:

a.Yield data (primary dataset)
b.Rainfall data
c.Temperature data
d.Pesticide usage data
4. Data Quality Checks
Verified no null values remain in final merged dataset and check data types change into numeric.
Again Checked for duplicates and 
examined descriptive statistics.

Data Characteristics for merged data set;
Final merged dataset contains 102,228 rows and 7 columns.
Key variables:
a.Yield_output (target variable)
b.average_rain_fall_mm_per_year
c.avg_temp
d.Pesticide_use
e.Item (crop type)
f.Area (country)
g.Year

5.Missing Data Handling:

a.Rainfall data had many missing values (filled with mean)
b.Temperature data had missing values (filled with mean)
c.Pesticide data had many missing values (filled with 0)

6.Detect non numeic string:Returns the value of rows where the value is a string and not convertible to float — i.e., invalid data for numerical analysis.Note:If x is a string:It tries to convert it into a float.If the float value is an integer (i.e., it has no fractional part), it returns the value as an integer.If the float value has a fractional part, it returns it as a float.If the conversion fails (e.g., the string cannot be converted to a float), it returns np.nan.If x is not a string (e.g., it’s already a number), it returns x unchanged.

7.EDA
a.graph for count of country or area (frequency vs area)
b.countplot for  Items counts
#Arrange Columns  in order('Area','Year','Item','average_rain_fall_mm_per_year','avg_temp','Pesticide_use','Yield_output)

8.Encoding and scalling at a same time(encoding and feature scalling)
Then final dataset was well-prepared for modeling crop yields based on environmental factors to predict crop yield.

9.Train test split

10.Fit and transform data into x_train dummy and x_test_dummy

11.Model training
I have used ,linearRegression, Ridge, Lasso,KNeighborsRegressor,DecisionTreeRegressor.

#Result
a.LinearRegression MSE: 1407140867.3618488 Score0.7071448260289731
b.Ridge MSE: 1407203899.7394783 Score0.7071317076850001
c.Lasso MSE: 1406919421.657399 Score0.7071909134689772
d.Knr MSE: 154385259.4155923 Score0.9678692282674717
e.DecisionTree MSE: 138583870.68658906 Score0.9711578247062148

#Chose the model that has high score ansd less mse,so here we chose decission tree which is best choice for this data #Decision tree do not need to apply encoding and feature scalling as it has capability to encode categorical data by itself

#Recommendations
Could incorporate soil quality data, farming practices, or economic indicators.Satellite/remote sensing data could enhance predictions
