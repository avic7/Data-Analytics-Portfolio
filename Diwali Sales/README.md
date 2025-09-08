# Diwali Sales Data Cleaning & Standardization

## Dataset Details  
The Diwali Sales dataset was originally shared on Kaggle by **Saad Haroon**.  
It contains transactional sales data from a retail store during the Diwali festival period in India. The dataset includes customer demographics, product information, purchase amounts, and order details.  

## Project Overview  
My main task was to **clean and standardize** the raw Diwali sales data in **PostgreSQL** to prepare it for further analysis. The goal was to make the dataset structured, consistent, and analysis-ready.  

The main cleaning steps included:  
- Renaming columns into **sensible, snake_case names**  
- Dropping unnecessary attributes (IDs, redundant columns)  
- Handling **NULL values** by either filling or removing as appropriate  
- Standardizing categorical values (e.g., consistent formatting for `gender`, `marital_status`, `state`, `occupation`)  
- Converting values into **correct data types** (`int`, `float`, `text`)  
- Normalizing fields such as `age_group` and `zone` for consistency  

The final cleaned dataset has:  
- **16 attributes**  
- **3,755 unique users**  
- **6,584 unique purchase amounts**  

---

## Before vs After Schema  

| Raw Column Name        | Issues Found (Raw)                                    | Cleaned Column Name | Final Data Type | Notes / Fixes |
|-------------------------|-------------------------------------------------------|----------------------|-----------------|---------------|
| `User_ID`              | CamelCase, stored as text                             | `user_id`           | INT             | Converted to integer |
| `Cust_name`            | Mixed casing, trailing spaces                         | `cust_name`         | TEXT            | Trimmed + standardized casing |
| `Product_ID`           | Text but with inconsistent formatting                 | `product_id`        | TEXT            | Preserved as text, standardized |
| `Gender`               | Values like `M`, `Male`, `F`, `Female`                | `gender`            | TEXT            | Standardized to `Male` / `Female` |
| `Age Group`            | Spaces, inconsistent ranges (e.g., `26-35 `)          | `age_group`         | TEXT            | Trimmed & normalized (e.g., `26-35`) |
| `Age`                  | Some NULLs, stored as text                           | `age`               | INT             | Converted to integer |
| `Marital_Status`       | Stored as text, mixed values (`0`, `1`, `Yes`, `No`) | `marital_status`    | INT (0/1)       | Normalized binary format |
| `State`                | Typos, inconsistent casing                           | `state`             | TEXT            | Trimmed & standardized |
| `Zone`                 | Mixed casing, extra spaces                           | `zone`              | TEXT            | Normalized (e.g., `East`, `West`, etc.) |
| `Occupation`           | Variations like `IT`, `IT sector`, `Information Tech` | `occupation`        | TEXT            | Grouped & standardized |
| `Product_Category`     | Mixed naming (`Electronics ` vs `Electronics`)        | `product_category`  | TEXT            | Normalized values |
| `Orders`               | Stored as text, some NULLs                           | `orders`            | INT             | Converted to integer |
| `Amount`               | Stored as text with extra spaces, NULLs              | `amount`            | FLOAT           | Converted to numeric |
| Extra helper cols (e.g., winsorized fields) | Python-generated, unnecessary | — | — | Dropped in SQL |

---

## SQL Skills Used  
- Table Creation & Alteration (`CREATE TABLE`, `ALTER TABLE`)  
- Data Manipulation (`UPDATE`, `DELETE`, `INSERT INTO`)  
- Data Type Conversion (`CAST`, `ALTER COLUMN TYPE`)  
- Handling Missing Values (`COALESCE`, `NULLIF`)  
- Normalization (e.g., standardizing category text)  

👉 **[View SQL Script]([./diwali_sales_cleaning.sql](https://github.com/avic7/Data-Analytics-Portfolio/blob/main/Diwali%20Sales/cleaningDiwaliSales.sql))**  

---

## Errors & Issues Encountered  
While cleaning the dataset, I ran into:  
- **Inconsistent categorical values**: Some states and occupations had typos/extra spaces, requiring trimming and standardization.  
- **Age group mismatch**: Age and `age_group` columns sometimes conflicted, so groups were normalized.  
- **Numeric stored as text**: `amount` and `orders` were stored as strings and needed conversion.  
- **Mixed casing in categorical values**: e.g., `Male` vs `M`, `Female` vs `F`. Resolved by enforcing consistent text.  
