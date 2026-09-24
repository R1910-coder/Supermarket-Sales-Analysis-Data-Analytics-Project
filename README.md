# 🛒 Supermarket Sales Analysis

## 📊 Data Analytics Project

A complete **Exploratory Data Analysis (EDA)** and **Business Intelligence** project based on supermarket sales data. The project analyzes sales performance, products, branches, customers, payment methods, ratings, and time-based trends to generate actionable business insights.

---

## 📌 Project Workflow

```text
01. Business Problem
        ↓
02. Dataset Overview
        ↓
03. Data Quality Check
        ↓
04. Descriptive Statistics
        ↓
05. Univariate Analysis
        ↓
06. Sales & Revenue Analysis
        ↓
07. Product Analysis
        ↓
08. Branch Analysis
        ↓
09. Customer Analysis
        ↓
10. Payment Analysis
        ↓
11. Rating Analysis
        ↓
12. Time-Series Analysis
        ↓
13. Multivariate Analysis
        ↓
14. Correlation Analysis
        ↓
15. Business Questions
        ↓
16. Key Insights
        ↓
17. Business Recommendations
        ↓
18. Conclusion
```

---

# 01. 🎯 Business Problem

Supermarkets generate large amounts of transactional data containing information about:

* Products
* Product categories
* Branches
* Customer types
* Gender
* Payment methods
* Sales
* Revenue
* Ratings
* Transaction dates and times

However, raw transactional data does not directly provide meaningful business insights.

### Business Objective

The objective of this project is to analyze supermarket sales data and identify:

* Overall sales and revenue performance
* Best-performing product lines
* Branch-wise performance
* Customer purchasing patterns
* Preferred payment methods
* Customer rating behavior
* Daily and monthly sales trends
* Relationships between sales variables
* Areas where business performance can be improved

---

# 02. 📂 Dataset Overview

The project uses a supermarket sales dataset containing transaction-level records.

### Dataset Information

| Feature                 | Description                   |
| ----------------------- | ----------------------------- |
| Invoice ID              | Unique transaction identifier |
| Branch                  | Supermarket branch            |
| City                    | City/location of branch       |
| Customer Type           | Member or Normal customer     |
| Gender                  | Customer gender               |
| Product Line            | Product category              |
| Unit Price              | Price per unit                |
| Quantity                | Number of products purchased  |
| Tax 5%                  | 5% tax applied to transaction |
| Total                   | Total transaction amount      |
| Date                    | Transaction date              |
| Time                    | Transaction time              |
| Payment                 | Payment method                |
| COGS                    | Cost of goods sold            |
| Gross Margin Percentage | Gross margin percentage       |
| Gross Income            | Gross income generated        |
| Rating                  | Customer rating               |

### Target Dataset

```text
supermarket_sales.csv
```

---

# 03. 🧹 Data Quality Check

Before performing analysis, the dataset is inspected for data-quality problems.

### Checks Performed

* Dataset dimensions
* Column names
* Data types
* Missing values
* Duplicate records
* Unique values
* Invalid values
* Numerical outliers
* Date/time consistency
* Category consistency

### Example Checks

```python
df.shape
df.info()
df.isnull().sum()
df.duplicated().sum()
df.describe()
```

### Data Cleaning

The cleaning process includes:

1. Standardizing column names
2. Removing duplicate records
3. Handling missing values
4. Converting dates into datetime format
5. Converting time into appropriate time format
6. Checking numerical columns
7. Validating categorical values
8. Creating additional analytical columns

---

# 04. 📈 Descriptive Statistics

Descriptive statistics are used to understand the distribution and central tendency of numerical variables.

### Numerical Variables

* Unit Price
* Quantity
* Tax
* Total
* COGS
* Gross Income
* Rating

### Statistics Analyzed

* Mean
* Median
* Minimum
* Maximum
* Standard deviation
* Quartiles
* Range

Example:

```python
df.describe()
```

This provides an initial understanding of transaction values, product quantities, revenue and customer ratings.

---

# 05. 📊 Univariate Analysis

Univariate analysis examines individual variables independently.

### Categorical Variables

Analysis is performed for:

* Branch
* City
* Customer Type
* Gender
* Product Line
* Payment

### Numerical Variables

Distribution analysis is performed for:

* Unit Price
* Quantity
* Total
* Gross Income
* Rating

### Visualizations

* Count plots
* Histograms
* Box plots
* Pie charts
* Bar charts

Example:

```python
sns.histplot(df["Total"], kde=True)
plt.show()
```

---

# 06. 💰 Sales & Revenue Analysis

This section focuses on overall sales performance.

### Key Metrics

* Total Sales
* Total Revenue
* Total Quantity Sold
* Total COGS
* Total Gross Income
* Average Transaction Value
* Average Quantity per Transaction
* Gross Margin

### Example Calculations

```python
total_sales = df["Total"].sum()
total_quantity = df["Quantity"].sum()
total_income = df["gross_income"].sum()
```

### Analysis Questions

