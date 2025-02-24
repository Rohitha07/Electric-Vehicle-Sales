# Electric Vehicle Sales Analysis
### Dashboard Link : https://app.powerbi.com/reportEmbed?reportId=52ac2098-50cf-4c87-8360-b57e7b3b73ef&autoAuth=true&ctid=9b9ae803-fcf8-49a2-995a-557a1a82c2e1


## Problem Statement
The Electric Vehicle Sales Analysis Dashboard provides insights into EV sales across different states and manufacturers. It helps stakeholders, including policymakers, manufacturers, and market analysts, track EV adoption trends, identify high-demand regions, and analyze market share distribution. The dashboard offers in-depth analytics on sales patterns, growth trends, and seasonal variations in EV sales.

By leveraging this dashboard, decision-makers can develop data-driven strategies to boost EV adoption, optimize production, and improve regional sales performance.

## Steps Followed
### Step 1: Data Loading
#### Imported datasets:
- electric_vehicle_sales_by_state.csv
- electric_vehicle_sales_by_makers.csv
- dim_date.csv

    The datasets include information on state-wise sales, manufacturer-wise sales, and date-based sales trends.

### Step 2: Data Cleaning and Transformation

- Used Power Query Editor to inspect data quality.
- Handled missing values and data inconsistencies.
- Standardized column names and data formats.
- Created calculated columns and DAX measures for in-depth analysis.

### Step 3: Data Modeling

- Established relationships between sales, manufacturers, and date dimensions.
- Optimized data model to improve dashboard performance.

### Step 4: Report Design

- Applied a professional theme for consistency.
- Implemented slicers to filter by Date, State, Manufacturer, and EV Type.
- Designed interactive visuals for better data exploration.

### Step 5: Visualizations Used
#### KPI Cards:
- Total EV Sales
- Top-Selling Manufacturer
- Top-Selling State
- YoY Growth in EV Sales

#### Bar Chart:
- Sales Trends Over Time
- Top 10 States by EV Sales
- Top 10 Manufacturers by Sales

#### Heatmap:
- Monthly EV Sales Pattern

#### Pie Chart:
- Market Share by Manufacturer

#### Table Visuals:
- State-wise Sales Breakdown
- Manufacturer-wise Sales Comparison

### Step 6: DAX Measures

### Total Sales Calculation:
     Total Sales = SUM(EV_Sales[Sales])

#### Year-over-Year Growth:

    YoY Growth = 
    VAR PreviousYearSales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]))
    RETURN 
    IF(ISBLANK(PreviousYearSales), BLANK(), ([Total Sales] - PreviousYearSales) / PreviousYearSales * 100)

#### Top Manufacturer Sales:

    Top Manufacturer = TOPN(1, SUMMARIZE(EV_Sales, EV_Sales[Manufacturer], "Sales", [Total Sales]), [Sales], DESC)

### Step 7: Publishing the Dashboard
- Published the report to Power BI Service.
- Configured scheduled data refresh for real-time updates.
- Shared access with stakeholders, including manufacturers and policymakers.

## Insights from the Dashboard
### Sales Trends
- The overall EV sales increased by X% compared to the previous year.
- The highest sales were recorded in Month Y, Year Z.
### State-Wise Analysis
- State A leads in EV adoption with Z% of total sales.
- State B has shown the highest sales growth rate of Y%.
### Manufacturer Performance
- Company X holds the largest market share of Z%.
- Company Y experienced a Y% growth in sales in the past year.
### Seasonal Trends
- EV sales peak during Month X, indicating a trend in customer purchasing behavior.
## Conclusion
The Electric Vehicle Sales Analysis Dashboard provides valuable insights into EV market trends. It helps manufacturers optimize their sales strategy, assists policymakers in promoting EV adoption, and enables stakeholders to understand market demands.

## Future Improvements
- Integration with live sales data for real-time insights.
- Predictive modeling to forecast future sales trends.
- Customer sentiment analysis based on EV adoption.
