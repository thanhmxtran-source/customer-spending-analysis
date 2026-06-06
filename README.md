# Customer Spending Analysis and Sales Regression
 
## Overview
This project analyzes the relationship between customer demographics and monthly spending patterns to help a retail store optimize its sales strategies. Using a dataset of 100 customers, the analysis explores how age, income, gender, and region influence spending behavior, culminating in a multiple linear regression model that identifies the key drivers of monthly spend.
 
## Objectives
- Extract and preprocess customer transaction data from a JSON file
- Engineer new features and encode categorical variables for analysis
- Conduct exploratory data analysis through descriptive statistics and visualizations
- Build and interpret a multiple linear regression model to predict monthly spending
- Translate findings into actionable business recommendations
## Dataset
- **Source:** JSON file containing customer transaction records
- **Size:** 100 customers (with some missing values handled during cleaning)
- **Key Features:**
  - `customer_id`: unique customer identifier
  - `age`: customer age (range: 19–69, average: 43.35)
  - `gender`: male or female
  - `region`: North, South, East, or West
  - `income`: annual income (range: $4,800–$87,900)
  - `monthly_spend`: monthly spending amount (range: $51–$308)
  - `monthly_spend_per_monthly_income`: engineered feature representing spend as a share of monthly income
## Tools & Technologies
- **Language:** Python
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Statsmodels
- **Environment:** Google Colab
## Methodology
1. **Data Extraction**: Loaded customer data from JSON format into a Pandas DataFrame
2. **Data Cleaning**: Handled missing values in income and monthly spend; dropped incomplete rows
3. **Feature Engineering**: Created `monthly_spend_per_monthly_income` to measure spending relative to earnings
4. **Encoding**: Converted `gender` and `region` into dummy variables using `pd.get_dummies` with `drop_first=True` to avoid multicollinearity
5. **Exploratory Data Analysis**: Generated summary statistics and visualizations, including histograms, boxplots, scatter plots, a correlation heatmap, and a pairplot
6. **Regression Modeling**: Built a multiple linear regression model using all variables, then refined it to only statistically significant predictors (age, income, gender)
## Key Findings
- The final regression model explains **66.1% of the variability** in monthly spending (R² = 0.661)
- **Age** is a strong positive predictor, which means each additional year of age is associated with approximately $1.42 more in monthly spend
- **Income** is also positively associated with spending indicates a $50,000 increase in annual income corresponds to roughly $50 more per month
- **Gender** is significant as female customers spend on average **$35.42 more per month** than male customers
- Region was not a statistically significant predictor and was excluded from the final model
## Business Recommendations
- **Target older adults** with higher-end products, as age is a strong driver of spending
- **Segment by income** to tailor offerings such as premium products for higher-income customers, value promotions for lower-income ones
- **Investigate the gender spending gap** to understand what product categories drive the $35 difference and tailor marketing accordingly
