# power_bi
# 📊 Region-wise Profitability Dashboard — Power BI

**An interactive Power BI dashboard built on a star-schema retail dataset (2023–2024) that reveals which regions, states, and product categories actually drive profit — not just sales.**

![Tool](https://img.shields.io/badge/Tool-Power%20BI%20Desktop-F2C811?logo=powerbi&logoColor=black)
![Language](https://img.shields.io/badge/Measures-DAX-yellow)
![Domain](https://img.shields.io/badge/Domain-Retail%20%2F%20Regional%20Profitability-orange)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📁 Table of Contents
- [Overview](#-overview)
- [Business Problem](#-business-problem)
- [Objectives](#-objectives)
- [Dataset](#-dataset)
- [Data Model](#-data-model)
- [Tools & Technologies](#-tools--technologies)
- [Project Workflow](#-project-workflow)
- [Dashboard Design](#-dashboard-design)
- [Key KPIs](#-key-kpis)
- [Key Insights](#-key-insights)
- [Power BI Skills Demonstrated](#-power-bi-skills-demonstrated)
- [Repository Structure](#-repository-structure)
- [How to Use](#-how-to-use-this-project)
- [Future Improvements](#-future-improvements)
- [References](#-references)
- [Author](#-author)

---

## 🧾 Overview

Organizations generate massive volumes of sales data across products, customers, regions, and time — but when that data is fragmented across sales, finance, and operational systems, it becomes difficult for stakeholders to tell which regions are actually profitable versus which just have high sales volume. This project, **Region-wise Profitability Dashboard**, uses a two-year (2023–2024) Indian retail dataset structured as a star schema to build an interactive Power BI dashboard that surfaces sales, profit, and profitability drivers by region, state, and product category.

Using DAX measures, interactive slicers, and drill-through, the dashboard lets management move from a single company-wide profit figure down to the exact region, category, or product responsible for it.

## ❗ Business Problem

A retail company generates thousands of transactions every day across multiple regions. While this data exists in spreadsheets, it's fragmented across sales, finance, and operational systems, making it difficult to:

- Identify which regions are high-performing versus low-performing
- Understand the factors affecting regional profitability — sales volume, discounts, operational costs
- React to trends quickly, since traditional static reports are too slow to support timely decisions
- Allocate resources efficiently across regions and product lines

An interactive Power BI dashboard is needed to convert this fragmented, raw data into a single, explorable source of truth.

## 🎯 Objectives

- Analyze profit performance across different regions
- Identify monthly sales trends
- Evaluate product performance based on sales and profitability
- Analyze sales and profit contribution at both the regional and state level
- Build an executive-friendly dashboard for business decision-making
- Improve data interpretation through interactive visualizations

## 🗃️ Dataset

| Detail | Description |
|---|---|
| **Source** | Regional Sales Trends dataset (2023–2024) |
| **File** | `Regional_Sales_Trends_2023_2024.xlsx` |
| **Structure** | Star schema — 1 fact table + 4 dimension tables |
| **Time Span** | Jan 2023 – Dec 2024 (2 full years, 731 days) |
| **Regions** | North, East, South, West |
| **States Covered** | 16 |
| **Product Categories** | Electronics, Fashion, Beauty, Grocery, Home |

## 🧱 Data Model

The dataset is structured as a proper star schema, ideal for Power BI's relational modeling:

| Table | Rows | Role | Key Columns |
|---|---|---|---|
| **Sales** (fact) | 15,000 | Central fact table | OrderID, OrderDate, CustomerID, ProductID, Region, State, Quantity, UnitPrice, Discount, Sales, Profit, PaymentMode, ShipMode |
| **Customers** (dim) | 2,000 | Customer attributes | CustomerID, CustomerName, Age, Gender, City, Region, SignupDate |
| **Products** (dim) | 20 | Product attributes | ProductID, ProductName, Category, SubCategory, Brand, UnitPrice |
| **DimDate** (dim) | 731 | Date/calendar table | Date, Year, MonthNumber, MonthName, MonthYear, Quarter |
| **Payments** (dim) | 5 | Payment mode lookup | PaymentID, PaymentMode |

This structure supports clean one-to-many relationships (Sales → Customers/Products/DimDate/Payments) — the foundation for reliable DAX measures and fast slicer performance.

## 🛠️ Tools & Technologies

- **Power BI Desktop** — data modeling and dashboard design
- **DAX (Data Analysis Expressions)** — calculated measures (Total Sales, Total Profit, Profit Margin, etc.)
- **Power Query** — data import and relationship modeling
- **Star Schema Design** — fact/dimension table modeling for scalable analysis

## 🔄 Project Workflow

1. **Data Collection** — Sourced the Regional Sales Trends (2023–2024) dataset.
2. **Data Import** — Loaded all five tables into Power BI Desktop via Power Query.
3. **Data Modeling** — Built star-schema relationships between the Sales fact table and the Customers, Products, DimDate, and Payments dimension tables.
4. **KPI Definition (DAX)** — Created measures for Total Sales, Total Profit, Profit Margin, and Total Orders.
5. **Multi-Level Analysis:**
   - **Sales Trend Analysis** — sales growth over time using DimDate
   - **Regional Analysis** — high vs. low performing regions and states
   - **Product Analysis** — category and sub-category performance comparison
   - **Profit Analysis** — profitability drivers across regions and products
6. **Dashboard Design** — Assembled Executive, Sales Trend, Regional Analysis, and Product Analysis views.
7. **Interactivity** — Added slicers and filters (Region, Category, Date, Payment Mode) for self-service exploration.
8. **Testing & Finalization** — Verified DAX measure accuracy and cross-filter behavior before finalizing.

## 🖥️ Dashboard Design

The project is structured as a set of linked dashboard pages:

| Dashboard Page | Purpose |
|---|---|
| **Executive Dashboard** | High-level KPI summary — Total Sales, Total Profit, Profit Margin, Total Orders |
| **Sales Trend Dashboard** | Monthly/yearly sales & profit trend using the DimDate table |
| **Regional Analysis** | Sales and profit performance broken down by Region and State |
| **Product Analysis** | Category and Sub-Category performance comparison by Sales and Profit |

*(Add dashboard screenshots or a `.pbix` file link here once available — see [How to Use](#-how-to-use-this-project).)*

## 📌 Key KPIs

Calculated directly from the dataset:

| Metric | Value |
|---|---|
| Total Sales | **₹35,44,80,935.67** (~₹35.4 Cr) |
| Total Profit | **₹5,50,18,915.74** (~₹5.5 Cr) |
| Overall Profit Margin | **15.52%** |
| Total Orders | **15,000** |
| Unique Customers | **2,000** |
| Average Discount | **3.76%** |

## 💡 Key Insights

1. **North region leads on both sales and profit.** North generates the highest sales (₹9.31 Cr) and the highest profit (₹1.45 Cr) of all four regions — the benchmark region for the rest of the business.
2. **Regional performance is more balanced than expected.** Sales and profit across North, West, East, and South differ by less than 8% at the top vs. bottom — this is not a "one region dominates" story, but a case of consistent nationwide execution with North slightly ahead.
3. **Electronics is the profit engine.** Electronics alone contributes ₹15.79 Cr in sales and ₹2.45 Cr in profit — more than double the next-highest category (Fashion) — making it the single most important category to protect and grow.
4. **Fashion and Beauty are close competitors for the #2 spot.** Fashion (₹6.23 Cr sales, ₹0.98 Cr profit) and Beauty (₹6.19 Cr sales, ₹0.96 Cr profit) perform almost identically — both maintain a healthy ~15.7% margin, in line with the company average.
5. **Home is the smallest and lowest-margin category.** Home generates the least sales (₹2.65 Cr) and profit (₹0.40 Cr) of the five categories, and is a candidate for either a targeted growth push or portfolio rationalization.
6. **Discounting is modest and controlled.** An average discount rate of just 3.76% suggests the healthy overall 15.52% profit margin is not being eroded by aggressive discounting — a sign of disciplined pricing strategy.

> 💬 **Takeaway for management:** Profitability is fairly evenly distributed across regions, so growth strategy should focus on category mix — doubling down on Electronics, sustaining Fashion/Beauty, and deciding whether to invest in or scale back Home.

## 🧩 Power BI Skills Demonstrated

- Star-schema data modeling (fact/dimension table relationships)
- DAX measure creation (Total Sales, Total Profit, Profit Margin, dynamic KPIs)
- Power Query for data import, cleaning, and relationship setup
- Time intelligence using a dedicated Date dimension table
- Interactive slicers, filters, and cross-page drill-through
- Executive dashboard design — layout hierarchy and visual storytelling

## 📂 Repository Structure

```
Region-wise-Profitability-Dashboard-PowerBI/
│
├── README.md                                      # Project documentation (this file)
│
├── Data/
│   └── Regional_Sales_Trends_2023_2024.xlsx       # Source dataset — star schema (5 sheets, 15,000 sales records)
│
└── Documentation/
    └── Project_Report.docx                        # Full project report (abstract, methodology, conclusion)
```

> 📌 **Note:** This repository currently includes the source dataset and full project report. Add your `.pbix` (Power BI workbook) file and dashboard screenshots to a `Dashboard/` and `Images/` folder respectively for a complete, recruiter-ready portfolio piece — see suggestions below.

## 🚀 How to Use This Project

1. Clone or download this repository.
2. Open `Data/Regional_Sales_Trends_2023_2024.xlsx` in Power BI Desktop and load all five sheets (Sales, Customers, Products, DimDate, Payments).
3. Set up relationships: `Sales[CustomerID] → Customers[CustomerID]`, `Sales[ProductID] → Products[ProductID]`, `Sales[OrderDate] → DimDate[Date]`, `Sales[PaymentMode] → Payments[PaymentMode]`.
4. Refer to `Documentation/Project_Report.docx` for the full write-up — abstract, methodology, and conclusions.
5. *(Recommended)* Publish the `.pbix` file to Power BI Service and link it here so recruiters can interact with the live dashboard directly.

## 🔮 Future Improvements

- Publish the dashboard to **Power BI Service** for web-based sharing and scheduled refresh.
- Add **forecasting visuals** (built-in Power BI forecasting or Python/R integration) for future revenue/profit prediction.
- Introduce **what-if parameters** to model the impact of discount changes on profit margin.
- Build **drill-through pages** for customer- or product-level root-cause analysis.
- Design a **mobile-optimized** report layout.
- Integrate **row-level security (RLS)** to simulate a real regional-manager access model.

## 📚 References

1. Regional Sales Trend Dashboard in Power BI (2023–2024) tutorial (YouTube)
2. Regional Sales Trends dataset (Google Drive)
3. Real-Time Power BI Project — End-to-End Insurance Domain tutorial (YouTube)
4. Dashboard background design tutorial — Data Tutorials (YouTube)

## 👩‍💻 Author

**Kamatchi Keerthika**
Data Analyst | SQL • Excel • Power BI • Tableau • Python
📍 Chennai, India

*This project is part of a self-directed data analytics portfolio built to demonstrate end-to-end BI dashboard development — from a fragmented, multi-table dataset to an executive-ready profitability view.*

---

⭐ If you found this project useful or interesting, consider starring the repository!
