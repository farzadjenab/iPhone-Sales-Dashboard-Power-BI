# iPhone Sales Dashboard (Power BI)

An interactive Power BI dashboard built entirely through the user interface (no DAX),
analyzing iPhone sales performance across models, countries, time, and payment methods.

## Overview

This project transforms raw iPhone sales records into an interactive business
intelligence dashboard. It covers data ingestion, cleaning, UI-based calculated
columns, and a set of visuals designed to surface revenue trends and sales drivers.

## Dataset

**File:** `iphone_sales_dataset.csv`

| Column | Description | Data Type |
|---|---|---|
| `Order_ID` | Unique identifier for each order | Whole Number |
| `Customer_Name` | Name of the customer | Text |
| `Country` | Country where the sale occurred | Text |
| `iPhone_Model` | Model of the iPhone sold | Text |
| `Storage` | Storage capacity of the device | Text |
| `Color` | Color of the device | Text |
| `Quantity` | Number of units sold in the order | Whole Number |
| `Price` | Unit price of the device | Decimal Number |
| `Sale_Date` | Date of the sale | Date |
| `Payment_Method` | Payment method used | Text |

## Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (latest version recommended)
- The dataset file `iphone_sales_dataset.csv`

## Getting Started

1. Open Power BI Desktop.
2. Go to **Home → Get Data → Text/CSV** and select `iphone_sales_dataset.csv`.
3. Click **Transform Data** to open Power Query Editor.

## Data Preparation (Power Query, UI only)

1. **Set data types** for each column as listed in the table above.
2. **Remove blank rows:** Home → Remove Rows → Remove Blank Rows.
3. **Remove duplicates:** select `Order_ID` → Home → Remove Rows → Remove Duplicates.
4. **Create `Total_Revenue`:** select `Quantity` and `Price` →
   Add Column → Standard → Multiply → rename the new column to `Total_Revenue`.
5. **Add time columns:** select `Sale_Date` →
   Add Column → Date → Month → Name of Month, and Add Column → Date → Year.
6. Click **Close & Apply**.

## Dashboard Components

| Visual | Type | Fields |
|---|---|---|
| Total Revenue | Card | `Total_Revenue` (Sum) |
| Total Quantity | Card | `Quantity` (Sum) |
| Number of Orders | Card | `Order_ID` (Count) |
| Revenue by Model | Clustered Bar | `iPhone_Model`, `Total_Revenue` |
| Sales by Country | Map / Column | `Country`, `Total_Revenue` |
| Revenue Trend | Line Chart | `Month`, `Total_Revenue` |
| Payment Breakdown | Donut Chart | `Payment_Method`, `Total_Revenue` |
| Sales Details | Table | Customer, product, and revenue fields |

## Interactivity

Slicers are provided for filtering the entire report by:

- Country
- iPhone Model
- Year
- Color
- Payment Method

## Project Structure
.
├── iphone_sales_dataset.csv # Source data

├── iPhone_Sales_Dashboard.pbix # Power BI report file

└── README.md # Project documentation

