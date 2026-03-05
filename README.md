# Australian Retail Customer Segmentation (Python + Power BI)

Customer segmentation using RFM-style features and K-Means clustering, packaged with a Power BI dashboard built on the generated customer-level dataset.

## What’s in this repo
- `Australian Retail Customer Segmentation.ipynb` — end-to-end notebook (cleaning → transaction integrity → customer features → clustering)
- `Australian Retail Customer Segmentation.pbix` — Power BI dashboard
- `dataaus.csv` — raw transactional dataset (5,000 rows)
- `dataausclean.csv` — cleaned transactional dataset
- `powerbi_enriched_data.csv` — customer-level dataset used by the Power BI dashboard
- `powerbi_data.csv` — customer-level dataset (customer metrics + last purchase date)
- `rfm_clustered.csv` — clustered customer output
- `cluster_analysis.txt` — numeric cluster summary
- `cluster_insights.txt` — plain-English segment interpretation and actions
- `powerbi_setup.txt` — exact Power BI build notes

## Results (reproducible from `powerbi_enriched_data.csv`)
- Customers: **788**
- Total revenue: **$715,541.58**
- Average revenue per customer: **$908.05**

### Cluster breakdown (K-Means)
- Cluster 0: **414 customers**, **$397,421.44** (**55.54%**), avg **$959.96/customer**
- Cluster 1: **106 customers**, **$113,668.90** (**15.89%**), avg **$1,072.35/customer**
- Cluster 2: **268 customers**, **$204,451.24** (**28.57%**), avg **$762.88/customer**

## Data quality work (transaction integrity)
The raw dataset re-used `Order No` inconsistently across cart-level fields.  
I validated cart integrity by checking whether each `Order No` maps to a single consistent combination of:
- `Order Date`
- `Customer Name`
- `Ship Date`
- `Ship Mode`
- `State`
- `Customer Type`

Integrity outcome (computed from `dataaus.csv`):
- Unique orders: **1,435**
- Valid cart-consistent orders: **394**
- Inconsistent orders: **1,041 / 1,435 (72.54%)**
- Rows tied to inconsistent orders: **4,597 / 5,000**

This ensures Frequency/Monetary features are computed on stable customer-transaction units rather than corrupted order groups.

## How to reproduce
1) Run the notebook:
   - `Australian Retail Customer Segmentation.ipynb`

2) Open the Power BI dashboard:
   - `Australian Retail Customer Segmentation.pbix`

3) Confirm the dashboard uses:
   - `powerbi_enriched_data.csv` (customer-level table)

## Feedback I want (please keep it practical)
Open a GitHub Issue titled: **Review: retail-customer-segmentation-australia** and tell me:
1) Does the dashboard layout show the right story in the first 10 seconds?
2) Are any measures/labels confusing or misleading?
3) If you were hiring, what would you want to see added/removed?
