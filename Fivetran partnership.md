# From Weeks to Minutes: Accelerate building your Bayesian Marketing Mix Model using Fivetran & PyMC-Marketing

**Table of Contents**×

-   [The Integration That Changes Everything](#the-integration-that-changes-everything)
-   [What We Shipped 🚀](#what-we-shipped-)
-   [How It Fits in Your Analytics Stack](#how-it-fits-in-your-analytics-stack)
-   [Ingestion & Standardization (Fivetran + dbt)](#ingestion-standardization-fivetran-dbt)
-   [Model-Ready Shaping (PyMC-Marketing loaders)](#model-ready-shaping-pymc-marketing-loaders)
-   [Modeling & Decisioning (PyMC-Marketing)](#modeling-decisioning-pymc-marketing)
-   [Hierarchical Approaches When Needed](#hierarchical-approaches-when-needed)
-   [What You Can Expect](#what-you-can-expect)
-   [Who Should Use This?](#who-should-use-this)
-   [Get Started Today](#get-started-today)
-   [Acknowledgements](#acknowledgements)
-   [Further Reading](#further-reading)

# From Weeks to Minutes: Accelerate building your Bayesian Marketing Mix Model using Fivetran & PyMC-Marketing

![Blog](https://res.cloudinary.com/dx3t8udaw/image/upload/v1756847861/Five_Tran_Partnership_Announcement_fd7076fcd2.png)

September 01, 2025

By PyMC Labs

Marketing teams consistently report that data wrangling consumes the majority of their Marketing Mix Modeling efforts, leaving little time for the insights that actually drive decisions. This fundamental challenge affects everyone from teams building their first MMM to those optimizing existing ones. What modern growth teams really want are two things: speed to first insight and confidence in the data and methods behind the numbers

**Through our strategic partnership with [Fivetran](https://www.fivetran.com/), we're changing that equation entirely.** Fivetran and dbt already standardize multi-platform advertising and commerce data, removing weeks of ad-hoc wrangling. PyMC-Marketing now turns those standardized tables into a production-grade Bayesian MMM complete with uncertainty quantification, adstock/saturation effects, and budget optimization without forcing teams to rebuild plumbing they already have.

## **The Integration That Changes Everything**[#](#the-integration-that-changes-everything)

In concrete terms, Fivetran's **ad\_reporting** dbt package harmonizes spend, impressions, clicks, and conversion metrics from major channels (Google, Meta, LinkedIn, TikTok, Amazon, etc.) into a unified schema (e.g., ad\_reporting\_ad\_report). Crucially, it also supports **unioning multiple connections,** say, multiple markets or brands, so analysts can analyze blended performance while still tracing each record back to its origin via a source\_relation field. That "many sources, one shape" design is exactly what a robust MMM pipeline needs.

PyMC-Marketing then picks up where your warehouse leaves off. Based on that data, our Bayesian MMM API estimates channel effects with proper uncertainty, handles carryover (adstock) and saturation, and supports budget allocation, calibration to experiments, and time-varying dynamics. These capabilities are difficult to bolt onto a spreadsheet or rules-based approach.

## **What We Shipped 🚀**[#](#what-we-shipped-)

As part of our collaboration with Fivetran, PyMC-Marketing now includes **data loaders** that transform Fivetran/dbt outputs into MMM-ready inputs in a few lines (illustrated here with Shopify, but extensible to any e-commerce platform):

-   **process\_fivetran\_ad\_reporting(...)** turns long-format ad reporting tables into a wide, date-indexed design matrix (X) by platform and metric (e.g., impressions or spend).
    
-   **process\_fivetran\_shopify\_unique\_orders(...)** converts Shopify orders into a clean target series (y) for modeling conversions/revenue.
    

```python
from pymc_marketing.data.fivetran import (
    process_fivetran_ad_reporting,
    process_fivetran_shopify_orders_unique_orders,
)

campaign_df = pd.read_sql("SELECT * FROM <schema>.<any_fivetran_ad_report>", con=conn)
orders_df = pd.read_sql("SELECT * FROM <schema>.<shopify_report>", con=conn)

x = process_fivetran_ad_reporting(
    campaign_df, 
    value_columns="spend",
    rename_date_to="date"
)
# Result: date | facebook_ads_spend | google_ads_spend | ...

# Process conversion data (orders) as target variable
y = process_fivetran_shopify_unique_orders(orders_df)
# Result: date | orders

# Use in MMM model
mmm = MMM(...)
mmm.fit(X=x, y=y["orders"])
```

  
These helpers are built around the schemas emitted by Fivetran's dbt packages and come with example CSVs and tests. They're designed to be run directly on a simple SELECT \* FROM . (and analogous Shopify tables) via pandas.read\_sql, minimizing glue code between your warehouse and your MMM.  
  

You can browse the **"MMM Fivetran Connectors"** example notebook in our docs to see the end-to-end flow from querying standardized tables to fitting an MMM and inspecting outputs. The notebook demonstrates switching between metrics (e.g., impressions vs. spend), handling missing dates, and producing the wide matrix expected by the model.

  

## **How It Fits in Your Analytics Stack**[#](#how-it-fits-in-your-analytics-stack)

### **Ingestion & Standardization (Fivetran + dbt)**[#](#ingestion-standardization-fivetran-dbt)

Fivetran connectors land raw platform data; and Fivetran’s quickstart data models (dbt based) transform it into consistent reporting layers such as ad\_reporting\_ad\_report, alongside platform-specific rollups. The package explicitly supports **unioning multiple accounts/regions/brands**. The resulting models include a source\_relation column for lineage. This is ideal for MMM use cases that span multiple markets or portfolios.

### **Model-Ready Shaping (PyMC-Marketing loaders)**[#](#model-ready-shaping-pymc-marketing-loaders)

Our loaders aggregate by platform and date, pivot to wide format, fill gaps if requested, and rename columns to MMM-friendly conventions (e.g., facebook\_ads\_spend). A corresponding target loader processes Shopify orders to a daily series. With X and y prepared, you can fit a Bayesian MMM immediately.

### **Modeling & Decisioning (PyMC-Marketing)**[#](#modeling-decisioning-pymc-marketing)

The MMM API provides carryover and shape (saturation) effects, full posterior uncertainty for ROAS and contributions, budget optimization and scenario analysis, plus optional time-varying effects and experiment calibration.

### **Hierarchical Approaches When Needed**[#](#hierarchical-approaches-when-needed)

For teams managing multiple brands or regions, the framework scales to multidimensional approaches without sacrificing individual market insights.

The result is a clean, auditable pipeline: **connect** → **standardize (dbt)** → **load (PyMC-Marketing)** → **infer (Bayesian MMM) → act.**  

### **What You Can Expect**[#](#what-you-can-expect)

1.  **Time-to-insight is measured in days, not months.** Teams already using Fivetran/dbt can skip bespoke cleaning and schema mapping. The standardized outputs slot directly into our loaders, so you can focus on model assumptions and decision-making instead of ETL.
2.  **Confidence and governance.** dbt's tested transformations, plus PyMC's probabilistic treatment of uncertainty, result in MMM outputs you can defend to finance and leadership. The source\_relation field and dbt docs provide lineage and explainability across the stack.
3.  **Scalability across brands and regions.** The union-across-connections feature makes it straightforward to analyze multi-market portfolios without sacrificing traceability, which is key for central teams supporting many business units.
4.  **Flexibility to match your KPIs.** Model on impressions, spend, or conversions; swap targets (e.g., orders or revenue) with a parameter change; and extend the model with controls or time-varying dynamics as your questions evolve.

## **Who Should Use This?**[#](#who-should-use-this)

-   **In-house data teams** already landing ad + Shopify data via Fivetran and running the official dbt packages.
-   **Analytics consultancies** orchestrating dbt transformations for multiple clients and seeking a standardized way to deliver MMM outputs with uncertainty.
-   **Finance and growth leaders** needing defendable ROAS, channel contributions, and budget recommendations aligned to data governance best practices.

## **Get Started Today**[#](#get-started-today)

**Start here:** Walk through the [**MMM Fivetran Connectors**](https://www.pymc-marketing.io/en/latest/notebooks/mmm/mmm_fivetran_connectors.html) notebook to see the complete workflow and copy/paste starter code.

**Go deeper:** Review what the new [**Fivetran data loaders**](https://github.com/pymc-labs/pymc-marketing/blob/main/pymc_marketing/data/fivetran.py) do in the corresponding PyMC-Marketing pull request.

**Are you new to Fivetran's Ad Reporting?** Check out the package README, especially the section on **unioning** **multiple connections**, to learn about supported platforms, models, and configurations.

---

## **Acknowledgements**[#](#acknowledgements)

This work builds on Fivetran's standardization efforts in the dbt ecosystem and PyMC-Marketing's growing MMM toolkit. We're excited to help teams go from raw connectors to Bayesian decisioning with minimal friction.

## **Further Reading**[#](#further-reading)

-   [PyMC-Marketing](https://www.pymc-marketing.io/en/latest/) overview and MMM guide
-   [MMM API docs and examples](https://github.com/pymc-labs/pymc-marketing/blob/main/pymc_marketing/data/fivetran.py)