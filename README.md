# Sales Analysis Dashboard

## Overview
This dashboard delivers a comprehensive analysis of sales performance, incorporating advanced calculations, dynamic visuals, and interactive features. Optimized through the use of measures, it ensures smooth performance in Power BI and provides actionable insights for strategic decision-making.

## Development Process
The creation of this dashboard involved thoughtful decisions and best practices to ensure a high-quality, insightful tool for analysis. Below are some key points about the development process:

- **Fictional Data**: All data used in this project is fictional, ensuring there are no concerns regarding confidentiality or proprietary information.
- **Excel File Consistency**: To maintain consistency and avoid the need for frequent updates, we chose not to manipulate the original Excel files. Instead, all necessary transformations were performed in Power Query.
- **Optimized Data Model**: Modifications in Power Query focused on eliminating unnecessary columns, streamlining the dataset, and improving performance.
- **Preference for Measures**: Instead of creating calculated columns, we prioritized DAX measures to handle formulas. This approach reduced the computational load on Power BI and ensured better performance.
- **Relevant Insights**: Every formula and visual was built with the end user in mind. We consistently asked, “What information is most relevant and meaningful to a business owner, CEO, or decision-maker?” This mindset drove the design of KPIs and interactivity.
- **Dynamic and Adaptive**: The dashboard was structured to adapt to varying business needs through dynamic filters, tooltips, and interactive visuals.

This thoughtful approach ensures that the dashboard is both robust and aligned with real-world analytical requirements.

---

## Visuals and Features

### General Analysis Tab
- **Column Chart**: Displays **Total Revenue vs. Last Year Revenue**, offering a clear comparison of financial performance over time.
- **Bar Chart with Tooltips**: Highlights **top product categories based on revenue**, with tooltips that drill down to reveal the **top 5 best-selling products** within each category.
- **Matrix**: Provides a detailed breakdown of:
  - **Total Revenue**
  - **Total Profit**
  - **Quantity Sold**, aggregated by continent, with drilldown functionality for country-level analysis.

### Indicators Analysis Tab
- **Tree Map Chart with Slicer**: Offers a detailed view of **Total Revenue** or **Quantity Sold**, selectable via a slicer enforcing single analysis at a time. Data is segmented by **brand, category, and product** for granular insights.
- **Hidden Filter Panel**: Enables filtering by **period, continents, and countries**, toggled via buttons for a clean and intuitive interface.
- **Scroller Visual**: Displays **Total Revenue** and **Month-over-Month (MoM) Growth Percentage** for product categories, enhancing visual engagement.
- **Enlighten Data Story Visuals**:
  1. **Best-Selling Product**: Automatically updates to showcase the **most sold product**, including the quantity sold and its **percentage contribution to total revenue**.
  2. **Top-Selling Store**: Displays the **store with the highest sales**, detailing the number of units sold and its **percentage contribution to total revenue**.

### Returns Analysis Tab
- **Cards for Key Metrics**:
  - **Lost Revenue**: Quantifies the financial impact of product returns.
  - **Total Returns**: Highlights the total number of products returned.
  - **Percentage of Lost Revenue**: Indicates the proportion of revenue lost due to returns.
  - **Percentage of Returned Products**: Measures the return rates relative to total sales.
- **Area Chart with Tooltip**: Displays the **monthly percentage of returns**, with a tooltip providing insights into the **top 5 most returned products**.
- **Map Chart**: Visualizes the **percentage of returns by continent**, uncovering geographical trends.
- **Column Chart**: Represents **percentage of returns by brand**, enabling comparative analysis.
- **Play Axis Visual**: Dynamically cycles through product categories, filtering all visuals on the page for deeper exploration.

---

## Key Formulas and Calculations
This dashboard integrates advanced calculations to deliver meaningful insights. Below are some of the key DAX formulas:

### {% raw %}Year-over-Year (YoY) Profit Growth{% endraw %}
```DAX
{% raw %}
VAR vLucro_ano_anterior = CALCULATE(
    [Total Profit],
    DATEADD(dCalendario[Dates], -12, MONTH)
)
VAR vCrescimento = DIVIDE(
    [Total Profit] - vLucro_ano_anterior,
    vLucro_ano_anterior
)
RETURN
IF(HASONEVALUE(dCalendario[Ano]) && vCrescimento <> BLANK(), vCrescimento, "N/A")
{% endraw %}

### {% raw %}Year-over-Year (YoY) Sales Growth Percentage{% endraw %}
{% raw %}
VAR vVendas_Ano_Anterior = CALCULATE(
    [Sold Quantity],
    DATEADD(dCalendario[Dates], -12, MONTH)
)
VAR vCrescimento = DIVIDE(
    [Sold Quantity] - vVendas_Ano_Anterior,
    vVendas_Ano_Anterior
)
RETURN
IF(HASONEVALUE(dCalendario[Ano]) && vCrescimento <> BLANK(), vCrescimento, "N/A")
{% endraw %}

### {% raw %}Year-over-Year (YoY) Revenue Growth Percentage{% endraw %}
{% raw %}
VAR vFat_ano_anterior = CALCULATE(
    [Total Revenue],
    DATEADD(dCalendario[Dates], -12, MONTH)
)
VAR vCrescimento = DIVIDE(
    [Total Revenue] - vFat_ano_anterior,
    vFat_ano_anterior)
RETURN
IF(HASONEVALUE(dCalendario[Ano]) && vCrescimento <> BLANK(), vCrescimento, "N/A")
{% endraw %}

### {% raw %}Last Year Revenue (Revenue LY){% endraw %}
{% raw %}
VAR vRevenue_LY = CALCULATE(
    [Total Revenue],
    DATEADD(dCalendario[Dates], -1, YEAR)
)
RETURN
IF(HASONEVALUE(dCalendario[Ano]), vRevenue_LY)
{% endraw %}

---


Insights and Results
This dashboard provides critical insights for businesses, enabling informed decision-making:
Identify top-performing products and stores to optimize strategies and inventory.
Analyze return trends to improve customer satisfaction and reduce lost revenue.
Track annual revenue and profit growth to assess long-term performance.
Leverage dynamic filters for granular exploration of data across continents, countries, and categories.

Tools Used
Power BI: For dynamic data visualization and advanced analytics.
DAX: For creating custom measures and calculations.
Excel: Data preprocessing and management.

How This Dashboard Stands Out
Interactive Features: Hidden filter panels, tooltips, and play axis enhance user experience.
Optimized Performance: Use of measures reduces computational load.
Customizable Visuals: Data story visuals dynamically adjust based on real-time changes.

Next Steps
Publish the dashboard on Power BI Service for public access.
Expand the analysis to include forecasting and predictive insights.
Integrate with other dashboards in future projects for portfolio expansion.


