# 🛍️🛒 Customer-Churn-Prediction
---
## 📖Overview
Customer retention is critical for businesses aiming to maximize revenue and build long-term relationships with their clientele. This project focuses on predicting customer churn using a machine learning approach, enabling businesses to proactively identify at-risk customers and take corrective actions.

---
## 🎯 Objective

The goal of this project is to:

*  **Predict customer churn:** Determine whether a customer will churn or stay based on historical data.
*  **Provide actionable insights:** Identify factors influencing churn to guide retention strategies.
*  **Evaluate model performance:** Use appropriate metrics to ensure the model is accurate and reliable for decision-making.
---
## 📂 Dataset Description
The dataset used in this project contains customer data and behavioral patterns. Below are the key features:

| Feature Name        | Description                                                                                      |    
|---------------------|--------------------------------------------------------------------------------------------------|
| InvoiceNo           | Unique identifier for each transaction. It represents the invoice number issued for a purchase.  | 
| StockCode           | A unique code assigned to each product in the inventory                                          | 
| Description         | Text description of the product purchased.                                                       |                                                          | Quantity            | Number of units of the product purchased in the transaction.                                     |
| InvoiceDate         | Date and time when the invoice was generated for the transaction.                                |
| UnitPrice           | Price of a single unit of the product, recorded in the local currency.                           |
| CustomerID          | Unique identifier for the customer who made the purchase. This helps track customer behavior.    |
| Country             | The country where the customer is located. This indicates the geographic location of the sale.   |                                                          

---

## 🧹 Data Cleaning
In this project, a robust data cleaning process was implemented to ensure the dataset was ready for analysis and modeling. Key transformations and feature engineering steps were carried out to create meaningful features that enhance the prediction of customer churn.

---

### Data Cleaning Steps

**1.  Handling Missing Values:**
*  Checked for missing values across all columns.
*  Imputed missing values appropriately based on the nature of the feature (e.g., mean or median for numerical features).

**2.  Date Conversion:**
*  converted the ```InvoiceDate``` column from a string format to a **datetime** object for accurate time-based analysis.

**3.  Duplicate Removal:**
*  Identified and removed duplicate rows to maintain data integrity.

---

### Feature Engineering

To enhance the dataset and create meaningful predictors for churn, several new features were engineered:

**1.  Recency:**
*  Calculated as the difference between the maximum date of purchase and each customer's most recent purchase date.
*  Provides insights into how recently a customer made a purchase.

**2.  Frequency:**
*  Counted the total number of purchases made by each customer using the CustomerID and InvoiceDate columns.
*  Indicates customer engagement over time.

**3.  Amount:**
*  Computed as the product of Quantity and UnitPrice for each transaction, representing the monetary value of each purchase.
*  Helps understand customer spending behavior.

**4.  Label (Churn):**
*  Created the target variable Churn using the Recency feature. Customers whose recency was greater than the 75th percentile were labeled as churned (1), while others were labeled as not churned (0).
*  This threshold was selected to focus on customers with a long gap since their last purchase.

---

## 🔍 Exploratory Data Analysis (EDA)
In this project, Exploratory Data Analysis (EDA) was conducted to uncover insights from the dataset and identify key factors influencing customer churn. Below are the steps and findings from the EDA:

**1.  Missing Values Analysis:**
Checked for missing or null values in the dataset.
 ![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/missing%20values.png)

**2. Average Customers Per Country:**
A bar chart was created to display the average number of customers across different countries.
 ![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/avarage%20purchage%20per%20country.png)

**3. Box Plot:**
Visualized key metrics (e.g., ```Frequency```, ```Recency```, ```Amount```) using box plots to detect outliers and understand the distribution of values.
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/box%20plot.png)

**4. Distribution of Total Price:**
A histogram was plotted to examine the distribution of total monetary value.
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/distribution%20of%20total%20price.png)

**5. Heatmap:**
Generated a correlation heatmap to visualize the relationships between features such as ```TotalPrice```, ```UnitPrice```, and ```Quantity```.

![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/heat%20map.png)

**6. Monthly Sales:**
A line chart was created to track monthly sales trends over the observed period.
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/monthly%20sales.png)

**7. Time Series Plot of Unit Price:**
A time series visualization of UnitPrice was generated to observe price changes over time.
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/time%20series%20plot%20of%20unit%20price.png)


---

## ⚙️ Model Building
* Train and evaluate multiple machine learning models, including:
  * Logistic Regression
  * Support Vector Machines
  * Random Forest
  * Neural Network
* Perform hyperparameter tuning using Grid Search/Random Search.
* Split data into training and testing sets to evaluate model performance.

---

### 🔬 Logistic Regression Model Performance : 

Accuracy: 0.9970896391152503

Precision: 0.9889380530973452

Recall: 1.0

F1 Score: 0.9944382647385984

#### Confusion Matrix For Logistic Regression Performance
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/logistic%20regression%20confusion%20matrix.png)


### 🔬 Support Vector Machine Model Performance : 

Accuracy: 0.9728260869565217

Precision: 0.9234972677595629

Recall: 0.9797101449275363

F1 Score: 0.950773558368495

#### Confusion Matrix For Support Vector Machine Model Performance
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/svm%20confusion%20matrix.png)

### 🔬 Random Forest Model Performance : 

Accuracy: 1.0

Precision: 1.0

Recall: 1.0

F1 Score: 1.0

#### Random Forest Tree Plot
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/random%20forest.png)

### 🔬 Neural Network Performance : 
Test Accuracy: 0.9736024737358093

#### Neural Network Accuracy Plot
![alt text](https://github.com/Evykings/Customer-Churn-Prediction/blob/main/neural%20network%20plot.png)

---

## 📈 Results

Best-performing model: **Random Forest** with an Accuracy of 100% and a precision-recall balance that allow business focus on the right customers.




