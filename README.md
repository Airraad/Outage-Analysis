# Outage-Analysis
US Power Grid Outage Analysis & Resource Allocation

Overview

This project analyzes 10 years of US power grid outage data (2014–2023) to identify vulnerabilities and provide data-driven recommendations for infrastructure resource allocation. By calculating the "severity" of each outage (duration × customers affected), we translated raw event logs into actionable business insights for an executive audience.

The Team

Ahmed

Peter

Jacob

Mark

Tech Stack

Environment: Google Colab / Jupyter Notebook

Language: Python 3

Libraries: pandas, numpy, matplotlib.pyplot, plotly.express, re

Data Source

The data is sourced from the Event-Correlated Outage Dataset in America (EAGLE-I).

Files Used: eaglei_outages_with_events_[year].csv and specific hour-lag files (8-hour and 24-hour).

Core Features & Analysis

The main script (Outage_Events.ipynb) contains modular functions to process and visualize the data:

import_data(lag): Concatenates yearly CSVs and allows filtering by specific lag times.

clean_events(eagle_df): Uses regex and dictionary mapping to clean and unify messy "Event Type" inputs (e.g., merging various vandalism types).

severity(eagle, time): Calculates outage severity (duration * mean_customers) and generates bar charts grouped by year or by month for a specific year.

heatmap(severity_df, time): Uses Plotly to generate an interactive US choropleth map highlighting geographic hotspots.

repair_time_barplot(): Calculates and visualizes the mean time to repair (MTTR) for different outage causes.

growth_rate(): Uses scatterplots and trendlines to map the correlation between outage duration and the number of customers affected.

Key Findings

Geographic Hotspots: Texas, Michigan, California, Florida, and New York account for the majority of the nation's outage severity. Texas alone accounted for over 2 Billion lost customer-hours.

The 2021 Anomaly: 2021 saw a massive spike to over 3 Billion lost customer-hours, driven almost entirely by the February winter freeze (Winter Storm Uri).

Primary Drivers: While Severe Weather causes the longest repair times (averaging ~17.3 hours), Vandalism is the second most frequent cause of outages nationwide.

Setup and Usage

Clone the repository.

Download the EAGLE-I dataset CSV files and place them in an Outage_Dataset folder.

Open Outage_Events.ipynb in Google Colab or your local Jupyter environment.

If using Colab, ensure you mount your Google Drive and update the file paths in the import_data function accordingly.

Run the cells sequentially to generate the cleaned dataframe, metrics, and visualization plots.
