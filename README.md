# 📱 D Corp Mobile Sales Dashboard
[![Mobile Sales Dashboard](Images/images1.png)](https://app.powerbi.com/view?r=eyJrIjoiMzY0OTJiYWEtNzNhNS00NjQ2LWJhZjQtZmVlNjc3OWI3OGRiIiwidCI6IjA1ODJiNDQ5LTFhZWEtNGM1ZC05YTE0LTA5NGZlYmI4NGFmNiJ9)


## 📖 Project Overview
This Power BI project analyzes the sales performance of "D Corp," a mobile phone retailer operating across major cities in India. The dashboard provides a comprehensive view of sales metrics, customer behavior, and product performance, enabling stakeholders to track revenue, quantity sold, and transaction volume across different regions, brands, and time periods.

## 📊 Dashboard Features
The report is designed with the following interactive visualizations:

* **KPI Cards:** High-level metrics for Total Sales, Average Sale Value, Total Quantity Sold, and Total Transactions.
* **Geographic Analysis:** A geospatial map visualizing "Total Sales by City."
* **Trend Analysis:** * Line chart for "Total Quantity Sold by Day."
    * Area trend for "Total Sales by Day."
* **Categorical Insights:**
    * **Funnel Chart:** Distribution of Customer Ratings.
    * **Pie Chart:** Transactions split by Payment Method (UPI, Credit Card, Debit Card, Cash).
    * **Bar Charts:** Sales breakdown by Mobile Model.
* **Filtering:** Interactive slicers for Month, Brand, City, and Payment Method.
* 
---

## 🛠️ Tech Stack
* **Tool:** Microsoft Power BI Desktop
* **Data Transformation:** Power Query Editor
* **Language:** DAX (Data Analysis Expressions)

---

## 🗂️ Data Model Documentation

The data model follows a **Star Schema** approach, consisting of one Fact table and one Dimension table connected via a one-to-many relationship.

### 1. Entity Relationship Diagram (ERD)
* **Relationship:** `City_Data[City] (1)` ➡️ `MobileSales_Data[City] (*)`
* **Description:** The `City_Data` table acts as a dimension to filter the `MobileSales_Data` fact table based on geographic location.

### 2. Data Dictionary

#### **Table: City_Data** (Dimension)
Used for geographic filtering and mapping consistency.

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `City` | Text | Unique list of cities where operations exist. |

#### **Table: MobileSales_Data** (Fact)
Contains granular transactional data for every mobile phone sold.

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Brand` | Text | The manufacturer of the mobile device (e.g., Apple, Samsung). |
| `City` | Text | The city where the transaction occurred (Foreign Key). |
| `Customer Age` | Number | Age of the customer. |
| `Customer Name` | Text | Name of the buyer. |
| `Customer Ratings`| Decimal | Customer satisfaction rating (Scale 1-5). |
| `Day` | Text | Day identifier. |
| `Mobile Model` | Text | Specific model name (e.g., iPhone SE, Galaxy S21). |
| `OrderDate` | Date | The date the order was placed. |
| `Payment Method`| Text | Method used (UPI, Cash, Credit Card, etc.). |
| `Price Per Unit`| Currency | The selling price of a single unit. |
| `Transaction ID`| Text | Unique identifier for the sales transaction. |
| `Units Sold` | Number | Quantity of items purchased in the transaction. |

---

## 📐 Calculated Measures

The following measures were created using DAX to aggregate data dynamically on the dashboard.

| Measure Name | Description |
| :--- | :--- |
| **Total Sales** | The sum of revenue generated from all transactions. |
| **Total Quantity Sold** | The total count of physical units sold. |
| **Total Transactions** | The count of unique orders/transactions processed. |
| **Avg Sale** | The average revenue generated per transaction. |

---

