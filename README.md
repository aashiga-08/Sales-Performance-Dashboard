# Sales-Performance-Dashboard

An interactive, static web dashboard for analysing the supplied Amazon product dataset. It is designed for a Netlify deployment and requires no Power BI licence, server, database, or build process.

## Features

- Filterable Category and Discount Band controls
- KPI cards for estimated revenue, estimated return loss, estimated net revenue, return rate, rating count, and average rating
- Heatmap of average rating by category and discount band
- Combined category chart for estimated revenue and average discount
- Top 10 products by estimated revenue
- Responsive layout for desktop and mobile viewing

## Project structure

```text
sales-dashboard/
|-- index.html              # Page structure
|-- style.css               # Responsive visual design
|-- app.js                  # Data loading, filters, calculations, and Plotly charts
|-- amazon_cleaned.csv      # Source data used by the dashboard
|-- README.md               # This documentation
`-- Business_Insights_Report.pdf
```


## Data preparation and methodology

- The dashboard uses `product_id` as the product key and keeps one record per product before calculating metrics.
- Price, discount, ratings, and rating-count fields are handled as numeric values.
- Discount bands are calculated as 0-19%, 20-39%, 40-59%, 60-79%, and 80-100%.
- Estimated revenue is supplied by the cleaned dataset; when unavailable, the dashboard uses `discounted_price x rating_count` as a fallback.
- Estimated return loss and estimated net revenue use the cleaned fields. The dashboard has a rating-based fallback estimate only to ensure visual continuity if values are missing.

## Important limitations

- `rating_count` is a customer-review signal, not verified units sold.
- Revenue, returns, and net revenue are estimates, not audited transaction figures.
- The source dataset has no region, state, city, customer location, or date field. Therefore, a truthful regional or time-series sales analysis is not included.
- This dashboard is appropriate for exploratory analysis and portfolio demonstration, not financial reporting.
