# B2B Pricing, Discount Leakage & Margin Protection Tracker

## Project Overview

The **B2B Pricing, Discount Leakage & Margin Protection Tracker** is an interactive business intelligence and pricing analytics project designed to evaluate sales profitability, identify excessive discounting, monitor pricing-policy compliance, and highlight deals requiring management intervention.

Built using **Excel Power Query and Google Sheets**, the project transforms raw sales, customer, and product pricing policy data into a structured analytical tracker with interactive filters, KPI scorecards, pricing exception monitoring, performance analysis, and prioritized intervention recommendations.

The tracker helps management understand where discounts are eroding margins, which product categories and deal types contribute most to estimated discount leakage, and where stronger pricing controls may be required.

**Live Tracker:** [Open the Google Sheets Tracker](https://docs.google.com/spreadsheets/d/19-tr-3t00YXe26n3LRaePFdfIc-hO2AIelZ7dlfN8gI/edit?usp=sharing)

## Objective

To develop an interactive pricing and profitability monitoring tracker that quantifies estimated discount leakage, evaluates margin performance against targets, identifies pricing-policy and approval exceptions, and prioritizes high-impact deals for management intervention through data-driven analysis.

## Business Problem

In B2B sales, increasing order volume does not necessarily translate into stronger profitability. Sales teams may offer discounts beyond permitted pricing limits, deals may fall below target margins, and approval exceptions may remain unresolved.

Without a consolidated monitoring system, management may struggle to identify the transactions responsible for margin erosion, determine which products and deal types create the greatest financial exposure, and prioritize corrective actions.

This project addresses that challenge by combining transaction-level pricing analysis, profitability metrics, policy compliance checks, and exception-based monitoring in a single interactive tracker.

## Tools & Technologies

- **Microsoft Excel:** Initial data preparation and workbook management.
- **Power Query:** Data cleaning, standardization, duplicate removal, data type correction, and preparation of structured datasets.
- **Google Sheets:** Lookup-based data integration, calculated columns, KPI calculations, interactive dropdown filters, dynamic tables, and dashboard development.
- **Spreadsheet Formulas:** Conditional logic, aggregation, lookup, filtering, sorting, and risk classification.

## Data Sources & Structure

The project uses three related datasets:

1. **Sales Transactions:** Transaction and order-line details, including order dates, customers, products, quantities, selling prices, discount information, order status, sales teams, and deal types.
2. **Customer Master:** Customer attributes such as customer identifiers, location, industry, segment, and customer onboarding information.
3. **Product Pricing Policy:** Product-level pricing information, including list prices, standard costs, target margins, and maximum permitted discount percentages.

The datasets are cleaned separately in Power Query and then transferred to Google Sheets for integration and analysis.

*The project is a portfolio analysis based on the prepared dataset. Its reported findings should be interpreted as illustrative analytical results, not verified results from an actual company's financial records.*

## Data Cleaning & Preparation

Data preparation was performed in Microsoft Excel using Power Query before the cleaned datasets were transferred to Google Sheets.

### 1. Customer Master Cleaning

- Detected and corrected column data types.
- Standardized text using Trim, Clean, and proper-case formatting where appropriate.
- Replaced missing customer names and city values with `Unknown`.
- Identified and removed duplicate customer records and duplicate customer IDs.
- Removed records with missing customer IDs.
- Reviewed category inconsistencies and standardized values.

### 2. Product Pricing Policy Cleaning

- Corrected data types for price and percentage columns.
- Converted monetary values to decimal numbers and standardized percentage fields.
- Cleaned and standardized text columns.
- Identified and removed duplicate product IDs.
- Removed records with missing product IDs.
- Replaced missing text-category values with `Unknown`.
- Standardized inconsistent category values.

### 3. Sales Transactions Cleaning

- Corrected data types, including conversion of order dates to date format and monetary fields to decimal numbers.
- Standardized text columns using Trim, Clean, and proper-case formatting where appropriate.
- Identified and removed duplicate transaction lines using the combination of order ID and order-line ID.
- Retained negative quantities associated with returns or cancellations for appropriate treatment during analysis.
- Preserved missing quantity and selling-price values for data-quality identification rather than silently replacing them with arbitrary values.
- Standardized missing text-category values using `Unknown`.

### 4. Data Integration & Quality Checks

The three cleaned datasets were transferred to Google Sheets. Customer and product pricing policy attributes were brought into the transaction-level dataset using lookup formulas.

Additional calculated columns and data-quality flags were created to identify issues such as:

- Missing or invalid quantity and pricing information.
- Missing or invalid product pricing policy values.
- Inconsistent price relationships.
- Transactions dated before the customer's recorded signup date.
- Missing approval information and other data-quality exceptions.

Order month and order year fields were also derived from the transaction date to support reporting and filtering.

## Tracker Features

### 1. Interactive Filters

The tracker includes dropdown filters for:

- Order Year
- Order Month
- Region
- Industry
- Customer Segment
- Sales Team
- Product Category
- Deal Type

These filters enable users to analyze pricing and profitability across different reporting periods, customer groups, regions, teams, products, and deal categories.

### 2. KPI Scorecard

The KPI section provides an overview of revenue, profitability, discounting, and pricing-policy compliance.

| KPI | Purpose |
|---|---|
| Total Revenue | Measures realized sales revenue from completed orders. |
| Gross Profit | Estimates gross profit using selling revenue and standard product costs. |
| Gross Margin % | Measures gross profit as a percentage of revenue. |
| Weighted Average Discount % | Measures the overall discount rate weighted by transaction list value. |
| Discount Leakage | Estimates the monetary value of discounts exceeding permitted pricing limits. |
| Policy Breach Deals | Counts completed order lines flagged for excessive discounts or margins below target. |
| Weighted Average Margin Gap % | Measures the difference between actual gross margin and revenue-weighted target margin. |

KPI calculations are designed to respond to the selected filters. Realized revenue and profitability metrics use completed orders, with invalid or incomplete financial records handled according to the data-quality rules.

### 3. Pricing Exception Monitor

This section summarizes pricing and approval exceptions to help management identify areas requiring investigation.

The monitored exceptions include:

- Excess Discount
- Unapproved Discount
- Below Target Margin Deals
- Negative Margin
- High-Risk Deals
- Approval Required Deals

The monitor includes deal counts and the percentage of deals associated with each exception. Approval-related exceptions are monitored separately from completed-order performance where appropriate because approval is a sales-governance process that may occur before a transaction is completed.

### 4. Product Category Pricing & Margin Monitor

This table compares product categories using:

- Revenue
- Profit Margin %
- Discount %
- Margin Gap %
- Discount Leakage
- Leakage Rate %

It helps identify categories with substantial financial exposure, elevated leakage rates, or weak margin performance.

### 5. Sales Team Pricing Performance Monitor

This table evaluates sales teams using revenue, profitability, discounting, margin gap, discount leakage, and leakage rate.

The analysis supports performance review and pricing-discipline coaching. Absolute leakage and leakage rate are considered separately because a team with high sales volume may generate greater leakage in monetary terms without necessarily having the highest leakage rate.

### 6. Deal-Type Pricing & Profitability Monitor

This table compares deal types using:

- Deal Count
- Revenue
- Profit Margin %
- Discount %
- Margin Gap %
- Discount Leakage
- Leakage Rate %

It helps identify deal structures that may require tighter pricing controls, revised discount guardrails, or additional approval oversight.

### 7. Priority Deals Requiring Intervention

The operational table highlights individual deals that warrant management attention.

It includes:

- Order ID
- Customer
- Salesperson
- Product
- Discount %
- Margin %
- Estimated Discount Leakage
- Risk Level
- Approval Status
- Recommended Action

Deals are filtered and prioritized using risk classification and financial exposure so that management can focus on the transactions requiring the most urgent review.

The risk rules classify deals as Critical, High, Medium, or Low based on margin performance and excess discounting. Recommended actions include stopping or renegotiating negative-margin deals, reviewing excessive discounts, and improving pricing where margins fall below targets.

## Calculation Methodology

The tracker uses row-level calculations to support consistent aggregation across its KPIs and analytical tables.

### Revenue

Revenue is calculated as:

`Revenue = Quantity × Selling Price per Unit`

Total revenue includes completed transactions with valid financial values.

### Gross Profit

Gross profit is estimated using:

`Gross Profit = Revenue − (Quantity × Standard Cost per Unit)`

This is an estimate based on standard costs, not verified actual transaction costs.

### Gross Margin %

`Gross Margin % = Gross Profit ÷ Revenue`

### Weighted Average Discount %

`Weighted Average Discount % = Total Discount Value ÷ Total List Value`

Where:

- Total Discount Value = Sum of Quantity × (List Price − Selling Price)
- Total List Value = Sum of Quantity × List Price

### Estimated Discount Leakage

For each eligible transaction line:

`Discount % = (List Price − Selling Price) ÷ List Price`

`Excess Discount = MAX(0, Discount % − Maximum Allowed Discount %)`

`Estimated Discount Leakage = Excess Discount × List Price × Quantity`

Total estimated discount leakage is the sum of eligible transaction-level leakage values for completed orders.

### Policy Breach Deals

A completed transaction line is flagged when:

- The actual discount exceeds the permitted maximum discount; **or**
- The actual gross margin falls below the target margin.

The count represents flagged transaction lines unless explicitly aggregated into distinct orders.

### Weighted Average Margin Gap

The tracker compares actual gross margin with the revenue-weighted target margin.

`Weighted Target Margin = SUM(Revenue × Target Margin %) ÷ Total Revenue`

`Margin Gap = Actual Gross Margin % − Weighted Target Margin %`

Under this convention, a negative margin gap indicates that actual gross margin is below the weighted target.

*Metric definitions and reporting filters should be applied consistently across the KPI scorecard and performance tables to ensure that the results reconcile.*

## Key Business Insights

The analysis documented in the tracker identifies several areas requiring attention:

1. **Estimated Discount Leakage:** The tracker reports approximately ₹43.23 crore in estimated discount leakage against total revenue of approximately ₹3,865.17 crore.
2. **Margin Performance:** The analysis reports that 18,723 completed transaction records are below target margin, representing approximately 35.90% of the completed deals under the tracker’s stated calculation.
3. **Strategic Deal Exposure:** Strategic deals show a reported leakage rate of 3.46%, substantially above the standard-deal rate, alongside weaker margin performance.
4. **Product Category Concentration:** Laptops account for approximately ₹19.16 crore of estimated leakage, or about 44% of total leakage. Laptops, Servers, and Networking together account for approximately 74%.
5. **Excessive Discounting:** Approximately 27.26% of completed deals are reported to exceed the standard maximum discount threshold.
6. **Concentrated Risk:** High- and Critical-Risk deals represent approximately 5.79% of transactions but account for approximately 49.81% of estimated leakage.
7. **Approval Governance:** The tracker identifies unapproved discount cases and pending approval exposure as separate areas for management review.
8. **Sales Team Differences:** SMB Sales has the highest reported absolute leakage, while East and North Sales have among the highest reported leakage rates.

These figures reflect the calculations documented in the portfolio tracker and should be interpreted using its data-quality rules, transaction eligibility criteria, and metric definitions.

## Business Recommendations

Based on the documented findings, the tracker supports the following management actions:

- Prioritize strategic deals for pricing review while considering their commercial importance.
- Focus margin-protection efforts on Laptops, Servers, and Networking, which contribute a large share of estimated leakage.
- Investigate high- and critical-risk transactions with substantial financial exposure first.
- Strengthen discount approval controls and separately investigate unauthorized discounts.
- Introduce approval-aging monitoring to prevent pending approvals from remaining unresolved.
- Consider product-category-specific discount guardrails instead of applying identical limits to every product.
- Use sales team performance analysis for coaching and pricing-discipline improvement rather than relying on absolute leakage alone.

## Limitations & Assumptions

- Discount leakage is an estimate of discount value above the configured pricing-policy threshold; it is not necessarily equivalent to realized profit loss.
- Gross profit and gross margin are estimated using standard product costs. Other operating expenses and actual transaction-level costs are not included, so net profit cannot be determined from this dataset.
- Approval and risk flags depend on the completeness and accuracy of the available approval, pricing, and transaction data.
- Returns, cancellations, incomplete records, and other exceptions require appropriate status and data-quality treatment before financial aggregation.
- Findings are based on the prepared portfolio dataset and should not be interpreted as verified financial results from a real business.
- The tracker supports management decision-making but does not replace detailed deal review or commercial judgment.

## Project Workflow

1. Import the raw customer, product pricing policy, and sales transaction datasets into Excel.
2. Clean and standardize each dataset using Power Query.
3. Load the cleaned datasets into separate worksheets.
4. Transfer the cleaned tables into Google Sheets.
5. Integrate customer and product pricing policy attributes into the transaction-level dataset.
6. Create data-quality flags, derived date fields, financial calculations, discount leakage calculations, and risk indicators.
7. Build interactive dropdown filters and KPI scorecards.
8. Develop pricing exception, product category, sales team, and deal-type monitoring tables.
9. Create a priority deals table with risk classification and recommended actions.
10. Interpret the results and translate the findings into actionable pricing and margin-protection recommendations.

## Conclusion

The B2B Pricing, Discount Leakage & Margin Protection Tracker demonstrates how spreadsheet-based data preparation, financial calculations, interactive reporting, and exception-based analysis can be combined into a practical pricing governance solution.

By connecting transaction-level pricing behavior with margin performance, estimated leakage, approval exceptions, and deal-level priorities, the project provides a structured approach to identifying financial exposure, improving pricing discipline, and supporting data-driven management intervention.
