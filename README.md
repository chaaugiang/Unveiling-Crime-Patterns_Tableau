# Unveiling Crime Patterns and Insights in Los Angeles

**Tableau · Data Visualization · Geospatial Analysis · Data Storytelling**

An exploratory analysis of **847K+ Los Angeles crime records from 2020 - 2023**, examining where vehicle theft is concentrated and how identity theft patterns differ across victim groups

## Project Overview

Citywide crime totals can hide important differences between neighborhoods, location types, and victim groups. This project analyzes 847K+ reported crime incidents in Los Angeles to turn detailed incident records into visual patterns that can support more focused prevention planning and further investigation

The analysis addresses two questions:

1. **Where are common crimes concentrated, and which locations warrant closer attention?**
2. **How did monthly identity theft reports differ between victims recorded as male and female?**


## Key Findings

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

<img width="600" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/5db0ac6c-d880-4c1b-a78f-f81e51e3bfdf">

### Step 1: Prepare Comparable Crime Categories

The original `Crm Cd Desc` field contained detailed descriptions such as:

- Theft from Motor Vehicle
- Theft from Person
- Theft, Coin Machine

We grouped related descriptions into broader categories such as **Theft**, making it easier to compare the overall distribution before examining individual offenses

We also created a Tableau calculated field to express each category as a percentage of the analyzed records:

```tableau
COUNT([Dr No]) / TOTAL(COUNT([Dr No]))
```

### Step 2: Identify the Largest Crime Category

A pie chart comparing the grouped categories showed that **theft accounted for 48.89%** of analyzed records

This made theft a useful starting point for a more focused analysis

### Step 3: Break Down Theft Offenses

A bar chart compared the individual offenses within the theft category

**Vehicle theft emerged as the most common theft offense**, leading us to investigate where these incidents were occurring

### Step 4: Map Vehicle Theft by LAPD Area

We plotted vehicle-theft incidents on a symbol map and compared their distribution across LAPD areas

The **77th Street area recorded the highest count, followed closely by Newton**
These findings narrowed the analysis from a citywide issue to two areas for closer examination

### Step 5: Examine Premises and Streets

Within the 77th Street and Newton areas, **86.82% of analyzed vehicle thefts occurred on streets**, rather than premises such as parking structures or residential driveways

A street-level breakdown then identified **Broadway, Central Ave, and Main Street** as the streets with the highest vehicle-theft counts

### Why This Matters

The analysis translates a broad crime category into specific areas, premises, and streets for further review

Public safety teams could use these findings to prioritize parking-security assessments, community outreach, and more detailed incident analysis. Rather than distributing resources uniformly across locations, geographic crime patterns can help decision-makers identify areas where targeted patrols, prevention programs, or further investigation may have the greatest impact.


# Analysis 2: Identity Theft Trends by Gender
## How did monthly identity theft reports differ by victim gender between 2020 and 2023?

<img width="530" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/5db0ac6c-d880-4c1b-a78f-f81e51e3bfdf">

### Step 1: Check the Reporting Period

We excluded **November 2023** because the available observations appeared incomplete relative to previous months

Including an incomplete month could create an artificial decline and distort the interpretation of the trend

### Step 2: Organize Dates for Monthly Comparisons

We organized `DATE OCC` into discrete year and month values so incidents could be compared across the analysis period

The monthly counts describe incidents by their recorded occurrence dates, rather than the dates on which they were reported

### Step 3: Compare the Time Series

We created a line chart showing monthly identity theft counts for victims recorded as male and female

- **Female victims, shown in pink:** Counts were relatively stable in 2020, increased sharply beginning in 2021, and later showed a pronounced peak and decline
- **Male victims, shown in blue:** Counts remained comparatively stable, without an increase of the same magnitude

The line chart made the timing, direction, and size of the differences easier to see than an overall total would

### Step 4: Interpret the Difference

The two series showed that recorded identity theft patterns were not uniform across victim groups

The increase involving female victims warrants further investigation, but the visualization does not explain its cause
Additional incident details and information about reporting practices would be needed to understand the pattern

### Why This Matters

Breaking down crime trends by victim group can reveal changes hidden in aggregate totals

These findings could help analysts identify questions for further research and assess whether more targeted identity-theft awareness efforts are appropriate. They do not, by themselves, establish differences in underlying vulnerability or individual risk

## Dataset

**Source:** [Los Angeles Crime Data from 2020 to Present](https://catalog.data.gov/dataset/crime-data-from-2020-to-present)

The project used a historical extract containing **847,726 records and 28 columns**, covering observations from 2020–2023

Each row represents a recorded crime entry
The source is based on LAPD crime reports and is updated over time, so a current download may differ from the extract used in this project

### Fields Used

| Field | Description and analytical use |
|---|---|
| `DR_NO` | Report identifier used to count records |
| `Date Rptd` | Date the incident was reported |
| `DATE OCC` | Date the incident occurred, used for monthly trends |
| `TIME OCC` | Recorded time of occurrence |
| `AREA` / `AREA NAME` | LAPD area code and name, used for geographic comparisons |
| `Crm Cd` / `Crm Cd Desc` | Crime code and description, used to group and compare offenses |
| `Vict Age`, `Vict Sex`, `Vict Descent` | Recorded victim characteristics |
| `Premis Cd` / `Premis Desc` | Premises code and description, used to compare location types |
| `LOCATION` / `Cross Street` | Location information used for street-level analysis |
| `LAT` / `LON` | Coordinates used to map incidents |

Other fields describe weapon use, report status, and additional crime codes

### Original Data Dictionary

<img width="450" alt="Los Angeles crime dataset data dictionary, first section" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/c1e8fef7-4d94-4188-a808-ab894b726c3a">

<img width="450" alt="Los Angeles crime dataset data dictionary, second section" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/6b0b4aad-3cc5-4bdc-aadb-cf24ac5ecef2">

## Tools and Skills

- **Tableau:** dashboards, calculated fields, table calculations, filtering, and interactive visualizations
- **Data preparation:** grouping detailed crime descriptions and checking incomplete periods
- **Geospatial analysis:** comparing incidents across LAPD areas, premises, and streets
- **Trend analysis:** examining monthly identity theft patterns across victim groups
- **Data storytelling:** connecting findings with practical questions and potential prevention priorities

## Limitations

The analysis describes **recorded incidents**, not all crime that occurred
Reporting behavior, missing information, and data quality may influence the observed patterns

Geographic counts are not adjusted for population, parking availability, or other measures of exposure
Similarly, the victim comparisons use the source's recorded sex field and do not establish differences in individual risk

The findings support further investigation and planning
They do not establish causation or demonstrate that a proposed intervention would reduce crime

## Contributors

Thai Le · Alvia Pham · Essex Glowaki · Kenneth Johnson · McKenna Sloan
