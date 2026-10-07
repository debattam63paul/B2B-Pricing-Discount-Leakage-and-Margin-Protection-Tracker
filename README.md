# B2B Pricing, Discount Leakage & Margin Protection Tracker

## 📌 Project Overview

The **B2B Pricing, Discount Leakage & Margin Protection Tracker** is an interactive sales-pricing analytics solution designed to identify where B2B transactions are losing profitability due to excessive discounts, pricing-policy exceptions, and below-target margins.

Instead of only reporting sales revenue, the project helps management answer:

> **Where are discounts eroding margins, which deals require intervention, and where is pricing discipline breaking down?**

---

## 🎯 Objective

The primary objective is to **identify and monitor transactions that are eroding profitability through excessive discounts, pricing-policy violations, and below-target margins, while estimating potential discount leakage and prioritizing high-risk deals, customers, products, sales teams, and business segments for management intervention and better pricing decisions.**

---

## 🏢 Why This Matters in Business

In B2B sales, higher revenue does not always mean higher profitability. Sales teams may use discounts to win customers or increase order volume, but excessive discounting can significantly reduce margins.

This tracker helps organizations:

* Monitor pricing discipline
* Identify excessive discounts
* Estimate potential discount leakage
* Detect below-target-margin deals
* Monitor approval exceptions
* Prioritize high-risk transactions
* Support margin-protection decisions

---

# 🗂️ Dataset

The project combines three business datasets:

### Sales Transactions

Transaction-level sales information including:

* Order ID / Order Line ID
* Order Date
* Customer
* Product
* Quantity
* List Price
* Selling Price
* Sales Team
* Deal Type
* Order Status
* Approval Status

### Customer Master

Contains:

* Customer
* Region
* Industry
* Customer Segment
* Sales Channel
* Payment Terms

### Product Pricing Policy

Contains:

* Product
* Product Category
* Brand
* Standard Cost
* List Price
* Target Margin %
* Maximum Allowed Discount %

---

# 🔄 Project Workflow

```text
Raw Data
   ↓
Power Query Cleaning
   ↓
Data Quality Validation
   ↓
Customer + Product Enrichment
   ↓
Derived Pricing & Margin Metrics
   ↓
Interactive Filters
   ↓
KPI Calculation
   ↓
Exception Monitoring
   ↓
Risk Classification
   ↓
Priority & Recommended Action
   ↓
Business Insights
```

---

# 🧹 Data Cleaning

Data was cleaned using **Excel Power Query**.

Key activities included:

* Data-type correction
* Trim/Clean/Capitalize text
* Duplicate detection and removal
* Blank-value handling
* Category standardization
* Customer ID validation
* Product ID validation
* Sales transaction validation
* Preservation of negative quantities for returns/cancellations

Transactions with missing Quantity or Selling Price were retained for data-quality traceability but excluded from financial/pricing KPI calculations.

---

## Google Sheet Link for Tracker
https://docs.google.com/spreadsheets/d/162MVSzO384lFs7TLjuEcCn6zJpo8xv9RlO1brcKL7Ow/edit?gid=354825797#gid=354825797

---

# 📊 Interactive Analysis

The tracker includes filters for:

* Order Year
* Order Month
* Region
* Industry
* Customer Segment
* Sales Team
* Product Category
* Deal Type

These filters allow users to analyze pricing and profitability across different business dimensions.

---

# 📈 Key KPIs

The tracker monitors:

| KPI                                | Purpose                                            |
| ---------------------------------- | -------------------------------------------------- |
| **Total Revenue**                  | Measures completed sales value                     |
| **Estimated Gross Profit**         | Measures transaction-level profitability           |
| **Estimated Gross Margin %**       | Measures profitability relative to revenue         |
| **Weighted Avg. Discount %**       | Measures actual discounting behavior               |
| **Estimated Discount Leakage**     | Estimates potential value given away beyond policy |
| **Pricing Policy Exception Deals** | Identifies deals violating discount/margin rules   |
| **Weighted Avg. Margin Gap**       | Measures performance against target margin         |

---

# 🚨 Exception & Risk Monitoring

