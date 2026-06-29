# S&OP Forecast Analytics Dashboard

> Internship Submission -- Smith & Nephew Healthcare

## Project Overview

This repository presents an end-to-end Sales & Operations Planning
(S&OP) Forecast Analytics Dashboard developed in Microsoft Power BI. The
project demonstrates complete business intelligence development,
beginning with raw data preprocessing in Power Query, data modeling, DAX
measure creation, and interactive dashboard design.

The dashboard helps business users compare forecasted values against
actual performance, evaluate planning quality, measure forecast
accuracy, detect forecast bias, analyze revenue variance, and monitor
business performance across countries, clusters, regions, items, and
planning periods.

## Business Objectives

-   Compare Forecast vs Actual performance.
-   Evaluate Forecast Accuracy.
-   Measure Revenue Variance.
-   Detect Forecast Bias.
-   Analyze Country, Region and Cluster performance.
-   Compare Lag0, Lag1 and Resultant forecasts.
-   Build an executive dashboard for decision makers.

## Data Preprocessing

### Source Tables

-   Actual
-   Forecast

### Power Query Workflow

1.  Duplicated Forecast query into Revenue, NonRevenue and Capex.
2.  Filtered each business category.
3.  Removed unnecessary columns.
4.  Pivoted Lag_Type into Lag0, Lag1 and Resultant.
5.  Renamed columns.
6.  Merged the three forecast queries using Item, Country and Period.
7.  Created Forecast_Master table.

## DAX Measures

-   Total Revenue Actual
-   Total Revenue Forecast
-   Revenue Variance
-   Revenue Variance %
-   Forecast Accuracy
-   Forecast Bias
-   Total Capex Actual
-   Total Capex Forecast
-   Total NonRevenue Actual
-   Total NonRevenue Forecast

## Dashboard Pages

### Executive Overview

```{=html}
<p align="center">
```
`<img src="Screenshots/Executive Overview.png" width="900"/>`{=html}
```{=html}
</p>
```
Contains executive KPIs, slicers, trend analysis, forecast accuracy and
revenue variance.

### Revenue Analysis

```{=html}
<p align="center">
```
`<img src="Screenshots/Revenue Analysis_1.png" width="900"/>`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="Screenshots/Revenue Analysis_2.png" width="900"/>`{=html}
```{=html}
</p>
```
Analyzes revenue across countries, clusters, items, regions and planning
periods.

### Forecast Performance

```{=html}
<p align="center">
```
`<img src="Screenshots/Forecast Performance_1.png" width="900"/>`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="Screenshots/Forecast Performance_2.png" width="900"/>`{=html}
```{=html}
</p>
```
Evaluates forecast accuracy, forecast bias, forecast error, and
Lag0/Lag1/Resultant comparisons.

### Capex & Non-Revenue Analysis

```{=html}
<p align="center">
```
`<img src="Screenshots/Capex & Non-Revenue Analysis_1.png" width="900"/>`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<img src="Screenshots/Capex & Non-Revenue Analysis_2.png" width="900"/>`{=html}
```{=html}
</p>
```
Analyzes Capex and Non-Revenue forecasts. The provided dataset contains
zero values for Capex Actuals, so the dashboard reflects the source data
faithfully.

## Repository Structure

``` text
SIOP-Forecast-Analytics/
├── Dashboard/
├── Dataset/
├── Documentation/
├── Screenshots/
└── README.md
```

## Installation

1.  Clone the repository.
2.  Open the PBIX file using Power BI Desktop.
3.  Refresh the dataset.
4.  Explore all dashboard pages using slicers.

## Future Enhancements

-   Machine Learning forecasting
-   Automated refresh
-   Power BI Service deployment
-   Row Level Security
-   Predictive analytics

## Conclusion

This project demonstrates a complete Power BI business intelligence
solution from raw data preparation through executive dashboard
reporting. It showcases Power Query transformations, DAX modeling,
interactive visualization, and business insight generation relevant to
Sales & Operations Planning in healthcare and manufacturing
organizations.
