# Sales Performance Analysis – Global Superstore Dataset

This project focuses on the comprehensive preparation and analysis of a global sales dataset, culminating in a planned interactive dashboard for Power BI. It demonstrates advanced data cleaning techniques, robust outlier management, and the generation of business-relevant insights.

---

## Objectives

- Clean and prepare raw transactional sales data for robust analysis.
- Identify and understand data anomalies, particularly through outlier detection.
- Explore key business metrics and their interrelationships (e.g., Sales, Profit, Discount).
- Develop a strategic plan for an interactive Power BI dashboard to visualize sales performance.

---

## Dataset Summary

The analysis is based on the **Global Superstore Dataset**, a comprehensive transactional record.

**Key Features Processed:**
* **Order Date & Ship Date**: Datetime fields, requiring proper formatting.
* **Categorical Columns**: Optimized for efficiency (e.g., `Segment`, `Region`, `Category`).
* **Sales, Profit, Shipping Cost, Discount**: Core numerical metrics for analysis.

---

## Data Cleaning & Preparation

The following key steps were performed to ensure data quality and readiness for analysis:

-   **Duplicate Removal**: Identified and removed exact duplicate records.
-   **Date Formatting**: Ensured `Order Date` and `Ship Date` were correctly parsed and formatted.
-   **Categorical Optimization**: Converted appropriate columns to `category` dtype to reduce memory usage and improve performance.
-   **Outlier Management**: Detected outliers using the Interquartile Range (IQR) method in `Sales`, `Profit`, and `Shipping Cost`. These were **retained** after careful analysis and justification, as they represent genuine business scenarios (e.g., bulk orders, high-discount transactions, logistics-driven pricing) rather than data errors.

The cleaned dataset was exported to `/data/Global_Superstore_Clean.csv` for use in Power BI.

---

## Exploratory Data Analysis

### 1. **Outlier Detection (IQR Method)**
- Identified significant numbers of outliers: `5655 in Sales`, `9755 in Profit`, `5909 in Shipping Cost`.
- The high volume (up to ≈41% of the dataset as potential outliers) suggested these were valid, while extreme, business events.

### 2. **Correlation Matrix**
- Computed Pearson correlations for `Sales`, `Profit`, `Shipping Cost`, and `Discount`.
- **Key finding**: A moderate negative correlation between `Profit` and `Discount` (-0.316) helped explain profit outliers, indicating that high discounts often lead to lower (or negative) profit margins, validating real business dynamics.

### 3. **Visual Exploration with Scatter Plots**
- Visualized `Sales vs Discount` and `Profit vs Discount`.
- Confirmed the presence of statistical outliers as visually distant points, reinforcing the decision to retain them as genuine business occurrences. For instance, high discount values consistently correlated with negative profit figures.

---

## Tools & Methods

-   **Python**: Used for data loading, cleaning, transformation, and exploratory analysis.
    -   `Pandas`: Data manipulation and preparation.
    -   `Matplotlib`, `Seaborn`: Data visualization for exploratory analysis.
-   **Power BI**: Planned for the interactive dashboard development, leveraging the cleaned dataset.

---

## Power BI Dashboard Plan

The visualization layer of this project is designed for **Power BI**, structured into two thematic pages to provide clear and actionable insights.

### Page 1 – Sales Overview

Focuses on general business performance and sales trends.

-   **KPI Cards**: Total Sales, Total Profit, Average Discount.
-   **Line Chart**: Sales and Profit by Month.
-   **Bar Charts**: Sales by Segment, Sales by Region.
-   **Column Chart**: Top 10 Sub-Categories by Sales.
-   **Filters (Slicers)**: Order Year / Month, Region, Segment, Category.

### Page 2 – Customer & Order Behavior

Provides insights into order dynamics and customer behavior.

-   **KPI Cards**: Total Orders, Total Distinct Customers, Average Shipping Delay.
-   **Column Chart**: Quantity by Sub-Category.
-   **Scatter Plot**: Profit vs. Discount (critical for outlier contextualization).
-   **Stacked Bar Chart**: Sales by Region and Category.
-   **Table (for outlier review)**: Order ID, Customer Name, Sales, Discount, Profit

---

## Repository Structure

<pre><code>

sales-performance-dashboard/
│
├── README.md
├── SalesInsight.ipynb
├── SalesInsight.pbix
│
├── data/
│   ├── Global_Superstore.csv
│   └── Global_Superstore_Clean.csv
│
├── assets/
│   ├── SalesOverview.png 
│   ├── CustomerBehavior.png
│   ├── Tooltip.png
│   └── Report_PDF.pdf

</code></pre>


---

## Key Insights

-   Statistical outliers in sales, profit, and shipping cost are predominantly genuine business events rather than data errors, reflecting high-value transactions or aggressive discount strategies.
-   A clear inverse relationship exists between `Discount` and `Profit`, highlighting the direct impact of promotional strategies on profitability.
-   The prepared dataset provides a robust foundation for granular analysis of sales performance, customer behavior, and regional trends in Power BI.

---

## Learnings & Reflection

This project significantly enhanced my skills in:

-   **Robust Data Cleaning & Transformation**: Handling diverse data types and ensuring data integrity for analytical readiness.
-   **Contextual Outlier Analysis**: Moving beyond simple statistical detection to understand and justify data anomalies from a business perspective.
-   **Exploratory Data Analysis (EDA)**: Utilizing statistical and visual methods to uncover relationships and validate hypotheses.
-   **Analytical Project Structuring**: Organizing a data analysis workflow from raw data to a clear dashboard plan.
-   **Applying Business Knowledge**: Translating data findings into actionable insights for business stakeholders, particularly in the context of sales and profitability.

This project reinforces my ability to deliver comprehensive data solutions that bridge technical analysis with practical business needs.

---

## License

This project is open for educational and demonstrative purposes. The dataset is publicly available and provided via Kaggle.