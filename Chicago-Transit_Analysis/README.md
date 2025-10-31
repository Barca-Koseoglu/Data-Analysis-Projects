# Chicago Transit Authority (CTA) Rail Ridership Analysis

<img width="1778" height="1002" alt="image" src="https://github.com/user-attachments/assets/4866599e-61ff-4a21-b890-9fe692ad43be" />

## Project Overview

This file contains the raw Chicago Transit Authority (CTA) rail ridership data and a comprehensive analysis focusing on the long-term impact of the COVID-19 pandemic and the subsequent recovery. The analysis is presented via an interactive Power BI dashboard (`CTA_Ridership_Dashboard.pbix`).

### Key Analytical Findings

The report synthesizes ridership volatility into three distinct performance phases:

#### 1. The Disruption Phase: 2020 Collapse

The most significant finding is the immediate and drastic reduction in system volume following March 2020.
* **Metric:** System-wide ridership registered a **-65.19%** drop when comparing the latest pre-pandemic baseline to the 2020 low point, establishing the severity of the initial shock to the network.

#### 2. The Resilience Phase: Uniformity of Decline

A detailed analysis of individual rail line performance demonstrates that the decline in ridership was remarkably proportional across the entire network.
* **Insight:** The analysis of **Shift in Line Ridership Share** shows that the **relative market share** of most lines shifted by less than $\pm 0.5$ percentage points. This indicates that the core, remaining ridership base was uniformly reliant on the entire system’s infrastructure.
* **Observation:** The **Red** and **Blue** lines recorded the largest absolute negative shift in share, suggesting that non-essential travel was concentrated in the highest-density urban routes.

#### 3. The Recovery Phase: Post-2020 Rebound

Following the nadir of 2020, the system has demonstrated a strong rebound toward pre-pandemic volumes.
* **Metric:** The CTA system recorded a **+73.59%** recovery in total annual rides when comparing the 2020 low point to the ridership volumes recorded in the latest full year of data (2024).

---

## Data Sources and Structure

### Source 
* **Original Provider:** Chicago Transit Authority (CTA) via the City of Chicago Open Data Portal.
* **Time Period Covered:** 2001 through 2024 (Although there was 2025 data, I didn't inlude it in the calculations due to the fact that there were abstract trends.)
* **Links (since the files are too large to upload here):** [CTA Ridership: L Station Entries - Daily Totals](https://data.cityofchicago.org/Transportation/CTA-Ridership-L-Station-Entries-Daily-Totals/5neh-572f/about_data), [CTA System Information: List of 'L' Stops](https://data.cityofchicago.org/Transportation/CTA-System-Information-List-of-L-Stops/8pix-ypme/about_data)

### Data Model and Files
The analysis utilizes two tables connected via a one-to-many relationship (`stations[station_id]` to `ridership[station_id]`):

* **`ridership` Table:** Contains the core metrics and time data.
    * `date`: The date of the ride count.
    * `rides`: The total number of rides recorded for the day.
    * `station_id`: Key used to link to the geometry table.
* **`stations` Table:** Contains geographical and categorical metadata.
    * `line`: The specific CTA train line (Red, Blue, Brown, etc.).
    * `latitude`/`longitude`: Coordinates for mapping.

### Files in this Repository
* `CTA_Ridership_Dashboard.pbix`: The Power BI project file containing the data model, DAX measures, Power Query transformations, and final visualizations.

---

## 🛠️ Technical Requirements

To view and interact with the full data model and report:
* **Software:** Microsoft Power BI Desktop (Free download).

***

*Analysis performed by Barca Koseoglu as a data science portfolio project.*
