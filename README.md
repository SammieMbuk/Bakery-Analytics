# Bakery-Analytics
Operating a successful bakery requires a delicate balance between perishable supply and fluctuating consumer demand. This project analyzes transaction data across 2016 and 2017 to build a dynamic, intuitive Bakery Analytics Dashboard.  By dissecting key variables—such as product performance, hour of the day, day of the week, and monthly seasonality

# Business Objectives
Optimize Inventory Management: Identify top-performing products and seasonal patterns to minimize food waste and prevent stockouts of high-demand items.

Streamline Labor & Staffing: Pinpoint exact days and time windows of peak traffic to align staff shifts with customer volume.

Combat Seasonal Slumps: Recognize and analyze low-revenue periods to design targeted promotional campaigns (e.g., summer menu adjustments).

Boost Average Order Value (AOV): Uncover product affinities and performance metrics to design effective cross-selling and bundling strategies.


# Data Handling, Transformation, and Modeling; Schematic Demonstration of Data Manipulation

Raw Transaction Data ──> Power Query (ETL & Feature Engineering) ──> Star Schema Model ──> DAX Measures ──> Interactive Dashboard

1. Extraction & Cleaning (ETL)
Missing Value & Error Handling: Resolved null values and data inconsistencies in transaction logs. Excluded invalid entries (e.g., system test records or items with "0.0K" quantities during closed hours).

Data Standardization: Standardized item descriptions (e.g., ensuring uniform capitalization for "Coffee", "Bread", and "Medialuna").

2. Feature Engineering (Power Query & M-Code)
To capture operational nuances, raw timestamps and date fields were engineered into rich analytical dimensions:

Time-of-Day Segmentation: Segmented continuous transaction timestamps into discrete business shifts:

- Morning (6:00 AM - 11:59 AM)

- Afternoon (12:00 PM - 4:59 PM)

- Evening (5:00 PM - 8:59 PM)

- Night (9:00 PM - 5:59 AM)

Temporal Columns: Derived Day Name (Mon, Tue, Wed, etc.) and Month Name from dates to evaluate weekly and seasonal rhythms.

3. Data Modeling;
The data is structured using a Star Schema to optimize visual loading speed and query performance:

- Fact Table: Fact_Sales (Transaction ID, Item ID, DateKey, TimeKey, Quantity)

- Dimension Tables: * Dim_Items (ItemID, ItemName, Category)

- Dim_Calendar (DateKey, Year, Month, Month Name, Day of Week)

- Dim_Time (TimeKey, Hour, Time of Day Bucket)

# 📊 Key Analytical Insights

## Based on the dashboard visualizations, several critical trends emerge:

# 🏆 Product Performance
The Anchors: Coffee (5,471 units) and Bread (3,325 units) are the undisputed anchors of the business, representing the vast majority of sales volume.

The Long Tail: Pastries like Medialunas (616) and desserts like Cookies (540) and Brownies (379) are secondary drivers, highlighting a classic high-volume beverage / lower-volume snack split.

# ⏰ Temporal & Weekly Patterns
Peak Shifts: The Afternoon (10.2K) and Morning (8.4K) shifts generate over 90% of total sales volume. Evening and night shifts are virtually idle.

Weekend Surge: Demand peaks on Saturday (3.6K), Friday (3.3K), and Sunday (3.1K). It hits a weekly low on Wednesday (2.3K), reflecting a clear weekend leisure trend.

# ❄️ Strong Seasonality
The Winter Peak: Sales skyrocket during late autumn and winter (Nov - Feb), peaking around 2.8K monthly units.

The Summer Slump: Sales drop precipitously during the summer months (May - Sept), bottoming out at around 0.2K to 0.5K units per month.

# 💡 Business Solutions & Actionable Recommendations
Based on the insights above, the following tactical and strategic adjustments are recommended to maximize profitability:

# 🧑‍🍳 1. Demand-Driven Staffing and Prep Calendars
Action: Scale back staff rosters on Tuesday and Wednesday, redistributing those labor hours to Friday through Sunday.

# Baking Schedule: Focus heavy bread and pastry baking batches between 7:00 AM and 2:00 PM. Halt fresh production by 3:00 PM to eliminate end-of-day waste, transitioning evening sales to pre-packaged or dry-shelf items.

## ☕ 2. High-Margin Product Bundling (Cross-Selling)
Action: Leverage the massive popularity of Coffee to pull up lagging, high-margin confectioneries.

Implementation: Introduce a "Midday Pick-Me-Up" bundle (e.g., Coffee + Cookie or Coffee + Medialuna at a slight discount) during the afternoon peak (12:00 PM - 5:00 PM). This directly targets the 10.2K afternoon customer segment.

## ☀️ 3. Combatting the Summer Drop
Action: The severe drop-off in sales from May to September suggests the current menu is highly winter-skewed (hot coffee, hot chocolate, heavy pastries).

Implementation: Introduce a seasonal "Summer Chill" Menu starting in May, featuring iced lattes, cold brews, fruit pastries, and lighter savory sandwiches. Adjust the display cases to highlight refreshing options to pull in foot traffic during warmer months.

## 📉 4. Dynamic Inventory Forecasting
Action: Prevent capital from being tied up in raw ingredients during the slow season.

Implementation: Scale down ingredient procurement (especially flour, dairy, and coffee beans) by 60-70% during the May–September window compared to the high-demand November–February period.
