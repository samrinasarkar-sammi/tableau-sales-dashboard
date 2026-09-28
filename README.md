# Sales Dashboard | Tableau

![Dashboard Overview]
<img width="1472" height="827" alt="image" src="https://github.com/user-attachments/assets/b8cbc89c-85bd-4c20-a357-d1aea9048a9f" />


**[🔗 View the interactive dashboard on Tableau Public](https://public.tableau.com/views/SalesDashboard_17905904496720/SalesDashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

## About This Project

This dashboard was built as a hands-on learning project by following the Tableau tutorial by [Data Tutorials](https://youtu.be/u5rjCZoVVvw). I rebuilt it step by step to learn dashboard design, calculated fields, LOD expressions, and interactivity in Tableau. All credit for the original design goes to the tutorial creator.

## Overview

An interactive sales dashboard comparing current year (2022) against previous year (2021) performance across sales, profit, and quantity, broken down by state, customer segment, and region/manager.

## Business Questions Answered

- How did sales, profit, and quantity change year over year?
- In which months did each KPI peak and dip?
- Which states are above or below the U.S. average for sales and profit?
- Which customer segments drive the most revenue, and when do they peak?
- How do regions and their managers compare?

## Key Insights

- **Sales:** $733K in 2022, up 20.36% year over year
- **Profit:** $82K, up 14.24%. Profit grew more slowly than sales, so the profit margin slipped slightly (about 11.2% of sales)
- **Quantity:** about 12K units, up 26.83%. Units grew fastest of the three KPIs
- **Segments:** Consumer is the largest segment (peak 50.23K), followed by Corporate (44.64K) and Home Office (29.71K). All three peak near year-end
- **Regions:** West leads with 250K in sales and East follows with 213K. Central (147K) and South (123K) trail
- **Geography:** Sales and profit are concentrated in a small number of states, visible on the tile map

## Dashboard Features

- **KPI cards** for Total Sales, Profit, and Quantity with current vs. previous year sparklines, max/min month markers, and YoY change indicators (▲/▼)
- **Tile-grid map** of U.S. states showing sales and profit together
- **Above/below average views** classifying states against the U.S. average for sales and profit
- **Monthly Sales by Segment** area charts (Consumer, Corporate, Home Office) with a measure selector for Sales, Profit, or Quantity
- **Sales by Location and Manager** bar chart with regional summary badges

## Technical Highlights

| Technique | Where it's used |
|---|---|
| Calculated fields | Current year vs. previous year measures for Sales, Profit, and Quantity |
| Dynamic year logic | `MAX(YEAR([Order Date]))` so the dashboard always compares the latest year to the year before |
| LOD expressions (`FIXED`) | State-level average vs. overall average for sales and profit |
| Table calculations | `WINDOW_MAX` / `WINDOW_MIN` to mark max and min months on the sparklines |
| Parameters | "Select Measure" switches the segment charts between Sales, Profit, and Quantity |
| Conditional logic | ▲/▼ YoY indicators and Above/Below Average color classification |
| Data blending / joins | Orders joined with People and a custom hex-map sheet for the tile map |
| Dashboard layout | 14 worksheets combined into a single dashboard |

## What I Learned

- Building KPI cards with sparklines and highlighted max/min points
- Creating a tile-grid map of U.S. states from a custom hex-map dataset
- Writing `FIXED` LOD expressions for averages that ignore the view's level of detail
- Using parameters with a `CASE` calculation to build a dynamic measure selector
- Calculating year-over-year change with reusable current/previous year fields
- Combining many worksheets into one polished, dark-themed dashboard

## Repository Structure

```
├── README.md
├── data/
│   ├── Sales_Data.xls          # Sample Superstore orders data
│   └── hexmap.xlsx             # State coordinates for the tile map
├── dashboard/
│   └── Sales_Dashboard.twbx     # Tableau workbook
└── images/
    └── Sales Dashboard.png
```

## Dataset

- **Sales_Data.xls**: Sample Superstore-style retail orders dataset (Orders and People tables)
- **hexmap.xlsx**: Grid coordinates used to draw each U.S. state as a tile

## How to Open

1. Clone or download this repository
2. Open `dashboard/Sales_Dashboard.twb` in Tableau Desktop
3. If Tableau asks for the data, point it to the files in the `data/` folder
4. Or skip all that and view it online: [Tableau Public](https://public.tableau.com/views/SalesDashboard_17905904496720/SalesDashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## Tools

- Tableau Desktop
- Microsoft Excel (data prep)

## Credits

- Tutorial and dashboard design: [Data Tutorials](https://youtu.be/u5rjCZoVVvw)
- Rebuilt by [Samrina Sarkar Sammi](https://github.com/YOUR_USERNAME) for learning purposes
