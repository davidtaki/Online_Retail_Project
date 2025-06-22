# **Dataset Overview**

This repository contains an **enriched retail-transaction corpus** that blends the well-known *“Online Retail”* log (item-level invoices from a UK giftware company) with **synthetic customer demographics** and a **two-tier product-category hierarchy**.  
It provides a privacy-safe playground that resembles the raw material you would feed into marketing-analytics pipelines: every purchase line is preserved, but each customer now carries age, gender, household structure, education level and income bracket—precisely the variables you need for segmentation, CLV modelling or uplift experiments.




## Native Transactional Columns 

Every row in **`online_retail_utf_8_2009_2010.csv`** and **`online_retail_utf_8_2010_2011.csv`** represents a single SKU on an invoice.

| Column         | Description                                                                   |
|----------------|-------------------------------------------------------------------------------|
| `InvoiceNo`    | Order identifier (repeats across items within the same basket)                |
| `StockCode`    | SKU / product ID                                                              |
| `Description`  | Free-text product description                                                 |
| `Quantity`     | Units sold                                                                    |
| `UnitPrice`    | Unit price in GBP                                                             |
| `InvoiceDate`  | Full timestamp                                                                |
| `CustomerID`   | Surrogate customer key (no PII)                                               |
| `Country`      | Billing country recorded at checkout                                          |

*No personal information is present in the original data; only the anonymous customer key survives.*



## Synthetic Customer Attributes

To unlock marketing use-cases we generated a **realistic demographic profile** for every distinct `CustomerID`.  
Values were drawn from age-dependent or household-dependent probability models, so they correlate in ways that resemble real populations (e.g. older customers earn more on average; couples are likelier to have children).



## Product Hierarchy

A separate CSV assigns a **marketing taxonomy** to every SKU.  
The image above shows the **17 `SubCategory_eng`** values grouped under **9 `MainCategory_eng`** headings, e.g.

* **Home and Decor** → *Home decor*, *Storage*  
* **Garden products** → *Garden decor*, *Garden tools*  
* **Lighting** → *Lamps*, *Candles*  

This mapping is invaluable for basket-affinity studies, category-level seasonality analysis or assortment-planning tasks.



## Typical Analytic Scenarios

With behaviour, product context and demographics united, you can:

* build RFM- or k-means-based** customer segments  
* estimate customer lifetime value or churn propensity  
* model promo uplift by crossing income brackets with price sensitivity (once added)  
* run market-basket analysis at sub-category level instead of raw SKUs  
* craft realistic Tableau / Power BI dashboards without privacy hurdles  



## Licensing & Provenance

* The transactional core is derived from the UCI “Online Retail” dataset *(public domain)*.  
* All demographic attributes were algorithmically fabricated; no real persons are represented.  
* The category hierarchy was authored manually with the aid of GPT for translation and consistency checks.  

Commercial reuse is permitted as-is, but comes without warranty.

Enjoy exploring—pull requests and ⭐ stars are welcome!
