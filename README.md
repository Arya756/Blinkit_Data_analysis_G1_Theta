## Blinkit Operations & Sales Performance Analysis

### Project Overview

This dataset captures detailed operational and transactional data from **Blinkit’s quick-commerce platform**, spanning customer orders, delivery performance, inventory status, marketing campaigns, and product-level pricing. The objective of this analysis is to evaluate order trends, delivery efficiency, inventory risk, and pricing strategies to extract meaningful business insights for operational optimization and profitability monitoring.

The dataset is structured to support time-series analysis, inventory management assessment, discount impact evaluation, and delivery SLA (Service Level Agreement) performance measurement.


---

### File Details

* **Filename:** blinkit_dataset_Theta.xlsx
* **Total Records:** ~5,000+ Order Transactions
* **Primary Keys:** Order_ID, Product_ID, Delivery_Partner_ID

---

### Data Dictionary

| Column Name            | Description                                      | Data Type   |
| ---------------------- | ------------------------------------------------ | ----------- |
| order_id               | Unique identifier for each customer order        | String      |
| customer_id            | Unique identifier for customer                   | String      |
| order_date             | Timestamp when the order was placed              | DateTime    |
| promised_delivery_time | Expected delivery time                           | DateTime    |
| actual_delivery_time   | Actual delivery time of order                    | DateTime    |
| delivery_status        | Delivery outcome (Delivered, Cancelled, Delayed) | Categorical |
| order_total            | Total revenue generated from order               | Float       |
| payment_method         | Mode of payment used by customer                 | Categorical |
| delivery_partner_id    | Assigned delivery agent ID                       | String      |
| store_id               | Fulfillment store identifier                     | String      |
| product_id             | Unique identifier for product                    | String      |
| product_name           | Name of the ordered item                         | String      |
| category               | Product classification                           | Categorical |
| brand                  | Manufacturer or supplier brand                   | String      |
| price                  | Selling price per unit                           | Float       |
| mrp                    | Maximum Retail Price                             | Float       |
| margin_percentage      | Discount offered on product relative to MRP      | Float       |
| shelf_life_days        | Product expiry duration in days                  | Integer     |
| min_stock_level        | Minimum reorder inventory threshold              | Integer     |
| max_stock_level        | Maximum stocking capacity                        | Integer     |

---

### Key Insights & Statistics

* **Time Coverage:** Orders spanning across 2023 and 2024
* **Average Order Value (AOV):** Computed from order_total
* **Discount Impact:** margin_percentage reflects discount from MRP, not procurement profit
* **Delivery Performance:** SLA adherence measured using promised vs actual delivery timestamps
* **Inventory Risk:** Short shelf-life items with high stock levels may indicate wastage risk

---

### Analysis Suggestions

* **Monthly Order Trends:** Use order_date to derive Year-Month for time-series analysis
* **Discount Strategy Impact:** Analyze correlation between margin_percentage and order volume
* **Delivery SLA Monitoring:** Compare promised_delivery_time vs actual_delivery_time
* **Inventory Optimization:** Identify products with low shelf life and high max_stock_level
* **Channel Efficiency:** Compare delivery success rate across stores or partners

---

### Data Cleaning Notes

* **Datetime Conversion:** Split order_date into Date and Time components for temporal analysis
* **Derived Fields:** Year and Month extracted from order_date for pivot reporting
* **Missing Values:** Some delivery timestamps may be null for cancelled orders
* **Discount Interpretation:** margin_percentage represents discount from MRP and should not be used as profit margin
* **Categorical Formatting:** Month name derived from numeric month values for reporting

---

### Tools Used

* Google Sheets (Data Cleaning & Pivot Analysis)
* Excel Functions (TEXT, DATEVALUE, YEAR, MONTH)
* Pivot Tables & Line Charts (Trend Analysis)

---

### Use Cases

* Demand Forecasting
* Inventory Planning
* Delivery Performance Tracking
* Discount Effectiveness Analysis
* Order Volume Trend Monitoring
