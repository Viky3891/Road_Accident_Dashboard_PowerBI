# Road_Accident_Dashboard_PowerBI
Interactive Power BI dashboard analysing UK road accident casualties for 2021 vs 2022 by severity, vehicle type, road type, area, light condition and location, with YTD and YoY KPIs built using DAX.
# Road Accident Dashboard – United Kingdom

An interactive, single-page Power BI dashboard that tracks road accident casualties, accidents and severity across the United Kingdom, comparing the **Current Year (CY, 2022)** with the **Previous Year (PY, 2021)**.

## Dashboard Preview

   ![Road Accident Dashboard](Road%20Accident%20Dashboard.png)

## Business Problem

The client needed one report page to:
- Assess whether casualties and accidents are reducing compared with last year
- Compare casualties by accident severity (Fatal, Serious, Slight)
- Identify which vehicle types and road types are involved in the most casualties
- Examine casualties by area (Rural/Urban), light condition (Day/Night) and location

## Key KPIs (CY vs PY)

| KPI | CY | PY | YoY |
|---|---|---|---|
| Total Casualties | 195.7K | 222.1K | -11.9% |
| Total Accidents | 144.4K | 163.6K | -11.7% |
| Fatal Casualties | 2.9K | 4.3K | -33.3% |
| Serious Casualties | 27.0K | 32.3K | -16.2% |
| Slight Casualties | 165.8K | 185.6K | -10.6% |

## Visuals

- **KPI Cards**: CY value, PY value and YoY % for casualties, accidents and severity
- **Casualties by Vehicle Type**: Agriculture, Bike, Bus, Car, Van and Others
- **CY vs PY Monthly Trend**: month-wise comparison of casualties for both years
- **Casualties by Road Type**: ranked bar chart (Single carriageway, Dual carriageway, Roundabout, One way street, Slip road)
- **Casualties by Rural/Urban**: donut chart with contribution %
- **Casualties by Light Condition**: donut chart with Day/Night split
- **Casualties by Location**: map showing casualty spread across the UK

## Filters

Weather Conditions, plus a **Clear all slicers** button.

## Data Model

- Accident fact table with casualties, severity, vehicle type, road type, area, light condition, weather and location
- `Calendar`: continuous date table used for time intelligence

Relationships are one-to-many (Calendar to fact table).

## Key Learnings and Approach

- CY calculated with `TOTALYTD` and PY with `PREVIOUSYEAR(DATESYTD())` for YTD comparison
- YoY growth calculated as (CY - PY) / PY using `DIVIDE`
- Monthly trend uses separate `CY Monthly` and `PY Monthly` measures with `CALCULATE`, because `TOTALYTD` gives a running total instead of month-wise values
- Month names sorted by month number, so the trend follows calendar order
- Dashboard background designed in PowerPoint and imported as images

## Tools Used

Power BI Desktop, DAX, Power Query, Data Modeling, PowerPoint (background design)

## Repository Structure

```
├── README.md
├── Road_Accident_Dashboard.pbix
├── Road-Accident-Dashboard-Business-Requirements.pdf
└── Road Accident Dashboard.png
```

## How to Use

1. Download `Road_Accident_Dashboard.pbix`
2. Open it in Power BI Desktop
3. Use the Weather Conditions slicer to explore the data

## Author

**Your Name**
🔗 [LinkedIn](https://www.linkedin.com/in/your-profile)

Feedback and suggestions are welcome!
