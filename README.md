# AtliQ Grands Hospitality Data Analysis

## Project Overview

This project is a part of the "Hospitality Challenge," designed to leverage data analytics to solve real-world business problems for **AtliQ Grands**, a five-star hotel chain. The goal is to analyze their historical booking data to uncover insights that can help them address their declining market share and revenue. The final output is an interactive business intelligence dashboard that empowers the management team to make data-driven decisions.

## Problem Statement

AtliQ Grands, a prominent player in the Indian hospitality industry for the last 20 years, is currently facing a significant business challenge. Due to strategic moves from competitors and ineffective internal decision-making, they are losing their market share and revenue in the luxury/business hotel category.

As a strategic response, the managing director wants to incorporate "Business and Data Intelligence" to regain their competitive edge. Since they lack an in-house data analytics team, they have hired a 3rd party service provider to analyze their historical data and provide actionable insights.

## Data Sources

The dataset is spread across five CSV files, forming a star schema that is ideal for BI analysis:

- **`dim_date`**: Contains date-related information, including week numbers and day types (Weekend/Weekday).
- **`dim_hotels`**: Provides details about each hotel property, such as property name, category (Luxury/Business), and city.
- **`dim_rooms`**: Includes information about room categories (RT1, RT2, etc.) and their corresponding class (Standard, Elite, etc.).
- **`fact_bookings`**: Contains transactional data for individual customer bookings, including booking platform, ratings given, booking status, and revenue generated.
- **`fact_aggregated_bookings`**: Provides pre-aggregated data on successful bookings and total room capacity for each property on a given day.

## Tools & Technologies

- **Data Transformation & ETL:** SQL / Power Query
- **Data Modeling & Visualization:** Microsoft Power BI / Tableau
- **Version Control:** Git & GitHub

## Methodology

1.  **Data Loading and Inspection:** Loaded the five CSV files into Power BI and performed an initial assessment of the data quality, structure, and relationships.
2.  **Data Cleaning and Transformation:**
    - Handled potential missing values and data type inconsistencies.
    - Created new calculated columns and measures using DAX (Data Analysis Expressions).
    - Established the business logic for key metrics. For example, `revenue_realized` is the full `revenue_generated` for bookings with a "Checked Out" or "No show" status. For "Cancelled" bookings, `revenue_realized` reflects the final amount that goes to the hotel.
3.  **Data Modeling:** Built a star schema data model in Power BI by creating relationships between the fact tables (`fact_bookings`, `fact_aggregated_bookings`) and dimension tables (`dim_date`, `dim_hotels`, `dim_rooms`).
4.  **Dashboard Development:**
    - Created calculated measures for all Key Performance Indicators (KPIs) as per the project requirements.
    - Designed an interactive dashboard based on the provided mock-up, focusing on user experience and clarity.

## Dashboard Overview

The final dashboard provides a comprehensive view of AtliQ Grands' performance across various dimensions.

### Key Performance Indicators (KPIs):
- **Total Revenue:** Total income generated from bookings.
- **Occupancy %:** Percentage of available rooms that were sold.
- **Average Daily Rate (ADR):** The average price of a room sold per day.
- **RevPAR (Revenue Per Available Room):** The most critical metric for hotel performance, blending Occupancy and ADR.
- **Realisation %:** The percentage of booked revenue that is actually collected after cancellations.

### Interactive Filters:
- Filter by **Date** (Month)
- Filter by **City**
- Filter by **Room Class** (Standard, Elite, etc.)
- Filter by **Property Name**

## Key Insights & Recommendations

The dashboard helps uncover several actionable insights, including:

1.  **City Performance Discrepancy:** While Mumbai generates the highest overall revenue, properties in Delhi have a higher average rating. **Recommendation:** AtliQ Grands could potentially implement a dynamic pricing strategy in Delhi to increase ADR without affecting customer satisfaction.

2.  **Booking Platform Effectiveness:** The "direct offline" and "direct online" booking platforms show the highest "Realisation %" (lowest cancellation rates). **Recommendation:** Invest in a loyalty program and direct booking campaigns to encourage customers to book through these channels, reducing dependency on third-party platforms that may have higher cancellation rates or commission fees.

3.  **Weekend vs. Weekday Occupancy:** Weekend occupancy is consistently higher than weekday occupancy across all cities. **Recommendation:** Launch targeted marketing campaigns for business travelers and corporate events to boost weekday occupancy. Offering special "work-from-hotel" packages could also be effective.

4.  **Presidential Suite Underperformance:** Presidential suites (RT4) have the lowest occupancy rate but the highest potential revenue per room. **Recommendation:** Create exclusive, high-value packages for presidential suites and market them to a niche, high-net-worth clientele to improve their occupancy.
