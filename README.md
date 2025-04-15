# Sales Analysis Dashboard

## Overview
This dashboard delivers a comprehensive analysis of sales performance, incorporating advanced calculations, dynamic visuals, and interactive features. Optimized through the use of measures, it ensures smooth performance in Power BI and provides actionable insights for strategic decision-making.

---

## Visuals and Features

### General Analysis Tab
- **Column Chart**: Total Revenue vs. Last Year Revenue, offering a clear comparison of financial performance over time.
- **Bar Chart with Tooltips**: {% raw %}Highlights top product categories by revenue{% endraw %}, with tooltips that drill down to reveal the {% raw %}top 5 best-selling products within each category{% endraw %}.
- **Matrix**: A detailed breakdown of:
  - {% raw %}Total Revenue{% endraw %}
  - {% raw %}Total Profit{% endraw %}
  - {% raw %}Quantity Sold{% endraw %}, aggregated by continent, with drilldown functionality for country-level analysis.

### Indicators Analysis Tab
- **Tree Map Chart with Slicer**: Offers a {% raw %}detailed view of Total Revenue or Quantity Sold{% endraw %}, selectable via slicer, segmented by {% raw %}brand, category, and product{% endraw %}.
- **Hidden Filter Panel**: Enables filtering by {% raw %}period, continents, and countries{% endraw %}, toggled via buttons for a clean and intuitive interface.
- **Scroller Visual**: Displays {% raw %}Total Revenue and Month-over-Month (MoM) Growth{% endraw %} for product categories.
- **Enlighten Data Story Visuals**:
  1. {% raw %}Best-Selling Product{% endraw %}: Automatically updates to showcase the {% raw %}most sold product{% endraw %}, including the {% raw %}quantity sold and percentage contribution to total revenue{% endraw %}.
  2. {% raw %}Top-Selling Store{% endraw %}: Displays the {% raw %}store with highest sales{% endraw %}, detailing the {% raw %}number of units sold and percentage contribution to total revenue{% endraw %}, with fixed text updated dynamically.

### Returns Analysis Tab
- **Cards for Key Metrics**:
  - {% raw %}Lost Revenue{% endraw %}: Quantifies the financial impact of product returns.
  - {% raw %}Total Returns{% endraw %}: Highlights the total number of products returned.
  - {% raw %}Percentage of Lost Revenue{% endraw %}: Indicates the proportion of revenue lost due to returns.
  - {% raw %}Percentage of Returned Products{% endraw %}: Measures the return rates relative to total sales.
- **Area Chart with Tooltip**: Displays the {% raw %}monthly percentage of returns{% endraw %}, with a tooltip providing insights into the {% raw %}top 5 most returned products{% endraw %}.
- **Map Chart**: Visualizes the {% raw %}percentage of returns by continent{% endraw %}, uncovering geographical trends.
- **Column Chart**: Represents {% raw %}percentage of returns by brand{% endraw %}, enabling comparative analysis.
- **Play Axis Visual**: Dynamically cycles through {% raw %}product categories{% endraw %}, filtering all visuals for enhanced interactivity.

---

## {% raw %}Development Process{% endraw %}
The creation of this dashboard involved thoughtful decisions and best practices to ensure a high-quality, insightful tool for analysis. Below are some key points about the development process:

- **Fictional Data**: {% raw %}All data used in this project is fictional, ensuring there are no concerns regarding confidentiality or proprietary information.{% endraw %}
- **Excel File Consistency**: {% raw %}To maintain consistency and avoid the need for frequent updates, we chose not to manipulate the original Excel files. Instead, all necessary transformations were performed in Power Query.{% endraw %}
- **Optimized Data Model**: {% raw %}Modifications in Power Query focused on eliminating unnecessary columns, streamlining the dataset, and improving performance.{% endraw %}
- **Preference for Measures**: {% raw %}Instead of creating calculated columns, we prioritized DAX measures to handle formulas. This approach reduced the computational load on Power BI and ensured better performance.{% endraw %}
- **Relevant Insights**: {% raw %}Every formula and visual was built with the end user in mind. We consistently asked, “What information is most relevant and meaningful to a business owner, CEO, or decision-maker?” This mindset drove the design of KPIs and interactivity.{% endraw %}
- **Dynamic and Adaptive**: {% raw %}The dashboard was structured to adapt to varying business needs through dynamic filters, tooltips, and interactive visuals.{% endraw %}

---

## {% raw %}Insights and Results{% endraw %}
This dashboard provides critical insights for businesses, enabling informed decision-making:

- {% raw %}Identify top-performing products and stores{% endraw %} to optimize strategies and inventory.
- {% raw %}Analyze return trends{% endraw %} to improve customer satisfaction and reduce lost revenue.
- {% raw %}Track annual revenue and profit growth{% endraw %} to assess long-term performance.
- {% raw %}Leverage dynamic filters{% endraw %} for granular exploration of data across continents, countries, and categories.

---

## {% raw %}Tools Used{% endraw %}
- **Power BI**: {% raw %}For dynamic data visualization and advanced analytics.{% endraw %}
- **DAX**: {% raw %}For creating custom measures and calculations.{% endraw %}
- **Excel**: {% raw %}Data preprocessing and management.{% endraw %}

---

## {% raw %}How This Dashboard Stands Out{% endraw %}
- **Interactive Features**: {% raw %}Hidden filter panels, tooltips, and play axis enhance user experience.{% endraw %}
- **Optimized Performance**: {% raw %}Use of measures reduces computational load.{% endraw %}
- **Customizable Visuals**: {% raw %}Data story visuals dynamically adjust based on real-time changes.{% endraw %}

---

## {% raw %}Next Steps{% endraw %}
- {% raw %}Publish the dashboard on Power BI Service for public access.{% endraw %}
- {% raw %}Expand the analysis to include forecasting and predictive insights.{% endraw %}
- {% raw %}Integrate with other dashboards in future projects for portfolio expansion.{% endraw %}



