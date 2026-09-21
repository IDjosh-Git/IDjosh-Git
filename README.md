<div align="center">
  <!-- Typing SVG Banner -->
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=2E9EF7&center=true&vCenter=true&width=500&lines=Data+Analyst+%7C+Power+BI+Developer;SVG+DAX+Engineer+%26+Dashboard+Architect;Semantic+Modeling+%7C+Power+Query+M;Community+Builder+%40+Zen+Analytics+Hub" alt="Typing SVG" />

  <p align="center">
    <a href="https://github.com/IDjosh-Git"><img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github" alt="GitHub"></a>
    <a href="https://linkedin.com/in/idowu-joshua-data"><img src="https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin" alt="LinkedIn"></a>
    <a href="https://mail.google.com/mail/?view=cm&fs=1&to=Esoterikjoshua@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-green?style=for-the-badge&logo=gmail" alt="Email"></a>
  </p>
</div>

---

## 🚀 About Me

I am a **Data Analyst, Power BI Developer, and Analytics Engineer** based in Nigeria, co-leading community upskilling initiatives at **Zen Analytics Hub Ltd**. 

My work centers on bridging raw data with strategic decision-making. I specialize in designing scalable star-schema semantic models, crafting bespoke SVG visual measures in DAX, optimizing Power Query (M) transformations, and delivering executive dashboards tailored for client adoption across diverse domains.

At **Zen Analytics Hub**, I actively facilitate hands-on bootcamps, workshops, and mentoring programs aimed at helping aspiring data professionals transition into production-ready roles.

> *I love the moment a messy dataset turns into a dashboard someone actually uses every day — that's the whole job, really.*

🏆 **[Explore My Live Portfolio & Case Studies](#)** *(https://idjoshportflio.vercel.app/)*

---

## 🛠️ Technical Capabilities & Stack

### Business Intelligence & Analytics Engineering
* **Data Modeling:** Star-schema architecture, TMDL measure management, incremental refresh strategies, granular RLS/OLS security implementation, and performance tuning via Tabular Editor.
* **SVG DAX Engineering:** Hand-crafting dynamic SVG visual measures (progress bars, inline KPI cards, sparklines, custom icons, and theme-adaptive UI badges) directly within DAX calculations.
* **ETL & Data Wrangling:** Complex data extraction, parameterization, and automated directory ingestion using Power Query (M Code), openpyxl, and pandas.
* **Dashboard UX/UI:** User-centered layout design, customized navigation flows, custom JSON theme palettes, dark/light mode toggles, and dynamic bookmarking.

### Skillset Overview

| Category | Core Skills & Technologies |
| :--- | :--- |
| **Business Intelligence** | Power BI Desktop & Service, DAX, Power Query (M), TMDL, Tabular Editor, Excel |
| **Languages & Scripts** | SQL, SVG (XML), HTML/CSS Visuals |
| **Architecture & Ops** | Star-Schema Modeling, Data Governance, Power Automate, Git/GitHub Version Control |
| **Community Leadership** | Curriculum Development, Bootcamp Facilitation, Technical Mentorship |

---

## 💼 Featured Projects & Case Studies

### 🛒 [Spark Pixel E-Commerce Analytics](#)
> *End-to-end e-commerce order management and fulfillment dashboard with custom SVG interface integration.*
* **Architecture:** Enterprise star-schema model separating facts (Orders, Order Lines) from dimensions (Customers, Products, Geography, Dates).
* **Highlights:** Native theme-switching engine, dynamic SVG navigation menus, and inline order status KPI cards engineered via SVG DAX measures.

### 🚚 [DM Logistics Carrier Performance Report](#)
> *Executive-level logistics dashboard monitoring carrier SLAs, delivery turnaround times, and fleet efficiencies.*
* **Architecture:** TMDL-driven measure organization built with modular DAX logic for rapid deployment.
* **Highlights:** Dynamic SVG icon set representing shipment statuses and custom carrier scorecard tables.

### 🚗 [Transportation & EV Mobility Analytics](#)
> *Strategic mobility report analyzing travel patterns, route delays, weather correlations, and EV charging equity.*
* **Architecture:** Multi-fact data engine integrating environmental scenarios with transportation metrics.
* **Highlights:** Spatial equity mapping, delay root-cause decomposition, and executive narrative summaries.

### 📊 [Enterprise Sales Analytics Model](#)
> *Two-page executive report powered by a robust core data model (`Fact_Sales`, `Dim_Products`, `Dim_Customers`, `Dim_Regions`).*
* **Architecture:** Optimized star schema supporting time-intelligence calculations (YTD, YoY, Moving Averages).
* **Highlights:** Product profitability matrix, regional performance rankings, and automated anomaly alerts.

---

## 🎨 Sample SVG DAX Showcase

Here is an example of an SVG measure I engineer to render custom, data-driven KPI progress indicators directly inside Power BI matrix tables without external visuals:

```dax
// Dynamic SVG KPI Progress Bar Measure
SVG_ProgressBar = 
VAR TargetValue = [Target Sales]
VAR ActualValue = [Total Sales]
VAR Percentage = DIVIDE(ActualValue, TargetValue, 0)
VAR ClampedPct = MIN(MAX(Percentage, 0), 1)
VAR BarWidth = INT(ClampedPct * 100)
VAR FillColor = IF(Percentage >= 1, "%23217346", "%23E66C37") // Green if goal met, else Orange

RETURN
"data:image/svg+xml;utf8," &
"<svg xmlns='[http://www.w3.org/2000/svg](http://www.w3.org/2000/svg)' width='120' height='18' viewBox='0 0 120 18'>" &
"  <rect x='0' y='3' width='100' height='12' rx='6' fill='%23E0E0E0'/>" &
"  <rect x='0' y='3' width='" & BarWidth & "' height='12' rx='6' fill='" & FillColor & "'/>" &
"  <text x='105' y='13' font-family='Arial' font-size='10' fill='%23333333'>" & FORMAT(Percentage, "0%") & "</text>" &
"</svg>"
