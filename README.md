# Customer Shopping Behavior Analysis

## Overview
This end-to-end data analytics project explores transactional shopping data from **3,900 customer purchases** across multiple retail categories[cite: 1]. The objective is to identify key revenue drivers, customer demographics, discount dependencies, and subscription trends to support data-driven business decisions[cite: 1]. The workflow spans data cleaning and exploratory data analysis (EDA) in Python, business querying in SQL, interactive dashboarding in Power BI, and executive storytelling via a written report and Gamma presentation[cite: 1, 2, 7].

---

## Dataset
* **Volume:** 3,900 rows and 18 columns[cite: 1]
* **Demographics:** Customer ID, Age, Gender, Location, Subscription Status[cite: 1]
* **Purchase Details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color[cite: 1]
* **Shopping Behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method[cite: 1, 2]
* **Data Quality Note:** 37 missing values identified in the `Review Rating` column prior to cleaning[cite: 1]

---

## Tools & Technologies
* **Python:** `pandas`, `numpy`, `sqlalchemy` / `psycopg2` (Data cleaning, feature engineering, EDA, and database loading)[cite: 1, 2]
* **SQL (PostgreSQL / MySQL / SQL Server):** Business metric aggregation, customer segmentation, and window functions[cite: 2, 6]
* **Power BI:** Interactive KPI tracking, slicers, and visual reporting[cite: 7]
* **Gamma & Documentation:** Executive presentation deck and structured analytical report

---

## Project Steps

### 1. Data Cleaning & EDA (Python)
* **Initial Inspection:** Assessed data types, summary statistics, and null counts using `.info()` and `.describe()`[cite: 1].
* **Imputation:** Filled 37 missing values in `review_rating` using the median rating grouped by product category[cite: 1, 2].
* **Standardization:** Converted all column names to `snake_case` for clean SQL compatibility.
* **Feature Engineering:** Created `age_group` (Young Adult, Middle-aged, Adult, Senior) and standardized `purchase_frequency_days`[cite: 2, 7].
* **Redundancy Removal:** Confirmed identical values between `discount_applied` and `promo_code_used`, dropping `promo_code_used`.
* **Database Load:** Exported the cleaned dataset directly into a relational SQL database[cite: 2].

### 2. Business Analysis (SQL)
Executed 10 targeted SQL queries to answer core business questions[cite: 2]:
* Revenue breakdown by gender and age group[cite: 2, 6]
* Identification of high-spending discount users (839 customers spending above the $59.76 average despite using discounts)[cite: 3, 7]
* Top 5 highest-rated products and top 3 best-selling items per category[cite: 3, 6]
* Average spend comparison across shipping types (Express vs. Standard)[cite: 4]
* Subscription adoption rates among repeat buyers (>5 purchases)[cite: 6]
* Customer segmentation into **New**, **Returning**, and **Loyal** tiers[cite: 5]

### 3. Visualization & Reporting (Power BI & Gamma)
* Built an interactive Power BI dashboard featuring dynamic slicers (Subscription Status, Gender, Category, Shipping Type)[cite: 7].
* Compiled findings into a comprehensive PDF report and a visual presentation deck using Gamma.

---

## Dashboard
The **Customer Behavior Dashboard** provides an executive view of core metrics and customer segments[cite: 7]:
* **Top-Level KPIs:** 3.9K Total Customers, $59.76 Average Purchase Amount, and 3.75 Average Review Rating[cite: 7].
* **Visual Breakdowns:**
  * Customer distribution by Subscription Status (27% Subscribed vs. 73% Non-Subscribed)[cite: 7].
  * Revenue and Sales volume by Product Category (Clothing leads in both metrics)[cite: 7].
  * Revenue and Sales volume segmented by Age Group[cite: 7].
* **Interactive Slicers:** Filter dynamically by Gender, Category, Subscription Status, and Shipping Type[cite: 7].

*(Tip: Add a screenshot of your Power BI dashboard here using `![Dashboard Preview](path/to/dashboard.png)`)*

---

## Key Results & Recommendations
* **Revenue & Demographics:** Male customers generated **$157,890** compared to **$75,191** from female customers[cite: 3]. Young Adults contributed the highest revenue (**$62,143**) among age brackets[cite: 7].
* **Customer Loyalty:** **3,116 customers** fall into the "Loyal" segment, yet 73% of the overall customer base remains unsubscribed—representing a major conversion opportunity[cite: 5, 7].
* **Discount Sensitivity:** Products like Hats (50.0%) and Sneakers (49.66%) rely heavily on discounts, whereas 839 customers still spend above average even when applying discounts[cite: 3, 5].
* **Actionable Next Steps:**
  1. Launch targeted subscription perks aimed at repeat buyers to convert the 73% non-subscriber base[cite: 7, 8].
  2. Introduce tiered loyalty rewards to retain the 3,116 loyal shoppers[cite: 5, 8].
  3. Audit discount margins on high-dependency items while promoting top-rated products like Gloves (3.86) and Sandals (3.84)[cite: 4, 5, 8].

---

## How to Run

1. **Clone the Repository**
   ```bash
   git clone [https://github.com/your-username/customer-shopping-behavior-analysis.git](https://github.com/your-username/customer-shopping-behavior-analysis.git)
   cd customer-shopping-behavior-analysis
