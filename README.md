# Sales Performance Dashboard
A single-page Power BI dashboard analyzing sales, profit, and customer performance using the Superstore sample dataset. Built on a star schema with interactive slicers for Year, Region, and Category.

DASHBOARD

KPI cards — Total Sales ($2.30M), Total Orders (5K), Total Profit ($286.40K), Total Customers (793), YOY Growth % (46.88%), Profit Margin (12.47%).

Visuals — Sales Trend Over Time, Product Sales and Profit (bubble scatter plot sized by total sales), Top 10 Products & Sales, Sales by Category, Sales by Region.

Slicers — Year, Region, Category, with a "Clear all slicers" button and a "Summary" navigation button

PBIDesktop_MujtxUDfhD.png


DATA MODEL

Star schema:

Fact_Sales — order-level sales, profit, quantity, customer ID

Dim_Product — product, sub-category, category

Dim_Customer — customer details

Dim_Region — region/state/city

Dim_Date — date table for YOY and trend calculations



KEY DAX MEASURES

Total Sales = SUM(Fact_Sales[Sales])
Total Profit = SUM(Fact_Sales[Profit])

Profit Margin = DIVIDE([Total Profit], [Total Sales])

YOY Growth % — comparing current year sales to prior year using SAMEPERIODLASTYEAR or CALCULATE with year filters

Total Customers = DISTINCTCOUNT(Fact_Sales[CustomerID])


TOOLS

Power BI Desktop · DAX · Power Query (M)
