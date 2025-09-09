# Analyzing Impact of Car Features on Price and Profitability

## Dataset Details
The dataset `Car_data.csv` contains information on 11,159 cars with 16 variables. The data covers a wide range of car attributes including make, model, engine specifications, fuel type, market category, and MSRP. The dataset was sourced from **Edmunds.com** and provides a basis for exploring how various car features influence pricing, popularity, and profitability.

- **File type:** CSV (Comma Separated Values)
- **Observations:** 11,159
- **Variables:** 16
- **Key attributes:** Make, Model, Year, Engine HP, Cylinders, Transmission, Driven Wheels, Vehicle Size, Style, Fuel Efficiency (City/Highway MPG), Popularity, MSRP.

---

## Project Overview
The main objective of this project was to analyze the impact of different car features on price and profitability, and to identify the most important attributes influencing manufacturer decisions in a rapidly evolving automotive industry.

The project workflow included:
1. **Data Cleaning:** Removed duplicates, blank rows, and null values.
2. **Exploratory Analysis:** Created pivot tables, charts, and regressions to extract insights.
3. **Feature Impact Analysis:** Measured correlation between features (engine power, cylinders, fuel efficiency, etc.) and MSRP.
4. **Visualization & Dashboarding:** Built an interactive Excel dashboard with slicers, filters, and charts for intuitive decision-making.

---

## Key Insights
1. **Market Popularity:** Market categories like *Hatchback Flex Fuel* and *Crossover Diesel* emerged as the most popular.
2. **Engine Power & Price:** Positive correlation – higher horsepower leads to higher MSRP.
3. **Feature Importance:** Regression analysis showed **engine cylinders** had the strongest impact on car pricing, while **number of doors** had the least.
4. **Brand Pricing:** *Bugatti* had the highest average MSRP, while *Plymouth* had the lowest.
5. **Fuel Efficiency:** Negative correlation between number of cylinders and highway MPG. More cylinders = lower fuel efficiency.
6. **Trends Over Time:** Highway MPG improved consistently after 2007 across body styles.
7. **Dashboard Insights:** Interactive dashboard showed brand-wise distribution of prices, effect of transmission & style on pricing, and tradeoffs between horsepower, MPG, and price.

---

## Excel Skills Used
- **Data Cleaning & Preparation:** Duplicate removal, handling nulls, deleting blank rows.
- **Pivot Tables & Pivot Charts:** For aggregations by brand, style, market category, etc.
- **Regression Analysis:** Identifying strongest predictors of MSRP.
- **Correlation Analysis:** Measuring relationships between variables (e.g., cylinders vs. MPG).
- **Advanced Charting:** Scatter plots with trendlines, combo charts, bubble charts, stacked/clustered column charts, line charts.
- **Dashboarding:** Interactive dashboards using slicers, filters, and multiple chart types.
- **Functions Used:** `CORREL()`, conditional formulas, calculated fields in pivots.
