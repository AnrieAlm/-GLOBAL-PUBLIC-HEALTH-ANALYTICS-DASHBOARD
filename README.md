# -GLOBAL-PUBLIC-HEALTH-ANALYTICS-DASHBOARD
Global Public Health Analytics Dashboard
A data analytics project exploring COVID-19 data from 243 countries. Built with Python in Google Colab.
What This Project Does
I analysed 402,910 records of COVID-19 data to answer questions like:

    Which countries had the highest death rates?
    How did hospital and ICU numbers change over time?
    What was the global pattern of cases and deaths?
    How do continents compare?

Tools Used
Table
Tool	What I Used It For
Python	Data cleaning and analysis
Pandas	Working with tables and data
Matplotlib	Making charts and graphs
Google Colab	Running everything in the cloud
The Data

    Source: Our World in Data (OWID) COVID-19 dataset
    Records: 402,910 rows
    Countries: 243
    Date range: January 2020 to August 2024
    Fields: Cases, deaths, ICU patients, hospital patients, reproduction rate

What I Did (Step by Step)
1. Cleaned the Data

    Removed duplicate and aggregate rows (like "World" and "European Union")
    Fixed date formats
    Checked for errors (negative numbers, missing values)
    Added useful columns like year, month, and quarter

2. Built a Data Model
I organised the data into three tables:
Table
Table	What It Holds	Rows
DimCountry	Country names, codes, continents, populations	243
DimDate	Dates with year, month, quarter	1,553
FactCovidMetrics	Daily numbers (cases, deaths, ICU, etc.)	402,910
This is called a star schema — a standard way to set up data for analysis.
3. Ran Analysis
I wrote code to calculate:

    Deaths per million people (fair comparison across countries)
    Cases per million people
    Case fatality rate (deaths divided by cases)
    7-day rolling averages (smoothing out daily jumps)
    Peak ICU and hospital numbers

4. Made Charts
I created 7 charts showing:

    Top 10 countries by death rate
    Top 10 countries by infection rate
    Continent comparison
    Global time series (cases, deaths, reproduction rate)
    Case fatality rate rankings
    ICU and hospital trends
    7-day rolling averages

Key Findings
Table
Finding	Detail
Highest death rate	Peru — 6,601 deaths per million people
Highest infection rate	Brunei — 763,599 cases per million
Deadliest continent (average)	Europe — 2,661 deaths per million
Peak global daily cases	~44 million (January 2022, Omicron wave)
Peak global daily deaths	~104,000
Highest case fatality rate	Peru — 4.88%
Files in This Repo
plain

Global_Public_Health_Analytics/
├── data/
│   ├── DimCountry.csv          # Country dimension table
│   ├── DimDate.csv             # Date dimension table
│   ├── FactCovidMetrics.csv    # Main data table
│   └── Cleaned_CovidData.csv   # Full cleaned dataset
├── charts/
│   ├── top10_mortality.png
│   ├── top10_infection.png
│   ├── continent_comparison.png
│   ├── global_time_series.png
│   ├── case_fatality_rate.png
│   ├── healthcare_capacity.png
│   └── rolling_7day_average.png
├── notebook/
│   └── covid_analysis.ipynb    # The full Colab notebook
└── README.md                   # This file

How to Run This Yourself

    Go to Google Colab
    Upload the notebook file
    Upload the owid-covid-data.csv dataset
    Run all cells (Ctrl+F9)
    Outputs save automatically to your Google Drive

What I Learned

    How to clean and prepare real-world data for analysis
    How to build a star schema (dimension and fact tables)
    How to use window functions for rolling averages
    How to normalise data (per-capita metrics for fair comparison)
    How to tell a story with data through clear charts

About Me
I am a data analytics student building projects to show my skills in Python, data cleaning, and visualisation. This project follows the CRISP-DM method: Business Understanding → Data Understanding → Data Preparation → Modelling → Evaluation → Deployment.
