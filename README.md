# 🏥 S&OP Forecast Analytics Dashboard

> **Power BI Business Intelligence Project**\
> **Internship Submission -- Smith & Nephew Healthcare**

------------------------------------------------------------------------

## 📌 Project Overview

This project presents an end-to-end **Sales & Operations Planning (S&OP)
Forecast Analytics Dashboard** developed using **Microsoft Power BI**.

The solution transforms raw forecast snapshot data into an interactive
executive reporting system that enables business users to compare
forecasts with actual performance, evaluate planning quality, identify
forecast bias, and support strategic decision-making.

Unlike a traditional dashboard, this project covers the complete BI
lifecycle:

-   Data Cleaning
-   Power Query ETL
-   Data Modeling
-   DAX Measure Development
-   Executive Dashboard Design
-   Business Insight Generation

------------------------------------------------------------------------

## 🎯 Business Problem

S&OP teams generate monthly forecast snapshots. Every planning cycle
produces a new forecast version. Business users need to compare the
latest forecast against previous planning cycles and actual sales.

Key questions answered:

-   How accurate are forecasts?
-   Which countries consistently over or under forecast?
-   How have forecasts evolved from Lag1 → Lag0 → Resultant?
-   Which regions contribute most revenue?
-   Where should planners improve forecasting?

------------------------------------------------------------------------

## 🧩 Dataset

The solution combines two source datasets.

### Actual Dataset

Contains historical business performance.

Main fields

-   Item
-   Country
-   Period
-   Revenue Qty
-   Non Revenue Qty
-   Capex Qty

### Forecast Dataset

Contains monthly planning snapshots.

Important fields

-   AsOfPeriod
-   Period
-   Revenue Forecast
-   Non Revenue Forecast
-   Capex Forecast
-   Segmentation Region
-   Segmentation Cluster
-   Country Group
-   Lifecycle

------------------------------------------------------------------------

## ⚙️ Power Query Workflow

### Step 1

Import Actual and Forecast data.

### Step 2

Clean missing values.

### Step 3

Remove Lifecycle because it is not used for business reporting.

### Step 4

Create Lag_Type

-   Resultant
-   Lag0
-   Lag1

### Step 5

Duplicate Forecast table

-   Forecast_Revenue
-   Forecast_NonRevenue
-   Forecast_Capex

### Step 6

Pivot Lag_Type into columns

Revenue

-   Lag0 Revenue
-   Lag1 Revenue
-   Resultant Revenue

Repeat for NonRevenue and Capex.

### Step 7

Merge all forecast tables.

### Step 8

Merge Forecast with Actual using

-   Country
-   Item
-   Period

Final table

**Fact_SIOP**

------------------------------------------------------------------------

## 📊 Dashboard Pages

### Executive Overview

```{=html}
<p align="center">
```
`<img src="Screenshots/Executive Overview.png" width="900"/>`{=html}
```{=html}
</p>
```
Shows executive KPIs:

-   Revenue Actual
-   Revenue Forecast
-   Forecast Accuracy
-   Revenue Variance
-   Forecast Bias

Visuals

-   Forecast vs Actual Trend
-   Revenue Variance Trend
-   Forecast Accuracy Trend
-   Forecast Bias Trend

Business Value

Allows senior management to monitor planning performance from one page.

------------------------------------------------------------------------

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
Provides revenue insights by

-   Country
-   Region
-   Cluster
-   Item
-   Planning Period

Highlights

-   Top revenue contributors
-   Regional performance
-   Revenue distribution
-   Actual vs Forecast

------------------------------------------------------------------------

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
KPIs

-   Forecast Accuracy
-   Forecast Bias
-   Forecast Error
-   Forecast Error %

Analysis

-   Country level errors
-   Cluster level errors
-   Lag0 vs Lag1 vs Resultant comparison

------------------------------------------------------------------------

### Forecast Snapshot & Non-Revenue Analysis

```{=html}
<p align="center">
```
`<img src="Screenshots/Forecast Snapshot Analysis.png" width="900"/>`{=html}
```{=html}
</p>
```
Includes

-   Capex Forecast
-   Non Revenue Forecast
-   Revenue Forecast by Region
-   Forecast Snapshot comparison

> Note: The provided dataset contains Capex Actual values as zero. The
> dashboard intentionally preserves the supplied business data.

------------------------------------------------------------------------

## 🧮 DAX Measures

-   Total Revenue Actual
-   Total Revenue Forecast
-   Revenue Variance
-   Revenue Variance %
-   Forecast Accuracy
-   Forecast Bias
-   Total NonRevenue Actual
-   Total NonRevenue Forecast
-   Total Capex Forecast

Each measure was created to represent business KPIs used by S&OP
planners.

------------------------------------------------------------------------

## 📁 Repository Structure

``` text
SIOP-Forecast-Analytics/
│
├── Dashboard/
│   └── SIOP_Dashboard.pbix
├── Dataset/
├── Documentation/
├── Screenshots/
├── README.md
└── LICENSE
```

------------------------------------------------------------------------

## 💡 Skills Demonstrated

-   Power BI
-   Power Query
-   DAX
-   ETL
-   Data Modeling
-   Dashboard Design
-   Business Intelligence
-   Data Storytelling
-   Forecast Analytics

------------------------------------------------------------------------

## 🚀 Future Enhancements

-   AI-assisted forecasting
-   Power BI Service deployment
-   Incremental Refresh
-   ML-based anomaly detection
-   Predictive demand planning

------------------------------------------------------------------------

## 🏁 Conclusion

This project demonstrates an end-to-end Business Intelligence workflow
aligned with Sales & Operations Planning. It transforms raw operational
data into meaningful executive insights and supports data-driven
decision-making for healthcare and manufacturing organizations.
