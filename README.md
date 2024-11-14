# NBA Data Insights - Analysis by DataHooper

Welcome to the **NBA Data Insights** repository! Here, I share in-depth analyses of NBA team and player performance data across recent seasons, exploring trends, comparisons, and statistical highlights. This project is part of my work as **DataHooper**, where I bring you data-driven insights into the world of NBA basketball.

## Project Overview

This repository features SQL queries and analyses covering a wide range of NBA statistics. The main focus is on year-over-year comparisons to uncover insights into changes in team performance, player efficiency, shooting trends, and other key metrics from season to season.

## Key Insights and Features

- **Field Goal and Shooting Efficiency**: Compare team effective field goal percentages (eFG%), three-point shooting, free throw accuracy, and other shooting metrics.
- **Player Performance**: Track standout player improvements and declines, scoring efficiency, rebounding, assists, and other performance indicators.
- **Team Rankings**: Rank teams based on changes in specific metrics, making it easy to spot those with the most significant improvements or declines.
- **Data Visualizations**: (Coming soon) Visual insights to help users quickly grasp season-to-season shifts in performance and identify trends.

## How to Use

1. **SQL Queries**: Use the SQL queries provided in this repository to pull various NBA metrics from your datasets, including:
   - Field goal percentages, effective field goal percentages, and shooting splits.
   - Advanced metrics like true shooting percentage (TS%), player efficiency ratings (PER), and more.
   - Team and player year-over-year statistical comparisons.

2. **Insights**: Analyze the output to generate insights and identify trends. These insights are published on my **DataHooper** Twitter to keep fans and analysts up-to-date with the latest NBA stats.

## Example SQL Query

Here’s an example query for comparing team FG% between two seasons:

```sql
SELECT 
    p1.Tm,
    ROUND(AVG(p1.`FG%`), 2) AS AVG_FG_23_24,
    ROUND(AVG(p2.`FG%`), 2) AS AVG_FG_22_23,
    ROUND(AVG(p1.`FG%`) - AVG(p2.`FG%`), 2) AS FG_percent_change
FROM 
    NBA_Regular_Stats_2023_2024.NBA_Regular_2324 p1
JOIN 
    NBA_Regular_Stats_22_23.NBA_Regular_2223 p2 
ON 
    p1.Tm = p2.Tm
GROUP BY 
    p1.Tm
ORDER BY 
    FG_percent_change DESC;# NBA Data Insights - Analysis by DataHooper
