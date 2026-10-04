# econom-project
# Supply Chain Optimization in the Apparel Industry

## Overview

This project analyzes supply chain strategies for a fashion retailer operating Limited Edition Collections (LECs).

The main objective is to determine how the company can improve profitability and reduce demand uncertainty by choosing between three operational models:

1. Outsourcing
2. Near-sourcing
3. Supply Chain Flexibility

The analysis combines historical sales data, regression forecasting, Monte Carlo simulation, scenario analysis, and Excel-based optimization to evaluate each strategy and identify the most profitable approach.

---

## Business Problem

The company sells Limited Edition Collections that are available only for a short period of time.

The main challenge is demand uncertainty.

If the company orders too many shirts, it is left with unsold inventory. If it orders too few, it loses potential sales.

Production in Ukraine costs **$65 per shirt**, but requires the company to make inventory decisions before observing actual demand.

A local production facility provides additional flexibility and faster delivery, but at a higher cost of **$95 per shirt**.

The project evaluates whether the additional flexibility can compensate for the higher production cost.

---

## Dataset

The dataset contains historical daily sales for Limited Edition Collections.

Main variables include:

- Date
- LEC ID
- Units Sold
- Collection Length
- Holiday Indicator
- Weekly Demand
- Total Demand

Historical data from previous LECs was used to estimate future demand and evaluate alternative supply chain strategies.

---

## Tools & Methods

### Tools

- Microsoft Excel
- Regression Analysis
- Monte Carlo Simulation
- Data Tables
- Scenario Analysis
- Data Visualization

### Analytical Methods

- Exploratory Data Analysis
- Demand Forecasting
- Regression Modeling
- Profit Optimization
- Monte Carlo Simulation
- Backtesting
- Supply Chain Scenario Comparison

---

## 1. Outsourcing Model

The first strategy assumes that all shirts are produced in Ukraine.

Because production and delivery require approximately three weeks, the company must determine the entire order quantity before the collection begins.

### Demand Forecast

Historical sales data was analyzed to identify factors affecting total demand.

The regression model uses:

- normalized logarithm of collection length
- holiday indicator

The model achieved an **R² of approximately 0.88**, indicating that it explains a substantial proportion of historical demand variation.

For the upcoming 21-day LEC, the regression model predicted demand of approximately:

**290 shirts**

Because the forecast contains uncertainty, Monte Carlo simulation was used to determine the order quantity that maximizes expected profit.

### Monte Carlo Optimization

1,000 demand scenarios were generated using the estimated demand distribution.

For each possible order quantity, profit was calculated as:

Profit = Sales Revenue - Production Cost

The simulation evaluated multiple order quantities and selected the quantity with the highest expected profit.

### Result

Predicted demand:

**≈ 290 units**

Optimal outsourcing order:

**≈ 292 units**

---

## 2. Near-Sourcing Model

The second strategy combines an initial order from Ukraine with additional production from a local facility.

The local facility can produce:

**12 shirts per day**

with next-day delivery after the first week of the collection.

Although local production is more expensive, it allows the company to react to actual demand instead of committing entirely before the collection begins.

### Strategy

The model consists of:

1. Initial order from Ukraine
2. Observation of actual demand
3. Calculation of additional demand
4. Local production when demand exceeds the initial inventory

Local production is limited by available production capacity.

### Optimization

Monte Carlo simulation was used again to evaluate different initial order quantities.

For the upcoming LEC, the simulation identified an initial Ukraine order of approximately:

**240 units**

The remaining demand can then be covered through local production when necessary.

---

## 3. Historical Backtesting

To evaluate whether near-sourcing provides a consistent advantage, both strategies were tested using historical LEC data.

For each collection, the analysis calculated:

- actual demand
- forecasted demand
- optimal initial quantity
- local production capacity
- additional demand
- sales
- realized profit

The models were compared across LECs 11–23.

### Results

| Strategy | Historical Profit |
|----------|------------------:|
| Outsourcing | $304,380 |
| Near-Sourcing | $369,810 |
| Improvement | **+$65,430** |

The analysis shows that near-sourcing significantly improves historical profitability by reducing the cost of overstocking while allowing the company to respond to unexpectedly high demand.

---

## 4. Supply Chain Flexibility Model

The third strategy introduces a two-stage ordering process.

Instead of committing to the entire inventory before launch, the company can:

1. Place an initial order before the collection starts.
2. Observe first-week demand.
3. Forecast remaining demand.
4. Place an additional order from Ukraine.
5. Receive the reorder approximately one week later.

This creates a **test-and-respond strategy**.

The key difference is that the second inventory decision incorporates real market information.

---

## Forecasting Remaining Demand

The flexibility model requires a different forecasting approach.

Instead of predicting only total LEC demand, the model considers:

- Week 1 demand
- Remaining demand after Week 1

Historical data from LECs 11–23 was used to estimate the relationship between early sales and remaining demand.

Monte Carlo simulation was then used to determine the optimal reorder quantity.

For each candidate quantity:

1. Remaining demand was simulated.
2. Sales and leftover inventory were calculated.
3. Profit was calculated.
4. Expected profit was estimated across simulations.
5. The quantity producing the highest expected profit was selected.

---

## Model Comparison

Historical backtesting was used to compare the three strategies.

| Business Model | Total Profit |
|----------------|------------:|
| Outsourcing | $309,255 |
| Flexibility | $314,135 |
| Near-Sourcing | **$375,950** |

The flexibility strategy performs slightly better than traditional outsourcing.

However, it does not outperform near-sourcing.

The main limitation is the high variance of the remaining-demand forecast, which reduces the effectiveness of the second-stage ordering decision.

---

## Key Insights

The analysis demonstrates several important supply chain principles:

- Forecast accuracy directly affects inventory profitability.
- Large initial orders increase the risk of excess inventory.
- Operational flexibility can reduce forecast risk.
- Observing real demand before making additional inventory decisions creates economic value.
- Higher unit production costs can still be profitable when they reduce inventory risk.
- Monte Carlo simulation provides a practical method for optimizing decisions under uncertainty.

---

## Final Recommendation

Based on the analysis, **near-sourcing is the preferred operational strategy**.

Although local production costs more per unit, the ability to react quickly to actual demand reduces inventory risk and improves overall profitability.

The flexibility model also creates value compared with rigid outsourcing, but its performance is limited by uncertainty in the remaining-demand forecast.
