# Olist E-Commerce Analytics Dashboard

A 9-page Power BI dashboard analyzing ~99K orders from the Brazilian e-commerce marketplace Olist — revenue trends, category and product performance, customer geography, delivery/logistics, reviews, payments, and seller performance, built on a PostgreSQL data model with DirectQuery and DAX.

## Dataset

[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) — Kaggle, published by Olist. Real, anonymized order data (2016–2018) covering ~100K orders across multiple relational tables (orders, order items, products, customers, sellers, payments, reviews, geolocation).

The raw CSVs were loaded into PostgreSQL and modeled into a star schema (fact table + date dimension) before being connected to Power BI via DirectQuery.

## Dashboard Pages

| Page | What it covers |
|---|---|
| **Overview (Executive Dashboard)** | Total revenue, orders, customers, AOV, on-time delivery rate, revenue trend, top categories, order status split, top states by revenue |
| **Sales Trends** | Revenue vs. last year, rolling 30-day revenue, YTD revenue, category × year performance |
| **Category & Product Analysis** | AOV vs. orders by category, top categories by rating, revenue share by category, full category performance table |
| **Customer Geography** | Top states/cities by revenue, state × category performance |
| **Delivery & Logistics** | Late orders, on-time delivery rate, delivery days by category, late order rate by state |
| **Customer Reviews & Ratings** | Average rating, positive/negative review %, rating distribution, rating by on-time vs. late delivery, rating by category |
| **Payment Analysis** | Payment method distribution, average installments, payment value trend, payment summary |
| **Seller Performance** | Total sellers, revenue per seller, top sellers, revenue by seller state, seller × category performance |
| **Drillthrough (Category Details)** | Right-click drillthrough from any category to a dedicated detail page — revenue trend by year, customer state breakdown, and KPI cards scoped to that category |

## Key Metrics

- **Total Revenue:** R$14.21M across 98.67K orders
- **AOV:** R$144.01
- **On-Time Delivery Rate:** 93.23%
- **Average Review Rating:** 4.03 / 5 (77.56% positive, 14.19% negative, 8.25% neutral)

## Techniques Used

- **DirectQuery** against PostgreSQL — no data duplication, always-live model
- **DAX measures**: rolling 30-day revenue, year-over-year comparison, AOV, on-time/late delivery rate, positive/negative review %, revenue-per-seller
- **Calculated column** to handle nulls in the category field for accurate downstream aggregation
- **Drillthrough** page bound to category, with a custom back-navigation button
- Cross-visual filtering, bookmarks-free navigation via page tabs

## Files

- `olist-ecommerce-analytics-dashboard.pbix` — the Power BI report (open in Power BI Desktop; DirectQuery connection details will need to point at your own PostgreSQL instance)
- `screenshots/` — page-by-page exports of the dashboard (see below)

## Screenshots

See the `screenshots/` folder for a full page-by-page walkthrough, or the images below (add these once exported from Power BI: File → Export → PDF, then convert each page to PNG, or use Snipping Tool per page).

## Author

Devesh Rathod 
