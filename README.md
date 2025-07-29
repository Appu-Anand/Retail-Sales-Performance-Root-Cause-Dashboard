# 🧠 Retail Sales Performance & Root Cause Analysis Dashboard

> A Power BI dashboard that does more than just display metrics — it pinpoints *why* things happen. Built to drive decisions, not just visualizations.

![Retail Sales Dashboard](./main/dashboard_preview.png)

## 📌 Project Summary

This project dives deep into retail sales data to uncover not just **what’s happening**, but **why it’s happening**. By integrating performance metrics, anomaly detection, and root cause layers, this dashboard delivers a complete analytical narrative that’s both executive-friendly and actionable.

---

## 🎯 Objectives

- Track core retail KPIs: Revenue, Profit, Discount, and Delivery Timeliness.
- Identify regional and category-wise profit patterns.
- Surface **root causes** behind profit dips.
- Enable drill-down with filters to assist category managers and business teams.

---

## 📊 Key Features

| Metric | Description |
|--------|-------------|
| 🧾 **Total Revenue & Profit** | Track performance across all sales over a year |
| 💸 **Avg. Discount** | Understand how discounting impacts margins |
| 🚚 **Late Deliveries** | Highlight logistics issues affecting profitability |
| 📉 **Monthly Profit Trend** | Time-series analysis segmented by region |
| 🧩 **Root Cause Widgets** | Combine Category, Discount, and Delivery to isolate drivers of poor performance |

---

## 🔍 Business Insights

- 🔻 **South Region**: Profit fell significantly post-July 2024.
- 🔥 **High Discounts (21%+)**: Strong link to margin erosion, especially in **Technology** category.
- 🛻 **Late Deliveries**: Consistently correlated with lower average profit per order.

---

## 🧰 Tools Used

| Tool | Purpose |
|------|---------|
| **Power BI** | Dashboard creation, DAX measures, interactivity |
| **Excel** | Data cleaning and preprocessing |
| **DAX** | Custom calculations like discount bins, average delivery profit, and conditional KPIs |

---

## 🧮 DAX Highlights

```dax
Profit Margin % = DIVIDE([Total Profit], [Total Revenue], 0)

Late Delivery % = 
    DIVIDE(CALCULATE(COUNTROWS(Sales), Sales[Delivery Status] = "Late"), COUNTROWS(Sales))

Discount Bin = 
    SWITCH(TRUE(),
        Sales[Discount] <= 0.10, "0%-10%",
        Sales[Discount] <= 0.20, "11%-20%",
        "21%-30%")
