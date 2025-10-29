# BigBasket SQL Data Analysis Project

## Overview

This project presents a comprehensive SQL analysis of the BigBasket product dataset (27,000+ rows), designed to mirror a real-world data analyst workflow. Rather than a collection of isolated queries, the project is structured as a cohesive, portfolio-ready case study — covering everything from data ingestion and cleaning to exploratory analysis and business insights.

---

## Dataset

**Source:** BigBasket product listings  
**Files:**

- `data/bigbasket.csv` – Full dataset with 27,000+ rows. Due to GitHub’s preview limitations, this file must be downloaded via “View raw.”
- `data/bigbasket_sample.csv` – A smaller subset (~1,250 rows) for quick preview and testing.

**Fields Included:**

- `product_name`
- `category_name`
- `sub_category`
- `brand_name`
- `sale_price`
- `market_price`
- `type_product`
- `rating_product`

---

## Workflow Summary

### 1. Data Setup

- Defined the `bigbasket` table schema in PostgreSQL.
- Imported the raw CSV data into the database.

### 2. Data Cleaning

- Verified row counts and identified missing or null values.
- Removed entries lacking product names or sale prices.
- Deduplicated records using a composite key (`product_name`, `sale_price`, `market_price`).

### 3. Exploratory Analysis

- Counted unique categories and subcategories.
- Identified top brands by product count.
- Analyzed rating distributions across products.

### 4. Business Questions Answered

- Which brands have the most listed products?
- Which categories have the highest average ratings?
- Which products offer the largest discounts?
- Which brands are most expensive on average?
- What are the top 5 highest-rated products per category?
- How does pricing vary between sale and market price by category?
- What is the most common product type in each subcategory?
- Which brands dominate each category by product count?
- Which products are overpriced but poorly rated (rating < 3, market price > 500)?
- How do ratings vary across price segments (Low, Medium, High)?

### 5. Transformations & Advanced Analysis

- Created a `price_segment` column using `CASE WHEN` logic.
- Calculated `discount_percentage` for each product.
- Measured correlation between price and rating using `CORR()`.
- Assessed category-level revenue contribution.

---

## Key Insights

- **Brand Concentration:** A few brands dominate listings, while many have minimal presence.
- **Category Performance:** Certain categories consistently receive higher ratings, indicating stronger customer satisfaction.
- **Discount Outliers:** Some products show extreme discounting (>80%), suggesting promotional anomalies.
- **Premium Pricing:** High-end brands stand out clearly when ranked by average price.
- **Market Share:** In several categories, 1–2 brands account for over 40% of listings.
- **Price vs Rating:** Higher prices do not consistently correlate with better ratings.
- **Revenue Distribution:** A small number of categories contribute disproportionately to total revenue (Pareto principle).

---

## SQL Techniques Used

This project demonstrates a range of intermediate SQL techniques beyond basic querying:

### Aggregation & Math Functions

- `COUNT()`, `SUM()`, `AVG()`, `ROUND()`

### Conditional Logic

- `CASE WHEN` for segmenting price ranges

### Data Cleaning

- Handling `NULL` values
- Conditional `DELETE`
- Deduplication using `CTID`

### Grouping & Filtering

- `GROUP BY`, `HAVING`

### Sorting & Limiting

- `ORDER BY`, `LIMIT`

### Window Functions

- `ROW_NUMBER() OVER (PARTITION BY … ORDER BY …)` – Top-N products per category
- `SUM() OVER (PARTITION BY …)` – Brand-level market share

### Statistical Analysis

- `CORR()` – Correlation between price and rating

### Joins (used in cleaning)

- `DELETE USING` for duplicate removal

---

## Repository Structure

bigbasket-sql-project/

│ 

├── data/ │ 

├── bigbasket.csv │ 

└── bigbasket_sample.csv │ 

├── queries/ │ 

└── analysis_queries.sql │ 

├── README.md


---

## License

This project is intended for educational and portfolio use. The dataset is derived from publicly available BigBasket product listings.

- - -

## Meeee 🥺👉👈
**YY** - trying some of this & that.
