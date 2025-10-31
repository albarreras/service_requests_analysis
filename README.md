#  NYC 311 Service Requests Analytics (2019–2024)

**Author:** Astrid Barreras  
**Stack:** R, tidycensus, dplyr, mgcv, ggplot2, plotly, flexdashboard, Shiny  
**Last Updated:** October 2025  

---

##  Project Overview

This project analyzes over **18.6 million** NYC 311 service requests (2019–2024) to understand how **volume**, **response times**, and **resolution rates** vary across boroughs—and how these variations are influenced by **socioeconomic factors** and **budget allocations**.

The analysis integrates three major data sources:
- **NYC Open Data – 311 Service Requests**
- **NYC Office of Management & Budget (OMB) Expense Budgets**
- **U.S. Census Bureau – ACS 5-Year Estimates (tidycensus)**

Key methods include:
- Large-scale data cleaning & preprocessing of 10GB+ raw 311 data
- Borough-level aggregation of service outcomes (volume, mean response, resolution rate)
- Integration of ACS socioeconomic variables and OMB budget data
- Linear (LM) and Generalized Additive (GAM) modeling to estimate SES and budget effects
- Interactive visualization via **R Shiny + Flexdashboard**

---

##  Repository Contents

| File | Description |
|------|--------------|
| `Individual Project Report.qmd` | Quarto technical report. Full data processing, modeling, and visualization workflow. |
| `service_requests.pdf` | Rendered report version for easy reading. |
| `SQ4Dashboard.Rmd` | Shiny + Flexdashboard app for interactive borough and model exploration. |
| `data/` | Contains raw and processed datasets (`/raw`). |

---

##  How to Run the Reports

###  View Reports
- **PDF report:** [`311_service_requests.pdf`](311_service_requests.pdf)  
- **Quarto source:** [`311_service_requests.qmd`](311_service_requests.qmd)

###  Run Locally (RStudio)

1. **Clone this repo**
   ```
   git clone https://github.com/albarreras/service_requests_analysis.git
   cd service_requests_analysis

2. Open RStudio
   
4. Run qmd file with CTRL + ALT + R to have the entire markdown file process or individually run each code chunk.


 ## Insights:

###  Volume

- Budgets have positive highly statistically significant linear and nonlinear effects on volume. Given that adopted agency budgets are informed by previous year performance, this could signal that increased demand in previous years drive the need for increases in funding.

- Unemployment has positive highly statistically significant linear effects on volume. This could be due to periods of economic hardship, suggesting that as economic strain rises, so does the demand for reporting public service issues.

### Response Time

- Budgets have positive statistically significant linear and statistically significant nonlinear effects on response times. Given that budgets are also statistically significant with volume, potentially in response to previous year performance, workloads potentially have increased as well, signalling an increase in response times (more workload means less capacity).

### Resolution Rate

- Budgets have negative statistically significant linear effects on resolution rates. This could be that although budgets are increasing, there may be allocation issues corresponding to the ability to resolve service requests.

- Unemployment has positive very statistically significant linear effects on resolution rates. This could be due to the capacity of individuals who file service complaints to engage with the process of resolving their service requests.

- Median income has positive statistically significant linear effects on resolution rates. This could be due to individuals who are more affluent having higher political and social capital leading to higher expectations of service delivery.

- Total population has negative very statistically significant linear effects on resolution rates. This could be due to the growth of demand in service requests outpacing the capacity to address them.


