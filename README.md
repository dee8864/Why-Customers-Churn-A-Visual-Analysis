# <p align="center">Why Customers Churn: A Visual Analysis<p>

# Why Customers Churn: A Visual Analysis

## Project Overview

This project is a comprehensive data analysis of customer churn in the telecommunications industry. The primary objective was to understand the key factors that influence a customer's decision to leave a service provider. By analyzing the Telco Customer Churn Dataset, this project uncovers hidden patterns in customer behavior, tenure, monthly charges, and demographic attributes.

The analysis follows a complete data analytics workflow: importing raw data, performing extensive data cleaning, conducting exploratory data analysis (EDA), creating both static and interactive visualizations, and finally deriving actionable business insights. This project serves as a practical demonstration of how Python can be used to turn messy, real-world data into clear, decision-driving narratives.

## Dataset Used

The dataset used is the IBM Telco Customer Churn dataset, a widely used benchmark for customer analytics. It contains information on 7,043 customers, including their demographic details, account information, services they subscribed to, and whether they churned.

Key features in the dataset:
- Customer demographics (gender, senior citizen, dependents, partner status)
- Account information (tenure, contract type, payment method, paperless billing)
- Service subscriptions (phone service, internet service, online security, tech support, etc.)
- Financial data (monthly charges, total charges)
- Target variable (Churn: Yes or No)

## Tools and Libraries Used

This project was built entirely in Python using the following libraries:

- **Pandas**: For data loading, cleaning, manipulation, and aggregation.
- **NumPy**: For numerical operations and handling missing values.
- **Matplotlib (plt)**: For creating foundational static visualizations.
- **Seaborn (sb)**: For statistical visualizations and enhanced static charts. The library was imported with the alias `sb` instead of the conventional `sns`.
- **Plotly Express (px)**: For generating quick, interactive charts that allow for dynamic exploration.
- **Plotly Graph Objects (go)**: For building highly customized interactive visualizations such as donut charts.

## Project Workflow

The project was executed in a structured, step-by-step manner.

### 1. Data Loading and Initial Exploration

The CSV file was loaded using Pandas. An initial inspection of the data revealed mixed data types and the presence of missing values. The first few rows were displayed to understand the structure and the nature of each column.

### 2. Data Cleaning

Real-world data is rarely clean. The following steps were taken to prepare the dataset for analysis:

- **Standardizing Column Names**: All column names were converted to lowercase and spaces were replaced with underscores. This made the data easier to reference during coding.
- **Checking for Duplicates**: The dataset was checked for duplicate records. No duplicate rows were found, ensuring data integrity.
- **Handling Missing Values**: The `TotalCharges` column was initially read as an object (string) type. This is a common issue when numeric columns contain empty strings or spaces. The column was converted to a numeric format using `pd.to_numeric` with the `errors='coerce'` parameter. This forced any invalid entries to become `NaN` (Not a Number), making them easier to identify. After conversion, the rows with missing values were dropped. This step taught the importance of understanding data types and the role of the `coerce` parameter in safely transforming messy columns.

### 3. Exploratory Data Analysis (EDA)

EDA was performed to uncover the underlying structure of the data and generate initial hypotheses.

- **Statistical Summaries**: Descriptive statistics such as mean, median, and quartiles were calculated for numeric columns like tenure and monthly charges.
- **Churn Rate Analysis**: The overall proportion of customers who churned was calculated. This established a baseline for comparison against different customer segments.
- **Distribution Analysis**: Histograms and boxplots were created to visualize the spread and skewness of customer tenure and monthly charges.

### 4. Visualization Strategy

A key focus of this project was differentiating between static and interactive visualizations to communicate findings effectively.

- **Static Visualizations (Matplotlib & Seaborn)**:
  - **Histograms**: Showed the distribution of customer tenure.
  - **Boxplots**: Displayed the spread of monthly charges and highlighted outliers.
  - **Bar Charts**: Compared churn rates across different demographic groups and service attributes.
  - **Clustered Bar Charts**: Compared average monthly charges across different tenure groups, with annotations to highlight significant trends.
- **Interactive Visualizations (Plotly Express & Graph Objects)**:
  - **Donut Charts**: Created using Plotly Graph Objects to visually segment customers by tenure groups (0-12 months, 13-36 months, 37+ months). The interactive nature allowed for on-hover details.
  - **Line Charts**: Visualized churn rate as a function of tenure, showing how risk changes over the customer lifecycle.
  - **Interactive Bar Charts**: Made comparisons by contract type and payment method more engaging.

### 5. Advanced Analysis and Segmentation

Customers were segmented into three tenure groups. The goal was to study the relationship between customer loyalty, financial behavior, and churn.

- **Grouping**: Customers were categorized using `pd.cut`.
- **Statistical Comparisons**: Average monthly charges and churn rates were computed for each tenure segment.
- **Demographic Analysis**: Churn rates were compared across gender, senior citizen status, payment method, and contract type. This helped in identifying which customer profiles are most vulnerable to churning.

## Key Business Insights

The analysis uncovered several critical insights that can guide retention strategies.

- **Tenure and Churn**: Customers with shorter tenure (0-12 months) have a significantly higher churn rate compared to long-term customers. The first few months after onboarding are the most critical for retention.
- **Monthly Charges and Churn**: Customers with higher monthly charges, particularly those paying above the average bracket, are more likely to churn. This suggests a price sensitivity or a perceived value gap.
- **Value for Loyalty**: Long-term customers (37+ months) tend to have lower average monthly charges compared to newer customers. This points to effective loyalty pricing or the success of retention offers over time.
- **Contract Impact**: Month-to-month contracts have a much higher churn rate than one-year or two-year contracts. Longer commitment periods strongly correlate with customer retention.
- **Payment Method**: Electronic check payments are associated with higher churn, whereas automatic bank transfers and credit card payments show lower churn rates. This could indicate a correlation with financial stability or convenience.
- **Service Subscriptions**: Customers lacking premium services like online security or tech support tend to churn more, suggesting that bundling added value helps retain users.

## Challenges and Learnings

This project provided a valuable hands-on learning experience, complete with real-world hurdles.

- **The 'errors=coerce' Lesson**: The most significant technical challenge was handling the `TotalCharges` conversion. Initially, the conversion failed, causing an error. Researching and implementing `errors='coerce'` was a key learning moment, as it is an essential tool for any data analyst dealing with inconsistent datasets.
- **Understanding Visualization Libraries**: A clear distinction was learned between `matplotlib` and `seaborn` (static, low-level vs. statistical, high-level) and `plotly express` vs `plotly graph objects` (quick high-level charts vs. deep customization). This project clarified when to choose each tool based on the specific visualization need and audience.
- **Interactive vs. Static**: The project emphasized that static charts are excellent for reports and PDFs, while interactive charts are indispensable for exploratory analysis and stakeholder presentations.
- **Precision in Aggregation**: Grouping data correctly required careful attention. The `pd.cut` function and `groupby` operations were honed, reinforcing the importance of pre-aggregation before creating segmented charts.

## How to Run This Project

To replicate this analysis on your local machine, follow these steps:

1. **Clone the repository or download the files**:
   Ensure the dataset `Telco_Customer_Churn_Dataset (3).csv` is in the same directory as your Python script or Jupyter Notebook.

2. **Install the required libraries**:
   It is recommended to create a virtual environment. Install the necessary packages using pip:
