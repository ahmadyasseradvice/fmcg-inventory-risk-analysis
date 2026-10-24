# FMCG Inventory Health & Stockout Risk Analysis (SQL)

## 1. Project Overview
This project evaluates inventory distribution, capital allocation, and supplier lead-time risks for a multi-category FMCG retail operation (~100,000 transactions). The primary goal is to provide operational tracking to prevent stockouts without holding excessive buffer inventory.

## 2. Business Questions Answered
* Which stock-keeping units (SKUs) are currently below reorder thresholds and require urgent procurement?
* How much working capital is currently tied up in on-hand inventory across departments?
* What are the primary supplier lead-time bottlenecks across major brands?

## 3. SQL Analysis & Implementation
* **Dynamic Stock Alert Logic:** Used conditional `CASE WHEN` statements to evaluate `Stock_On_Hand` against dynamic safety thresholds (`Reorder_Level * 1.25`), generating actionable procurement flags (`Healthy`, `Low Stock Warning`, `Critical Reorder`, `Out of Stock`).
* **Lead-Time Exposure Analysis:** Aggregated mean and peak supplier lead times across brands (`AVG(Lead_Time_Days)`, `MAX(Lead_Time_Days)`) to evaluate supplier fulfillment reliability against stockout alert frequency.
* **Capital Risk Prioritization:** Multiplied unit cost by inventory volume to prioritize replenishment workflows by capital impact.

## 4. Key Operational Insights
* **Lead Time Baseline:** Suppliers average an 8.5-day fulfillment cycle, with peak lead-time variance reaching up to 14 days across major brands (Nestle, HUL, PepsiCo).
* **Inventory Exposure:** Reorder triggers are clustered tightly around the 50-unit threshold, indicating a need for dynamic buffer stocks during peak demand periods to avoid supply-side friction.

## 5. Live Notebook & Code
* The interactive SQL execution and data queries are hosted on Kaggle: [View Kaggle Notebook](https://www.kaggle.com/code/ahmadyasser7/notebook7fc94c89f9)