* What is the total revenue?
* What is the average transaction value?
* How many products were sold?
* What is the total gross income?
* What percentage of sales comes from each branch?

---

# 07. 🛍️ Product Analysis

Product-level analysis identifies high-performing and low-performing product categories.

### Analysis Areas

* Sales by product line
* Quantity by product line
* Revenue by product line
* Gross income by product line
* Average unit price
* Average rating by product line

### Key Questions

* Which product line generates the highest sales?
* Which product line sells the highest quantity?
* Which product line generates the highest gross income?
* Which categories receive the highest customer ratings?

### Visualization

```text
Product Line
     │
     ├── Sales
     ├── Quantity
     ├── Gross Income
     └── Rating
```

---

# 08. 🏢 Branch Analysis

Branch-level analysis compares supermarket performance across locations.

### Metrics

* Total revenue by branch
* Quantity sold by branch
* Gross income by branch
* Average transaction value
* Average rating
* Customer count

### Questions

* Which branch generates the highest revenue?
* Which branch sells the highest quantity?
* Which branch generates the highest gross income?
* How does customer satisfaction differ between branches?

---

# 09. 👥 Customer Analysis

Customer analysis focuses on purchasing behavior and customer segments.

### Customer Segments

* Member
* Normal

### Analysis

* Sales by customer type
* Quantity by customer type
* Average transaction value
* Gender distribution
* Product preferences
* Ratings by customer type

### Questions

* Do members generate more revenue?
* What products are preferred by each customer type?
* Which customer segment has higher transaction values?
* How does purchasing behavior differ by gender?

---

# 10. 💳 Payment Analysis

Payment analysis identifies customer payment preferences.

### Payment Methods

Depending on the dataset, payment methods may include:

* Cash
* Credit Card
* E-wallet

### Analysis

* Number of transactions by payment method
* Revenue by payment method
* Average transaction value
* Payment method by branch
* Payment method by customer type

### Business Questions

* Which payment method is most frequently used?
* Which payment method generates the highest revenue?
* Does payment preference differ between branches?

---

# 11. ⭐ Rating Analysis

Customer ratings are analyzed to understand customer satisfaction.

### Analysis Areas

* Average rating
* Rating distribution
* Rating by branch
* Rating by product line
* Rating by customer type
* Rating by gender

### Visualization

```python
sns.histplot(df["Rating"], kde=True)
plt.title("Customer Rating Distribution")
plt.show()
```

### Questions

* What is the average customer rating?
* Which product line has the highest average rating?
* Which branch receives higher ratings?
* Is there a relationship between sales and ratings?

---

# 12. 📅 Time-Series Analysis

Time-series analysis examines how sales change over time.

### Time Features

The following features are extracted:

```text
Year
Month
Day
Day of Week
Hour
```

### Analysis

* Daily sales
* Monthly sales
* Daily transaction count
* Sales by day of week
* Sales by hour
* Peak shopping hours

### Example

```python
df["Date"] = pd.to_datetime(df["Date"])

df["Month"] = df["Date"].dt.month
df["Day"] = df["Date"].dt.day
df["Day_Name"] = df["Date"].dt.day_name()
```

### Business Questions

* Which month has the highest sales?
* Which day generates the most revenue?
* What are the peak shopping hours?
* Are there specific periods with unusually high or low sales?

---

# 13. 🔍 Multivariate Analysis

Multivariate analysis examines relationships between multiple variables simultaneously.

### Variables Analyzed

Examples include:

```text
Branch × Product Line
Branch × Customer Type
Product Line × Gender
Product Line × Payment
Customer Type × Product Line
Branch × Payment
```

### Visualizations

* Heatmaps
* Grouped bar charts
* Stacked bar charts
* Pivot tables
* Box plots

Example:

```python
pd.crosstab(
    df["Branch"],
    df["Product line"],
    values=df["Total"],
    aggfunc="sum"
)
```

---

# 14. 🔗 Correlation Analysis

Correlation analysis is used to identify linear relationships between numerical variables.

### Variables

Possible variables include:

* Unit Price
* Quantity
* Tax
* Total
* COGS
* Gross Income
* Rating

Example:

```python
corr = df[numerical_columns].corr()

sns.heatmap(
    corr,
    annot=True,
    cmap="coolwarm"
)

plt.title("Correlation Matrix")
plt.show()
```

The analysis helps identify variables that move together, but correlation alone does **not** establish causation.

---

# 15. ❓ Business Questions

The analysis is designed to answer practical business questions.

### Sales

1. What is the total revenue?
2. What is the average transaction value?
3. Which branch generates the highest revenue?
4. Which product line generates the highest sales?

### Products

5. Which products have the highest sales?
6. Which product lines have the highest quantity sold?
7. Which product lines generate the most gross income?

### Customers

8. Which customer type generates more revenue?
9. What are the purchasing patterns of members vs normal customers?
10. How does customer behavior differ by gender?

### Payments

11. What is the most frequently used payment method?
12. Which payment method generates the highest revenue?

### Ratings

