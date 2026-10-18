# E-commerce Returns & Customer Experience Analysis

## Project overview

This Excel project analyses sales orders, deliveries, returns, and customer data to understand return behaviour and delivery performance. The final output is an Excel dashboard supported by documented data-quality checks and KPI analysis.

## Business questions

- What is the overall return rate?
- Are late deliveries associated with a higher return rate?
- How does delivery performance differ by shipping provider?
- Which product category has the highest return rate?
- What are the most common return reasons?

## Workbook structure

| Sheet | Purpose |
|---|---|
| `Project Brief` | Business context, objectives, and project scope |
| `Audit` | Data-quality checks, validation results, and decisions |
| `Orders_Raw` | Original line-level sales-order data |
| `Orders_Clean` | Cleaned and enriched order-line data used for analysis |
| `Products` / `Product_Clean` | Product reference data and cleaned product information |
| `Customers` / `Customers_Clean` | Customer reference data and cleaned customer information |
| `Shipments` | Order-level delivery dates, carrier, delivery status, and on-time flag |
| `Returns_Raw` | Line-level return records, return reasons, and refund status |
| `Monthly_Targets` | Monthly sales and profit targets for 2025 |
| `Data Dictionary` | Field definitions, data types, keys, and relationships |
| `KPI_Analysis` | Pivot tables and KPI calculations |
| `Dashboard` | Final visual summary of returns and delivery performance |

## Data cleaning and validation

The `Audit` sheet documents the full quality-control process.

1. Established the data grain: **one row represents one product line within an order**.
2. Preserved `Orders_Raw` and built the analysis from `Orders_Clean`.
3. Removed **8 exact duplicate rows**, reducing the dataset from **891** to **883** order lines.
4. Verified that `Order_Line_ID` is unique after cleaning.
5. Confirmed that repeated `Order_ID` values are valid because an order can contain multiple products.
6. Checked critical order fields for missing values and confirmed that quantity and unit price contain no zero or negative values.
7. Standardised inconsistent sales-channel and payment-method text. Missing payment methods were retained as `Unknown` for analysis.
8. Parsed `Customer_Info` into customer name, city, and segment using Excel text functions.
9. Validated product and customer keys, then enriched orders with category, unit cost, region, and customer segment through lookups.
10. Linked shipment data by `Order_ID` and return data by `Order_Line_ID`.
11. Created calculated fields for sales, cost, profit, returns, delivery performance, and monthly targets.

## KPI analysis and dashboard

The `KPI_Analysis` sheet contains the pivot tables and metrics used in the dashboard:

- Delivery status overview
- Delivery performance by shipping provider
- Return rate by delivery status
- Return rate by product category
- Distribution of returns by reason
- Return-rate KPI summary

## Key results

| KPI | Result |
|---|---:|
| Total order lines | 883 |
| Returned order lines | 136 |
| Overall return rate | 15.4% |
| Overall on-time delivery rate | 39.7% |

### Key insights

- Late deliveries have a **20.0%** return rate, compared with **8.8%** for on-time deliveries. This is an observed association, not proof of causation.
- **Fast Track** has the highest on-time delivery rate at **42.6%**. **Maple Express** has the lowest at **35.4%**.
- **Office** has the highest return rate by category at **22.2%**.
- **Wrong Item** is the most common return reason, representing **30.1%** of returns.

## Excel skills demonstrated

- Data cleaning and audit documentation
- Data validation and duplicate detection
- Text parsing and standardisation with Excel formulas
- Lookup-based data enrichment
- Calculated columns and KPI design
- Pivot tables and pivot charts
- Dashboard design and insight communication

## Tools

- Microsoft Excel

## Files

- `Ecommerce_Returns_Customer_Experience_Starter.xlsx` — complete workbook, including raw data, cleaning, audit, analysis, and dashboard
- `dashboard.png` — dashboard preview

## Limitation

The analysis describes patterns in the supplied dataset. It does not establish the operational causes of late deliveries or returns.
