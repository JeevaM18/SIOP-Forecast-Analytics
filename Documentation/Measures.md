# Measures Documentation

# S&OP Forecast Analytics Dashboard

This document describes all DAX measures used in the Power BI dashboard. Each measure has been designed to support Sales & Operations Planning (S&OP) reporting and provide meaningful business insights for decision makers.

---

# Table of Contents

* Revenue Measures
* Forecast Measures
* Variance Measures
* Forecast Accuracy Measures
* Forecast Bias Measures
* Non-Revenue Measures
* Capex Measures
* Supporting Measures

---

# Revenue Measures

---

## Total Revenue Actual

### Purpose

Calculates the total actual revenue quantity recorded in the business.

This represents the real business performance and serves as the baseline for comparing forecast quality.

### DAX

```DAX
Total Revenue Actual =
SUM(Fact_SIOP[Actuals___Revenue_Qty])
```

### Business Meaning

Shows the total revenue generated during the selected planning period.

### Used In

* Executive Dashboard KPI
* Revenue Analysis
* Forecast Comparison
* Country Analysis

---

## Total Revenue Forecast

### Purpose

Calculates the latest forecasted revenue using the Resultant Forecast.

### DAX

```DAX
Total Revenue Forecast =
SUM(Fact_SIOP[Resultant Revenue])
```

### Business Meaning

Represents the latest planning team's revenue expectation.

### Used In

* Executive Dashboard
* Revenue Analysis
* Forecast Comparison

---

# Revenue Variance Measures

---

## Revenue Variance

### Purpose

Measures the difference between Actual Revenue and Forecast Revenue.

### DAX

```DAX
Revenue Variance =
[Total Revenue Actual] -
[Total Revenue Forecast]
```

### Business Meaning

Positive Value

* Actual Revenue exceeded Forecast

Negative Value

* Forecast exceeded Actual Revenue

### Used In

* KPI Cards
* Revenue Variance Trend
* Forecast Performance

---

## Revenue Variance %

### Purpose

Calculates percentage deviation from forecast.

### DAX

```DAX
Revenue Variance % =
DIVIDE(
[Revenue Variance],
[Total Revenue Forecast],
0
)
```

### Business Meaning

Shows how far actual performance deviated from planning.

### Used In

* Executive Dashboard
* Variance Analysis

---

# Forecast Accuracy Measures

---

## Forecast Accuracy

### Purpose

Measures how close forecasted values are to actual values.

### DAX

```DAX
Forecast Accuracy =
1 -
DIVIDE(
ABS([Revenue Variance]),
[Total Revenue Actual],
0
)
```

### Formula

Forecast Accuracy

=

1 −

|Forecast − Actual|

/

Actual

### Interpretation

100%

Perfect Forecast

95%

Very Good Forecast

80%

Acceptable Forecast

Below 70%

Needs Improvement

### Used In

* KPI Card
* Forecast Accuracy Trend
* Forecast Performance Dashboard

---

# Forecast Bias Measures

---

## Forecast Bias

### Purpose

Identifies systematic over-forecasting or under-forecasting.

### DAX

```DAX
Forecast Bias =
DIVIDE(
[Revenue Variance],
[Total Revenue Actual],
0
)
```

### Interpretation

Positive

Under Forecast

Negative

Over Forecast

Near Zero

Balanced Forecast

### Used In

* KPI Card
* Forecast Bias Trend
* Country Analysis

---

# Forecast Error Measures

---

## Forecast Error

### Purpose

Calculates the absolute difference between forecasted and actual revenue.

### DAX

```DAX
Forecast Error =
ABS(
[Total Revenue Actual] -
[Total Revenue Forecast]
)
```

### Business Meaning

Represents total forecasting error without considering direction.

### Used In

Forecast Performance Dashboard

---

## Forecast Error %

### Purpose

Shows forecasting error as a percentage.

### DAX

```DAX
Forecast Error % =
DIVIDE(
ABS(
[Total Revenue Actual] -
[Total Revenue Forecast]
),
[Total Revenue Actual],
0
)
```

### Business Meaning

Provides normalized forecast error allowing fair comparison across countries.

---

# Non-Revenue Measures

---

## Total Non-Revenue Actual

### Purpose

Calculates actual Non-Revenue quantity.

### DAX

```DAX
Total NonRevenue Actual =
SUM(Fact_SIOP[Actuals___NonRevenue_Qty])
```

### Used In

* KPI Card
* Non-Revenue Dashboard

---

## Total Non-Revenue Forecast

### Purpose

Calculates Resultant Non-Revenue Forecast.

### DAX

```DAX
Total NonRevenue Forecast =
SUM(Fact_SIOP[Resultant NonRevenue])
```

### Used In

* KPI Card
* Non-Revenue Trend

---

# Capex Measures

---

## Total Capex Actual

### Purpose

Calculates actual Capex quantity.

### DAX

```DAX
Total Capex Actual =
SUM(Fact_SIOP[Actuals___Capex_Qty])
```

### Note

The supplied dataset contains zero values for Actual Capex.

Therefore the dashboard correctly reports zero for this KPI.

---

## Total Capex Forecast

### Purpose

Calculates forecasted Capex.

### DAX

```DAX
Total Capex Forecast =
SUM(Fact_SIOP[Resultant Capex])
```

### Used In

* KPI Card
* Capex Trend
* Forecast Analysis

---

# Forecast Snapshot Measures

The transformed dataset contains three forecast versions.

---

## Lag1 Revenue

Oldest Forecast Snapshot.

Used for historical comparison.

---

## Lag0 Revenue

Previous Forecast Snapshot.

Represents the forecast created immediately before the latest version.

---

## Resultant Revenue

Latest Forecast Snapshot.

Represents the final planning version used for reporting.

---

# Business Importance of Lag Comparison

Comparing

* Lag1
* Lag0
* Resultant

helps planners understand how demand forecasts evolved over time.

Large changes between snapshots indicate uncertainty in demand planning.

Small changes indicate stable forecasting.

---

# Dashboard Usage

| Measure                   | Dashboard            |
| ------------------------- | -------------------- |
| Total Revenue Actual      | Executive Overview   |
| Total Revenue Forecast    | Executive Overview   |
| Revenue Variance          | Executive Overview   |
| Revenue Variance %        | Executive Overview   |
| Forecast Accuracy         | Forecast Performance |
| Forecast Bias             | Forecast Performance |
| Forecast Error            | Forecast Performance |
| Forecast Error %          | Forecast Performance |
| Total NonRevenue Actual   | Snapshot Analysis    |
| Total NonRevenue Forecast | Snapshot Analysis    |
| Total Capex Forecast      | Snapshot Analysis    |

---

# Summary

The DAX measures developed in this project transform raw transactional data into meaningful business KPIs that support executive decision-making within the Sales & Operations Planning (S&OP) process.

These measures enable planners to evaluate forecast quality, monitor planning accuracy, detect forecast bias, compare historical forecast snapshots, and identify opportunities for improving forecasting performance across countries, regions, and business segments.

Collectively, these measures form the analytical foundation of the dashboard and provide actionable insights for data-driven planning and operational excellence.