13. What is the average customer rating?
14. Which branch has the highest average rating?
15. Which product line receives the highest ratings?

### Time

16. Which month has the highest sales?
17. Which day has the highest revenue?
18. What are the peak transaction hours?

---

# 16. 💡 Key Insights

The final analysis should summarize the major findings from the dataset.

Example insight categories:

### Sales Performance

* Overall revenue and transaction performance
* Average transaction value
* Revenue distribution across branches

### Product Performance

* Top-performing product lines
* High-volume categories
* Categories generating higher gross income

### Customer Behavior

* Member vs normal customer purchasing behavior
* Customer gender distribution
* Product preferences

### Payment Behavior

* Most commonly used payment method
* Revenue contribution by payment method

### Customer Satisfaction

* Overall rating distribution
* Branch-level rating differences
* Product-level rating differences

### Time Trends

* High-sales periods
* Peak transaction hours
* Daily/monthly trends

> **Note:** Final numerical insights should be populated from the cleaned dataset rather than hard-coded assumptions.

---

# 17. 🚀 Business Recommendations

Based on the actual findings, the following types of recommendations can be developed:

### 1. Product Strategy

Focus inventory and promotional activities on high-performing product categories while investigating underperforming categories.

### 2. Branch Strategy

Compare branch-level sales, customer volume and profitability to identify operational differences.

### 3. Customer Strategy

Develop targeted loyalty campaigns for members and analyze opportunities to increase repeat purchases.

### 4. Payment Strategy

Maintain strong support for frequently used payment methods while encouraging convenient digital payment options where appropriate.

### 5. Inventory Strategy

Use historical sales patterns to improve stock planning and reduce the risk of overstocking or stockouts.

### 6. Promotional Strategy

Schedule promotions around periods with lower sales and leverage high-traffic periods for targeted campaigns.

### 7. Customer Experience

Investigate low-rating product categories and branches to identify potential service or product-quality improvements.

---

# 18. ✅ Conclusion

The **Supermarket Sales Analysis** project demonstrates how transactional sales data can be transformed into meaningful business insights using data analytics techniques.

The project covers the complete analytical workflow:

```text
Raw Data
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Statistical Analysis
   ↓
Business Analysis
   ↓
Visualization
   ↓
Insights
   ↓
Recommendations
```

The analysis provides a structured view of:

* Sales and revenue
* Product performance
* Branch performance
* Customer behavior
* Payment preferences
* Customer ratings
* Time-based trends
* Relationships between numerical variables

The project demonstrates practical skills in **Python, Pandas, NumPy, Matplotlib, Seaborn, Statistics, EDA and Business Analytics**.

---

# 🛠️ Technologies Used

| Technology       | Purpose                   |
| ---------------- | ------------------------- |
| Python           | Data analysis             |
| Pandas           | Data manipulation         |
| NumPy            | Numerical analysis        |
| Matplotlib       | Data visualization        |
| Seaborn          | Statistical visualization |
| Jupyter Notebook | Analysis environment      |
| Git & GitHub     | Version control           |

---

# 📁 Project Structure

```text
Supermarket-Sales-Analysis/
│
├── data/
│   ├── supermarket_sales.csv
│   └── supermarket_sales_cleaned.csv
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_sales_analysis.ipynb
│   └── 04_business_insights.ipynb
│
├── reports/
│   └── Supermarket_Sales_Analysis_Report.pdf
│
├── visualizations/
│   ├── sales_analysis.png
│   ├── product_analysis.png
│   ├── branch_analysis.png
│   ├── customer_analysis.png
│   └── correlation_heatmap.png
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

# ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/your-username/Supermarket-Sales-Analysis.git
```

### 2. Navigate to the project

```bash
cd Supermarket-Sales-Analysis
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the environment

### Windows

```bash
venv\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebooks in the `notebooks/` folder and execute the analysis sequentially.

---

# 📦 Requirements

```text
pandas
numpy
matplotlib
seaborn
jupyter
openpyxl
```

---

# 📊 Project Deliverables

The project contains:

* ✅ Raw dataset
* ✅ Cleaned dataset
* ✅ Data-quality analysis
* ✅ Exploratory Data Analysis
* ✅ Statistical analysis
* ✅ Sales analysis
* ✅ Product analysis
* ✅ Branch analysis
* ✅ Customer analysis
* ✅ Payment analysis
* ✅ Rating analysis
* ✅ Time-series analysis
* ✅ Correlation analysis
* ✅ Business questions
* ✅ Business insights
* ✅ Business recommendations
* ✅ Project report
* ✅ Visualizations

---

# 👨‍💻 Author

**Rohan Pawar**

### Skills Demonstrated

```text
Python
SQL
Pandas
NumPy
Data Cleaning
EDA
Statistics
Data Visualization
Business Analytics
Power BI
Machine Learning
```

---

## ⭐ Project Objective

> **Transform supermarket transaction data into clear, data-driven business insights that can support better decisions regarding products, customers, branches, payments, sales and business performance.**