The tracker identifies:

* Excess Discount
* Unapproved Discount
* Below Target Margin
* Negative Margin
* High-Risk Deals
* Approval Pending

### Risk Levels

| Risk            | Condition                                     |
| --------------- | --------------------------------------------- |
| 🔴 **Critical** | Negative Gross Margin                         |
| 🟠 **High**     | Margin Gap ≤ -5 pp OR Excess Discount ≥ 10 pp |
| 🟡 **Medium**   | Negative Margin Gap OR Excess Discount        |
| 🟢 **Low**      | No major pricing exception                    |

---

# 🎯 Priority Intervention

The **Priority Deals Requiring Intervention** table converts analysis into action.

It includes:

* Order ID
* Order Line ID
* Customer
* Salesperson
* Product
* Discount %
* Margin %
* Leakage ₹
* Risk
* Approval Status
* Priority
* Recommended Action

### Recommended Actions

* **Stop / Renegotiate**
* **Review Discount**
* **Improve Pricing**
* **No Action**

This makes the tracker operational rather than simply descriptive.

---

# 🔍 Key Business Insights

The analysis identified several important patterns:

### 1. Significant Pricing Leakage

Approximately **₹122.98 Cr** of estimated discount leakage was identified, representing around **6.06% of revenue**.

### 2. Strategic Deals Require Attention

Strategic Deals show approximately **5.80% margin** and **9.34% estimated leakage/revenue**, with around **96% classified as High/Critical risk**.

### 3. Volume Deals Also Show Pricing Pressure

Volume Deals show approximately **7.73% margin** and **7.11% estimated leakage/revenue**.

### 4. Inside Sales Provides a Benchmark

Inside Sales achieves approximately **10.88% margin** with **4.23% leakage/revenue**, providing a useful benchmark for other sales teams.

### 5. Key Accounts Need Pricing Governance

Key Accounts show approximately **7.80% margin** and **7.29% leakage/revenue**, indicating the need for stronger account-level pricing controls.

### 6. High-Revenue Categories Need Protection

Laptops and Servers together contribute approximately **₹1,057 Cr revenue**, making them important areas for margin protection.

### 7. Approval Backlog

Approximately **4,148 transactions are approval-pending**, creating an opportunity to improve pricing-governance efficiency.

---

# 💡 Business Recommendations

Based on the analysis:

1. **Strengthen discount approval controls** for deals exceeding pricing thresholds.
2. **Apply stricter pricing controls** to Strategic and Volume Deals.
3. **Prioritize Critical/High-risk deals** based on estimated ₹ leakage and revenue exposure.
4. **Protect Key Accounts and high-revenue products** through account/SKU-level pricing reviews.
5. **Reduce approval backlog** using ownership, aging monitoring, and escalation.
6. **Study stronger Inside Sales practices** and replicate effective pricing behavior across teams.
7. **Introduce minimum-margin governance** for transactions falling below acceptable profitability levels.

---

# 🛠️ Tools & Technologies

* **Microsoft Excel**
* **Power Query**
* **Google Sheets**
* Excel/Sheets formulas
* Data validation & dynamic filters
* Lookup-based data enrichment
* KPI & exception analysis

---

# 📌 Business Value

This project transforms:

**Raw Sales Data → Clean Data → Pricing Analysis → KPI → Exception → Risk → Priority → Action**

The key value is that it does not stop at:

> **"How much did we sell?"**

It answers:

> **"Where are we losing margin, which deals are risky, and what should management do about them?"**

---

# 📁 Repository Structure

```text
B2B-Pricing-Discount-Leakage-Margin-Protection-Tracker/
│
├── README.md
├── B2B_Pricing_Discount_Margin_Protection_Tracker.xlsx
│
├── Data/
│   ├── Sales_Transactions_Cleaned.xlsx
│   ├── Customer_Master_Cleaned.xlsx
│   └── Product_Pricing_Policy_Cleaned.xlsx
│
└── Screenshots/
```

---

## 👤 Author

**Debattam Paul**

**Focus:** Sales Analytics | MIS | Pricing Analytics | Business Analysis | Margin Protection
