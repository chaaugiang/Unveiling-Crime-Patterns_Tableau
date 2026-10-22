# Unveiling Crime Patterns and Insights in Los Angeles

**Tableau · Data Visualization · Geospatial Analysis · Data Storytelling**

An exploratory analysis of **847K+ Los Angeles crime records from 2020–2023**, examining where vehicle theft is concentrated and how identity theft patterns differ across victim groups

## Project Overview

Citywide crime totals can hide important differences between neighborhoods, location types, and victim groups. This project analyzes 847K+ reported crime incidents in Los Angeles to turn detailed incident records into visual patterns that can support more focused prevention planning and further investigation

The analysis addresses two questions:

1. **Where are common crimes concentrated, and which locations warrant closer attention?**
2. **How did monthly identity theft reports differ between victims recorded as male and female?**

## Tools & Skills
Tableau - dashboards, calculated fields, filtering, and interactive visualizations
Data Cleaning & Transformation - grouped detailed crime descriptions into broader analytical categories
Geospatial Analysis - mapped crime incidents by LAPD area and location
Trend Analysis - analyzed monthly identity theft patterns from 2020 - 2023
Data Storytelling - translated visual findings into operational recommendations

## Key Findings
Theft accounted for 48.89% of reported crimes in the analyzed data.
Vehicle theft was the most common theft category.
The 77th Street and Newton LAPD areas showed particularly high concentrations of vehicle theft.
86.82% of vehicle thefts analyzed within these two areas occurred on streets rather than locations such as parking structures or driveways.
Broadway, Central Ave, and Main Street emerged as the streets with the highest vehicle-theft counts in the analysis.
Identity theft reports showed different patterns across victim genders, including a pronounced increase among female victims beginning in 2021.

| Finding | What it means for decision makers |
|---|---|
| **Theft represented 48.89%** of analyzed crime records | Theft is a substantial part of the reported crime workload and a useful starting point for deeper analysis |
| **Vehicle theft was the largest theft category**, with high counts in the **77th Street and Newton LAPD areas** | These areas are candidates for closer review of vehicle-theft prevention needs |
| **86.82% of vehicle thefts within those two areas occurred on streets** | Prevention efforts could focus on street parking conditions, resident awareness, and specific locations |
| **Broadway, Central Ave, and Main Street** had the highest vehicle theft counts in the street-level analysis | Street level findings help narrow broad geographic priorities into locations for further assessment |
| Identity theft reports involving **female victims rose sharply beginning in 2021**, while male victim reports were comparatively stable | Demographic breakdowns can reveal changes that aggregate crime totals may obscure |

These findings identify **where to investigate and what to examine next**. They do not establish causes or demonstrate that a particular intervention would reduce crime

# Analysis 1: Geographic Patterns in High-Frequency Crime
## Of the most prevalent types of crime, where do the majority of incidents occur?

<img width="530" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/5db0ac6c-d880-4c1b-a78f-f81e51e3bfdf">

## Data Preparation

To support the analysis, we performed two primary transformations.

### Crime Category Grouping

The original Crm Cd Desc field contained highly specific crime descriptions such as:

Theft from Motor Vehicle
Theft from Person
Theft, Coin Machine

We grouped related descriptions into broader categories such as Theft, allowing similar offenses to be analyzed together.

### Crime Percentage Calculation

A Tableau calculated field was created to measure each crime category as a percentage of total reported incidents:

COUNT([Dr No]) / TOTAL(COUNT([Dr No]))

## Analysis

We built a sequence of Tableau visualizations to progressively narrow the analysis from overall crime patterns to specific high-risk locations.

### 1. Crime Distribution

A pie chart comparing major crime categories showed that theft represented 48.89% of reported crimes, making it the largest category in the analysis.

### 2. Theft Breakdown

A bar chart was then used to examine individual theft categories. Vehicle theft emerged as the most common type of theft.

### 3. Geographic Distribution

Vehicle theft incidents were plotted geographically using a symbol map. The 77th Street LAPD area recorded the highest concentration, followed closely by Newton.

### 4. Location Analysis

Within these two areas, 86.82% of analyzed vehicle thefts occurred on streets, rather than other location types such as parking structures or residential driveways.

Further analysis at the street level identified Broadway, Central Ave, and Main Street as the streets with the highest vehicle-theft counts.

## Takeaway

