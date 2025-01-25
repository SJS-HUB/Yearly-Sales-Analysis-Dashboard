# Yearly Sales Analysis Dashboard

## Project Description
The **Yearly Sales Analysis Dashboard** is a Power BI project that provides a detailed analysis of the company's yearly sales performance. This dashboard includes various visualizations and metrics that offer insights into sales trends, profitability, and performance across different segments, states, cities, and shipping modes. The project also involved transforming and cleaning data using the Power Query Editor, including using "Use First Row as Headers" and removing null values. Additionally, several new measures were created for enhanced analysis by using Data Analysis Expressions(DAX) functioanl language.

## Features
- **Sales Performance Metrics**: Displays total sales and profit.
- **Yearly Sales Trend**: Line graph showing sales performance over the years.
- **Sales by Segment**: Pie chart visualizing sales distribution across different segments.
- **Sales by State and City**: Bar charts depicting sales performance in various states and cities.
- **Sales by Shipping Mode**: Breakdown of sales by different shipping modes.
- **Data Transformation and Cleaning**: Data cleaning and preparation using Power Query Editor.
- **New Measures**: Creation of new measures by using DAX for detailed analysis.

## Visualizations
- **Line Graph**: Yearly sales trends from 2014 to 2017.
- **Pie Chart**: Sales distribution by Consumer, Corporate, and Home Office segments.
- **Bar Charts**: Sales performance by state (Illinois, Michigan, Texas, Wisconsin) and by city (Chicago, Dallas, Detroit, Houston, Milwaukee).
- **TreeMap**: Highlighting key states with significant sales.
- **Detailed Analysis of West Region**: Includes total profit breakdown by year, segment, city, state, and ship mode.

## New Measures Created
- **Profit Central_tech_corQ1_Q2**: Profit calculation for Central Technology Corporate in Q1 and Q2.
-  DAX used:
-      Profit Central_tech_corQ1_Q2 = CALCULATE(
                                        SUM(Orders[Profit]),
                                        AND(
                                            Orders[Category] = "Technology",
                                            Orders[Segment] = "Corporate",
                                            Orders[Region] = "Central",
                                            Orders[Quarter] IN { "Q1", "Q2" }
                                        )
                                    )

- **Total Profit West_Q1**: Total profit for the West region in Q1.
- ** DAX used-
-         Total Profit West_Q1 = CALCULATE(
                                SUM(Orders[Profit]),
                                Orders[Region] = "West",
                                Orders[Quarter] = "Q1"
                            )

- **FurnitureSalesCentral**: Central region sales for Furniture.
   DAX used:
-        FurnitureSalesCentral = CALCULATE(
                                   SUM(Orders[Sales]),
                                   Orders[Category]= "Furniture",
                                   Orders[Region] = "Central"
                                   )
- **TechSales_E/W**: Technology sales for East and West regions.
- ** DAX used-
-     TechSales_E/W = CALCULATE(
                        SUM(Orders[Sales]),
                        AND(
                            Orders[Category] = "Technology",
                            OR(
                                Orders[Region] = "East",
                                Orders[Region] = "West"
                            )
                        )
                    )

- **TechSales E/W**: Sales for East and West office segments.
   -      TechSales_E/W = 
          CALCULATE(
          SUM(Orders[Sales]),
          AND(Orders[Category] = "Technology",
          OR(Orders[Region] = "East", Orders[Region]= "West")
          ))

     
## How to Use
1. **Clone the Repository**: Clone this repository to your local machine using `git clone <repository_url>`.
2. **Open in Power BI**: Open the Power BI file (`.pbix`) in Power BI Desktop.
3. **Explore the Dashboard**: Navigate through the various visualizations and metrics to gain insights into the company's sales performance.
4. **Customize**: Modify the visuals and data as per your requirements to tailor the analysis to your needs.

## Requirements
- **Power BI Desktop**: Ensure you have Power BI Desktop installed on your machine.

## Contact
For any questions or feedback, feel free to contact [Sharada S.] at [sharadasonaje25@gmail.com].
