# Australian Retail Customer Segmentation (Python + Power BI)

Customer segmentation using RFM features + K-Means clustering, packaged with a Power BI dashboard for interactive exploration.

---

## What this repo contains
- A full Python notebook workflow (cleaning → transaction integrity → RFM → clustering)
- A Power BI dashboard built on the produced customer-level dataset
- Cleaned CSV outputs used by Power BI

---

## Results (reproducible from `powerbi_enriched_data.csv`)
- Customers: **788**
- Total revenue: **$715,541.58**
- Avg revenue per customer: **$908.05**

### Cluster breakdown
- Cluster 0: **414 customers**, **$397,421.44** (55.54%), avg **$959.96/customer**
- Cluster 1: **106 customers**, **$113,668.90** (15.89%), avg **$1,072.35/customer**
- Cluster 2: **268 customers**, **$204,451.24** (28.57%), avg **$762.88/customer**

---

## Data quality work (transaction integrity)
The raw dataset re-used `order_no` inconsistently across key cart-level fields.  
I validated order integrity using cart-level uniqueness checks and rebuilt transaction grouping:

- Unique orders: **1,435**
- Valid cart-consistent orders: **394**
- Inconsistent orders: **1,041 / 1,435** (**72.54%**)
- Rows tied to inconsistent orders: **4,597 / 5,000**

This ensured Frequency and Monetary metrics were computed on stable transaction units.

---

## How to reproduce
1) Run the notebook:
   - `Australian Retail Customer Segmentation.ipynb`
2) Open the Power BI dashboard:
   - `Australian Retail Customer Segmentation.pbix`

---

## Files
- `dataaus.csv` / `dataausclean.csv` — raw and cleaned transaction datasets
- `rfm_*.csv` — intermediate and final clustering datasets
- `powerbi_enriched_data.csv` — customer-level dataset used in Power BI
- `Australian Retail Customer Segmentation.pbix` — dashboard
- `cluster_insights.txt` — segment-level actions in plain English

---

## Review request
Open an Issue titled: **Review: retail-customer-segmentation-australia**  
I want feedback on dashboard layout, metric naming, and reproducibility clarity.
