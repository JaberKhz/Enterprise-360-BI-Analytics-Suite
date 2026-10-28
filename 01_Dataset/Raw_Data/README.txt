POWER BI PORTFOLIO PROJECT - GLOBAL SALES & SUPPLY CHAIN ANALYTICS

Files are deliberately generated for training and are synthetic (not real customer data).
Encoding: UTF-8 with BOM for smoother opening in Excel.

Suggested import order:
1) Load every CSV into Power BI using Get Data > Text/CSV.
2) Append Fact_Sales_2023.csv, Fact_Sales_2024.csv and Fact_Sales_2025.csv into one Fact_Sales query.
3) Clean each dimension so its key is unique before creating relationships.
4) Replace blank foreign keys with the matching UNKNOWN member where appropriate:
   CUST-UNKNOWN, PROD-UNKNOWN, BR-UNKNOWN, EMP-UNKNOWN, WH-UNKNOWN.
5) Merge Dim_Suppliers into Dim_Products on SupplierID if you want a flattened product dimension.
6) Treat all Fact_Sales_* dates as raw text until formats are standardized and invalid values handled.
7) Fact_Shipments contains ShipDate, PromisedDeliveryDate and DeliveryDate for on-time delivery analysis.
8) Dim_Date is a clean date dimension from 2023-01-01 to 2026-12-31.
9) Normalize Currency to ISO uppercase codes, parse the relevant date, build a Date|Currency key,
   and merge Fact_FXRates to sales (OrderDate), returns (ReturnDate) and shipments (ShipDate).
10) Use USD_Rate to derive USD-converted amounts. The exchange rates are synthetic training rates,
    not authoritative historical market rates. Sales targets are denominated in USD.

Intentional training issues include duplicate rows, inconsistent date formats, blanks,
misspellings, inconsistent category/case/whitespace, invalid numeric outliers, missing foreign keys,
negative inventory values and a small number of impossible date sequences. Review and fix them
in Power Query; do not assume every extreme value is an error without business validation.

Important: these are synthetic practice records, not actual business results.