The results demonstrate how crime data can be analyzed at increasingly granular geographic levels—from citywide crime categories to LAPD areas and individual streets.

Rather than distributing resources uniformly across locations, geographic crime patterns can help decision-makers identify areas where targeted patrols, prevention programs, or further investigation may have the greatest impact.



# Analysis 2: Identity Theft Trends by Gender
## How did monthly identity theft reports differ by victim gender between 2020 and 2023?

<img width="530" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/5db0ac6c-d880-4c1b-a78f-f81e51e3bfdf">

## Data Preparation

Two adjustments were made before visualization:

### Incomplete Period Filtering

November 2023 was excluded because the available observations appeared incomplete relative to previous months and could distort the time-series analysis.

### Date Transformation

The DATE OCC field was transformed into discrete month and year values to support month-over-month comparisons.

## Analysis

A time-series visualization was created to compare reported identity theft incidents among male and female victims.

The analysis revealed a noticeable divergence between the two groups:

Identity theft reports involving female victims increased sharply beginning in 2021, followed by a substantial peak and subsequent decline.
Reports involving male victims remained comparatively stable, without an increase of the same magnitude.

A line chart was used to highlight the timing, direction, and magnitude of these changes across the analysis period.

- **Females (Pink Line)**:
  - The trend was relatively stable in 2020.
  - There was a sharp increase in reported identity theft cases beginning in 2021, peaking sharply and then dropping rapidly. This suggests a temporary but intense vulnerability or a series of events that particularly affected females.

- **Males (Blue Line)**:
  - The trend remained relatively flat throughout the same period, indicating a steady rate of identity theft cases without dramatic peaks.

The linear graph is optimal for visualizing this data as it depicts the rate of change, emphasizing the rapid growth of identity theft incidents between the two groups. This is crucial for analysts and decision-makers to understand the magnitude and timing of the events and to investigate potential causes and remedies for the observed disparities.

## Takeaway

The results suggest that identity theft trends were not uniform across victim demographics during the analyzed period.

The sharp change in reports involving female victims warrants deeper investigation into potential contributing factors. Additional demographic, financial, or incident-level data would be necessary to determine the underlying causes.

From an analytical perspective, segmenting cyber-enabled crime trends by demographic characteristics can help organizations identify patterns that may be obscured when examining aggregate incident counts alone.

## Dataset Description
The dataset is sourced from incidents of crime in the City of Los Angeles dating back to 2020. The data is transcribed from original crime reports that are typed on paper.There are 847726 columns and 28 rows.

This dataset contains a range of information, each row represents a unique crime event. In this  dataset, the 'DR_NO' column is of integer data type, representing the report number for each crime incident. The 'Date Rptd,' 'DATE OCC' columns are of date/time data types, capturing the reporting date, date of occurrence, and 'TIME OCC' in integer to represent the number of occurrences of the crime. Geographic details are captured through 'AREA' (integer) and 'AREA NAME (string) representing the numeric code and name of the geographic area. Other columns include 'Crm Cd' (integer) and 'Crm Cd Desc' (string) providing a numeric code and description for the type of crime, and 'Vict Age,' (string) 'Vict Sex,' and 'Vict Descent,' both in integer describing the victim's age, gender, and descent. 

“Premis Cd” (integer) and “Premis Desc” (string) describe the numeric code and name of the crime location type (condo, police station, etc). Various codes and descriptions are provided for weapon use, and the status of the crime report, such as “Weapon Used Cd” (integer), “Status” (string), “Status Desc” (string); and “Crm Cd 1”, “Crm Cd 2”, “Crm Cd 3”, “Crm Cd 4” all in integers. Crime address is described specifically with “LOCATION” and “Cross Street” both in strings. Additionally, 'LAT' and 'LON' columns both in floats offer precise latitude and longitude coordinates for each crime incident. 

## Data Dictionary
<img width="381" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/c1e8fef7-4d94-4188-a808-ab894b726c3a">
<img width="380" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/6b0b4aad-3cc5-4bdc-aadb-cf24ac5ecef2">


## Dataset Used
https://catalog.data.gov/dataset/crime-data-from-2020-to-present

<img width="473" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/3cb655b0-a0d1-4b60-a075-f4f8a866ab53">


## Contributors:
Thai Le, Alvia Pham, Essex Glowaki, Kenneth Johnson, McKenna Sloan
