# Detecting Abnormal Energy Spikes and Preventing Energy Waste ⚡

## Table of Contents
- [Project Overview](#project-overview)
- [Business Introduction](#business-introduction)
- [Business Problem](#business-problem)
- [Rationale for the Project](#rationale-for-the-project)
- [Aim of Project](#aim-of-project)
- [Data Sources](#data-sources)
- [Tools Used](#tools-used)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results / Findings](#results--findings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)

---

## Project Overview
This project focuses on detecting abnormal energy usage spikes in households and preventing energy waste using real-time data analytics.  
It leverages smart meter readings and operational data to identify anomalies, provide proactive alerts, and empower both customers and support teams.

**Goal:** Reduce energy waste, improve customer satisfaction, and strengthen **NovaGrid Energy’s** operational efficiency.

---

## Business Introduction
NovaGrid Energy, headquartered in Manchester, UK, is a modern utility provider offering:
- Renewable electricity and gas supply  
- Smart home integration  
- Real-time energy usage dashboards  
- Energy-saving recommendations  

**Key milestones:**
- 1M smart meters deployed in UK households by 2021  
- Launched *GreenSmart Tracker* to monitor real-time carbon intensity  
- Partnered with local councils to support efficient energy usage  

NovaGrid’s core advantage is its **data-first customer experience model**, delivering personalized insights and nudges to reduce costs and carbon footprint.

---

## Business Problem
NovaGrid faced rising customer complaints over high energy bills, often caused by abnormal energy spikes:

- ⚡ **Unexpected Spikes:** Not aligned with typical usage patterns  
- 🔧 **Contributing Factors:** Faulty appliances, behavioral changes, leaking systems  
- ❗ **Impact:** Customer dissatisfaction, higher operational costs, reputational risk, and energy waste  

A proactive alert system was required to detect anomalies, inform users, and minimize waste.

---

## Rationale for the Project
Reasons to implement this initiative:
- **Customer Trust:** Reduce billing disputes and increase transparency  
- **Proactive Support:** Shift from reactive to predictive energy management  
- **Sustainability:** Identify and reduce unnecessary energy consumption  
- **Operational Savings:** Reduce inbound queries and manual investigations  
- **Competitive Advantage:** Position NovaGrid as a tech-driven, customer-focused utility  

---

## Aim of Project
Primary objectives:
- Detect real-time abnormal energy spikes per household  
- Classify spike types: appliance-related, behavioral, infrastructure-driven  
- Send proactive alerts and usage recommendations  
- Reduce unnecessary energy consumption  
- Enhance Tableau dashboards for operations and customer monitoring  

---

## Data Sources
Data was sourced from:
- **Google Sheets:** Smart meter readings and household energy usage  
- **Customer Data:** Region, housing type, historical usage patterns  
- **Spike Alerts:** Records of detected spikes, alerts sent, and resolutions  

**Key variables:**
- Household ID, Region, Housing Type  
- Energy Usage (kW), Spike Flag  
- Alert Sent (Yes/No), Resolution Status (Resolved/Unresolved)  
- Timestamp of spike occurrence  

---

## Tools Used
- **Google Sheets:** Data collection and raw storage  
- **Tableau:** Data visualization, anomaly tracking, and operational dashboards  

---

## Data Cleaning & Preparation
Steps performed:
- Data validation for missing or inconsistent energy readings  
- Standardized timestamps and unit measurements (kW)  
- Classified spike events and added calculated fields for resolution metrics  
- Aggregated household data by region, housing type, and day-of-week  

---

## Exploratory Data Analysis
Key questions explored:
- Which households and regions exhibit the most spikes?  
- What are the most common spike causes?  
- How do spikes correlate with housing type and energy consumption?  
- Are spikes more frequent on weekdays vs weekends?  

**Visualizations included:**
- Heatmaps by region and housing type  
- Time series of energy usage vs baseline  
- Pie charts for spike distribution by housing type  

---

## Data Analysis
Example SQL query:

```sql
SELECT Region, HousingType, COUNT(SpikeFlag) AS SpikeCount
FROM Smartmeter_data
WHERE SpikeFlag = 'Yes'
GROUP BY Region, HousingType
ORDER BY SpikeCount DESC;
```
### Calculated metrics:

- Spike counts per region and housing type

- Resolution rates (%)

- Correlation between total usage and spike frequency

## Results / Findings

**Energy Usage Dashboard:**  
![Energy Usage Dashboard](https://github.com/WittyJerry/Detecting-Abnormal-Energy-Spikes-and-Preventing-Energy-Waste/blob/main/Dashboard%202.png)

**Energy Spike Dashboard:** 
![Energy spike Dashboard](https://github.com/WittyJerry/Detecting-Abnormal-Energy-Spikes-and-Preventing-Energy-Waste/blob/main/Dashboard%201.png)
<details> <summary>📌 Spike Detection & Resolution</summary>

- 114 abnormal spikes detected

- 111 proactive alerts sent

- 77 resolved (~69.4% resolution rate)

</details>

<details> <summary>📊 Regional Insights</summary>

- High spikes in London, Manchester, Glasgow

- Lower activity in Bristol and Reading

</details>

<details> <summary>🏠 Housing Type</summary>

- Semi-Detached: 40.35% of spikes

- Detached: 31.58%

- Flats: 28.07%

</details>

<details> <summary>📈 Time Patterns</summary>

- Weekday spikes: 89

- Weekend spikes: 26

- Detached homes consume most energy (avg 1.61 kW)

</details>

## Recommendations

- ⚡ Prioritize alerts for semi-detached homes and high-spike regions

- 📅 Deploy weekday-focused alerts for high-energy households

- 🏠 Use baseline comparisons to educate customers on abnormal usage

- 📊 Enhance anomaly detection models with housing type, day-of-week, and usage patterns

- 💡 Provide actionable energy-saving tips via dashboards or notifications

</details>

## Limitations
- Dataset limited to smart meter readings and historical household usage

- External factors (weather, holidays, appliance malfunctions) not fully captured

- Spike classification may be imperfect due to behavioral complexity

- Resolution metric only reflects detected and reported spikes

## References
- Tableau Documentation

- Google Sheets Data Management Guides

- Energy analytics best practices

- UK Smart Meter Program Reports
