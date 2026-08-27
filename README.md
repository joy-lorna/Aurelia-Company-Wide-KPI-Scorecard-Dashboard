# Company-Wide KPI Scorecard Dashboard

## Aurelia Financial Services S.A. | Power BI Portfolio Project

### Business Intelligence Analyst Portfolio Project

---

## Project Overview

This project demonstrates the design and implementation of a management reporting dashboard for a fictional Luxembourg financial-services organisation. The solution combines dimensional modelling, DAX calculations, KPI governance, drill-through reporting, and interactive dashboard design to support executive decision-making across Revenue, Cost, Customer, and Operations functions.

The project was built to demonstrate practical Business Intelligence skills commonly expected in Power BI analyst roles, including:

- Star schema data modelling
- Power Query transformations
- DAX measure development
- Time intelligence calculations
- KPI framework design
- RAG (Red-Amber-Green) performance monitoring
- Drill-through reporting
- Dashboard publishing and documentation

---
## Live Dashboard

### Power BI Dashboard

🔗 **View the published dashboard**

[Open Aurelia Financial Services KPI Dashboard](https://frelotraders-my.sharepoint.com/:u:/g/personal/joylorna_frelotraders_onmicrosoft_com/IQB9T_JnjoypT6mWzpxhq8WhAQPOC_1bBCVloizjIBn8Oso?e=Kw6O7X)

The dashboard contains:

- Executive Summary
- Revenue Drill-Through Analysis
- Operations Deep Dive

Built using Power BI Desktop, Power Query, DAX, and a dimensional star-schema model.
---
# Dashboard Preview
## Executive Summary

The Executive Summary page provides a company-wide management scorecard across Revenue, Cost, Customer, and Operations performance pillars.

Key features include:

- Revenue KPI monitoring
- Cost management controls
- Customer growth and retention monitoring
- Operational service-quality tracking
- RAG status indicators
- Interactive slicing by:
  - Region
  - Department
  - Product Category
  - Reporting Month

<img width="656" height="365" alt="image" src="https://github.com/user-attachments/assets/3e65802d-a5a6-4aaf-ba68-1b6a69b7ad7b" />

## Revenue Drill-Through

This page allows users to move beyond high-level KPI reporting and investigate revenue performance in greater detail.

Key features include:

- Revenue vs Budget analysis
- Revenue YTD tracking
- Revenue contribution by country
- Revenue contribution by product
- Detailed tabular drill-through views

<img width="662" height="368" alt="image" src="https://github.com/user-attachments/assets/b5782c02-415f-473e-8df4-a9f6f2e7583e" />

## Operations Deep Dive

The Operations page focuses on service delivery, operational efficiency, and customer experience metrics.

Key features include:

- SLA Compliance trends
- Digital Adoption trends
- Complaint Rate monitoring
- Transaction activity monitoring
- NPL Ratio monitoring
- Regional operating performance analysis

<img width="659" height="365" alt="image" src="https://github.com/user-attachments/assets/aa17f137-e8b1-4d8c-9285-5f0d353a1766" />

---
## Business Problem

Senior management requires a single reporting interface that consolidates key financial, operational, and customer performance indicators across multiple business units and regions.

The dashboard was designed to answer questions such as:

- Are revenue targets being achieved?
- Are costs being controlled effectively?
- Is customer growth being sustained?
- Are operational service levels meeting expectations?
- Which regions or business areas require management attention?

---

## Dashboard Deliverables

### Core Deliverables

- `Aurelia_Scorecard.pbix`
- Published Power BI dashboard
- Source dataset (`Aurelia_KPI_Data.xlsx`)
- Supporting methodology document

### Dashboard Pages

#### 1. Executive Summary

Management scorecard covering:

- Revenue
- Profitability
- Cost efficiency
- Assets Under Management (AUM)
- Customer growth
- Customer retention
- Operational performance
- Service quality
- Credit quality

#### 2. Revenue Drill-Through

Provides detailed analysis of:

- Revenue trends
- Revenue vs Budget
- Regional contribution
- Product contribution
- Revenue performance by business area

#### 3. Operations Deep Dive

Provides detailed analysis of:

- SLA compliance
- Digital adoption
- Customer complaints
- Transaction activity
- Non-performing loan performance

---

## Technology Stack

| Component | Technology |
|------------|-------------|
| Dashboard | Power BI Desktop |
| Data Preparation | Power Query |
| Data Modelling | Star Schema |
| Calculations | DAX |
| Data Source | Excel |
| Documentation | Word / PDF / Markdown |

---

## Data Source

### Dataset

**Aurelia Financial Services S.A. (fictional)**

### Reporting Period

**January 2025 – December 2025** 

### Geographic Coverage

- Luxembourg
- Germany
- France
- Belgium

### Dataset Characteristics

The dataset contains operational, customer, lending, transaction, and AUM information designed to simulate a management reporting environment within a financial-services organisation.

---

## Synthetic Data Disclosure

This repository contains **entirely fictional data** created for portfolio and educational purposes.

The dashboard:

- is not based on real institutions
- does not contain confidential information
- is not a regulatory report
- is not a production system
- does not represent actual financial performance

The project is intended solely to demonstrate business intelligence, reporting, and data-modelling skills.

---

# Data Model

## Star Schema Design

The solution uses a dimensional model consisting of one fact table and multiple dimensions.

```text
Dim_Date
     |
Dim_Region
     |
Dim_Product
     |
Dim_Department
     |
KPI_Targets

       ↓

Fact_Performance
```

### Fact Table

#### Fact_Performance

Grain:

> One row per Month × Region × Product

The table contains:

- Revenue
- Cost
- Customer activity
- Operational KPIs
- AUM
- Lending metrics
- Service quality metrics

---

## Dimension Tables

### Dim_Date

Time dimension supporting:

- Year
- Quarter
- Month
- Year-Month reporting

### Dim_Region

Business region hierarchy:

- Luxembourg
- Germany
- France
- Belgium

### Dim_Product

Business products:

- Corporate Lending
- Wealth Advisory
- Payments & Transaction Banking
- Investment & Portfolio Management

### Dim_Department

Business departments used for management reporting.

### KPI_Targets

Target values used to determine KPI status and RAG thresholds.

---

# Data Dictionary

## Fact_Performance

| Field | Description |
|---------|------------|
| Revenue_EUR | Monthly revenue generated |
| Revenue_Budget_EUR | Monthly revenue budget |
| Operating_Cost_EUR | Monthly operating cost |
| Cost_Budget_EUR | Monthly operating cost budget |
| Active_Customers | Active customer population |
| New_Customers | Customer acquisitions |
| Churned_Customers | Customer attrition |
| AUM_EUR | Assets under management |
| AUM_Target_EUR | AUM target |
| Transaction_Count | Transactions processed |
| Digital_Transaction_Count | Digital transactions |
| Complaints | Customer complaints |
| Total_Tickets | Service tickets raised |
| Tickets_Within_SLA | Tickets resolved within SLA |
| Gross_Loan_Balance_EUR | Gross loan exposure |
| NPL_Balance_EUR | Non-performing loans |
| FTE | Full-time equivalent employees |

---

# KPI Dictionary

## Revenue Pillar

### Total Revenue

**Definition**

Total recognised revenue generated during the reporting period.

**Calculation**

```DAX
SUM(Revenue_EUR)
```

**Target**

Revenue Budget

---

### EBITDA Margin

**Definition**

Operating profitability after operating costs.

**Calculation**

```DAX
(Revenue - Operating Cost)
/ Revenue
```

**Target**

≥ 48%

---

### Assets Under Management (AUM)

**Definition**

Closing-period assets under management.

**Calculation**

Closing balance using LASTDATE logic.

**Target**

100% of target

---

## Cost Pillar

### Cost vs Budget %

**Definition**

Comparison of actual operating cost against budget.

**Target**

≤ 100%

---

### Cost-to-Income Ratio

**Definition**

Operating cost divided by revenue.

**Calculation**

```DAX
Operating Cost / Revenue
```

**Target**

≤ 48%

---

### Revenue per FTE

**Definition**

Revenue generated per employee.

**Calculation**

```DAX
Revenue / Closing FTE
```

**Target**

€180,000+

---

## Customer Pillar

### Active Customers

**Definition**

Closing customer base.

**Target**

100% of target

---

### Net New Customers

**Definition**

New customers less customer attrition.

**Calculation**

```DAX
New Customers - Churned Customers
```

---

### Customer Churn Rate

**Definition**

Customers lost relative to active customer base.

**Target**

≤ 1.50%

---

### Complaint Rate

**Definition**

Complaints per 1,000 customers.

**Target**

≤ 2 complaints per 1,000 customers

---

## Operations Pillar

### Transaction Volume

**Definition**

Transactions processed during the reporting period.

### Digital Adoption Rate

**Definition**

Digital transactions divided by total transactions.

**Target**

≥ 78%

---

### SLA Compliance

**Definition**

Tickets resolved within SLA divided by total tickets.

**Target**

≥ 95%

---

### Non-Performing Loan Ratio

**Definition**

Non-performing loans divided by gross loan balance.

**Calculation**

```DAX
NPL Balance / Gross Loan Balance
```

**Target**

≤ 1.80%

---

# Data Modelling Considerations

## Mixed-Grain Data Challenge

During development, a data-quality issue was identified.

The fact table operates at:

> Month × Region × Product

However, several operational metrics were recorded at:

> Month × Region

These values were therefore repeated across product records.

Affected measures included:

- Active Customers
- New Customers
- Churned Customers
- Complaints
- FTE
- SLA activity
- Ticket volumes

To prevent double counting, DAX measures were redesigned using region-level aggregation logic and closing-period calculations where appropriate. 

This correction represents one of the key technical modelling exercises completed during the project.

---

# Validation Summary

The following areas were tested during development:

- Relationship integrity
- Slicer functionality
- Drill-through navigation
- Time-intelligence calculations
- Revenue reconciliation
- Cost reconciliation
- AUM calculations
- Operational KPI aggregation
- Customer KPI calculations

No material reconciliation issues remained after model refinement.

---

# Key Skills Demonstrated

### Data Modelling

- Star schema design
- Relationship management
- Dimension modelling
- Fact table design

### Power BI

- Dashboard development
- Interactive filtering
- Drill-through navigation
- Visual analytics

### DAX

- CALCULATE
- TOTALYTD
- SAMEPERIODLASTYEAR
- LASTDATE
- DIVIDE
- Conditional KPI logic

### Business Analysis

- Management reporting
- KPI framework development
- Performance monitoring
- Executive dashboard design

---

# Limitations

The project uses a single calendar year of data (2025).

As a result:

- Prior-year metrics return blank values
- Year-over-year analysis cannot be populated
- Trend analysis is limited to a single reporting year

The KPI framework still includes these measures to demonstrate model design, but the source data does not contain historical periods required for population.

---

# How to Reproduce

1. Download the repository.
2. Open `Aurelia_KPI_Data.xlsx`.
3. Open `Aurelia_Scorecard.pbix`.
4. Refresh the dataset.
5. Verify table relationships.
6. Review DAX measures.
7. Interact with dashboard pages and drill-through functionality.

---

# Portfolio Summary

This project demonstrates the design, development, and publication of a company-wide KPI scorecard for a fictional Luxembourg financial-services organisation. The solution combines dimensional modelling, Power Query transformation, DAX calculations, KPI governance, drill-through reporting, and management dashboard design to provide decision-ready performance reporting across Revenue, Cost, Customer, and Operations functions. The published Power BI dashboard can be accessed directly through the dashboard link above, allowing reviewers to interact with slicers, drill-through functionality, KPI cards, and supporting visualisations without downloading the PBIX file.
