# Customer-Analytics
This project focuses on analyzing customer and sales data to provide valuable insights that support business decision-making.

## Project Information

This project includes the following key steps:
1.  **Data Preprocessing:** Cleaning and preparing data from various sources.
2.  **Customer Demographics Analysis:** Exploring customer characteristics related to age, gender, marital status, and geographical region.
3.  **Customer Segmentation (RFM Analysis):** Dividing customers into groups based on RFM: recent purchase (Recency), purchase frequency (Frequency), and monetary value (Monetary Value).
4.  **Data Visualization:** Using dashboards to present insights and understandably.

---

## Data Preprocessing

The data preprocessing script Customer_cleaning.ipynb performs the necessary steps to clean and prepare the dataset before analysis. The main steps include:

1.  **Import Libraries:** Loading essential Python libraries (`numpy` and `pandas`) for data manipulation.
2.  **Load Data:** Reading various CSV data files (`dbo.customer.csv`, `dim.date.csv`, `dim.geography.csv`, `dim.sales_territory.csv`, `fact_internet_sales.csv`, `dim.product.csv`) into pandas DataFrames.
3.  **Preview Data:** Displaying the first 5 rows of each DataFrame to inspect their initial structure.
4.  **Eliminate Unnecessary Columns:** Retaining essential columns and removing irrelevant ones from specific DataFrames (`dbo.customer`, `dim.geography`, `dim.product`) to simplify data and reduce noise.
5.  **Check and Handle Missing Values:** Checking the number of missing values in each DataFrame. Note that some missing values in columns like `Phone` (in customer data) or `CarrierTrackingNumber` (in sales data) do not affect the main analysis objectives and are therefore not addressed.
6.  **Check and Convert Data Types:** Ensuring that columns have appropriate data types for analysis. Specifically, the `FullDateAlternateKey` column in the `dim.date` data is converted to a datetime format for time-related calculations.
7.  **Check for Duplicates:** Identifying and reporting the number of duplicate rows in each DataFrame (if any).
8.  **Remove Extra Spaces:** Stripping leading and trailing whitespace from string-type columns to ensure data consistency.
9.  **Export Cleaned DataFrames:** Saving the preprocessed DataFrames as new CSV files (`cleaned_customer.csv`, `cleaned_date.csv`, etc.) into the specified directory, ready for subsequent analysis steps.

The goal of this code is to effectively prepare the data, ensuring it is clean and ready for later analysis.

---

## Key Insights from Data

Here are the significant insights derived from the analysis of customer and sales data:

### 1. Customer Demographics

* **Overview:**
    * Total Sales reached **29.36 Million**.
    * The total number of customers is **18.48 Thousand**.
* **Gender and Marital Status Distribution:** Sales are fairly balanced between male (50.46%) and female (49.54%) customers, as well as between married (51.73%) and single (48.27%) customers. This suggests that both groups make significant contributions to revenue.
* **Sales by Age Band:**
    * The **50-59 age group** contributes the highest sales (approximately 9 million), indicating this is a core customer segment.
    * The **Above 60 and 40-49 age groups** also show substantial contributions.
    * The "30-39" age group has the lowest sales.
    * **Insight:** Middle-aged customers (40-59 years old) represent the most valuable customer segment in terms of revenue and should be a focus for marketing strategies.
* **Sales by Country:**
    * The **United States** is the top country contributor to sales (21.34K), significantly outperforming other nations.
    * **Australia** ranks second with 13.35K.
    * **Insight:** The US and Australia are two key markets generating large revenues and should be prioritized in business development strategies.

### 2. Customer Segmentation (RFM Analysis)

RFM (Recency, Frequency, Monetary Value) analysis has segmented customers into 12 distinct groups based on their purchasing behavior.

* **Number of Customers by Segment:**
    * The **"At Risk" (2.8K)** and **"Hibernating" (2.1K)** segments have the largest number of customers, indicating a significant number of customers at risk of churn or who have been less interactive.
    * **"Champions" (1.9K)** and **"Loyal Customers" (1.6K)** segments show a healthy number of loyal customers.
* **Total Sales Amount by Segment:**
    * **"Champions"** contribute the highest sales (8.8M), followed by **"Loyal Customers" (5.8M)**. These are the most valuable customer groups.
    * The **"Can't Lose Them"** segment also contributes significantly (2.6M), despite its name suggesting a risk of loss.
    * **Insight:** Focus should be placed on retaining and nurturing "Champions" and "Loyal Customers" as they are the primary revenue drivers. Simultaneously, strategies are needed to re-engage "Can't Lose Them" customers to prevent potential revenue loss.
* **Recency by Segment:**
    * Segments like **"At Risk", "Hibernating", "Lost", "Can't Lose Them", "About To Sleep"** have high Recency values (meaning they haven't interacted recently).
    * **"Champions"** and **"Recent Customers"** have the lowest Recency (most recent interactions).
    * **Insight:** Re-engagement campaigns are crucial for segments with high Recency to encourage them to interact again.
* **Frequency by Segment:**
    * **"Potential Loyalist", "Champions", "At Risk", "Loyal Customers", "Hibernating"** show high purchase/interaction frequency.
    * **Insight:** High-frequency groups like "Champions" and "Loyal Customers" should be encouraged to maintain and increase their purchase frequency.
* **Monetary Value by Segment:**
    * **"Champions"** contribute the highest monetary value (nearly 9M).
    * **"At Risk"** and **"Loyal Customers"** also contribute substantial value.
    * **"Can't Lose Them"** also demonstrates high monetary value.
    * **Insight:** Despite being at risk, "At Risk" and "Can't Lose Them" customers still hold significant monetary value. This emphasizes the importance of retention efforts through special programs.

---

## Actionable Recommendations

Based on the insights gathered, here are some actionable recommendations:

1.  **Target Middle-Aged Customers:** Develop products, services, and marketing campaigns specifically tailored to the 50-59 age group, as this segment generates the highest revenue.
2.  **Strengthen Presence in Core Markets:** Continue investing in and expanding business operations in the United States and Australia.
3.  **Customer Retention Strategies:**
    * **For "Champions" and "Loyal Customers":** Implement loyalty programs, exclusive offers, and premium services to maintain their loyalty and encourage repeat purchases.
    * **For "At Risk", "Hibernating", and "Can't Lose Them":** Launch re-engagement campaigns such as personalized offers, feedback surveys, or special support services to encourage their return and prevent churn. Pay particular attention to "Can't Lose Them" as they still hold high monetary value.
4.  **Deeper Analysis of Other Groups:** Conduct further investigation into segments with large numbers but lower value (e.g., "About To Sleep", "Lost") to understand the underlying reasons better and identify potential opportunities for recovery or strategy optimization.
5.  **Optimize Frequency-Based Campaigns:** Encourage high-frequency groups to maintain their purchasing habits, while designing programs to increase the purchase frequency for lower-frequency segments.

---
