# Unveiling Crime Patterns and Insights in Los Angeles

## Project Overview
This Tableau project leverages crime data from Los Angeles (2020-2023) to identify high-crime zones and analyze identity theft trends. By creating visualizations like pie charts, bar charts, and line graphs, the project pinpoints areas with frequent car thefts and reveals a concerning rise in female identity theft cases. These insights can help police allocate resources more effectively and guide cybersecurity strategies.

## Contributors:
Thai Le, Alvia Pham, Essex Glowaki, Kenneth Johnson, McKenna Sloan

## Insight 1
### Of the most prevalent types of crimes committed, where do a majority of them take place?

<img width="479" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/5db0ac6c-d880-4c1b-a78f-f81e51e3bfdf">

#### Importance: 

The specific location of crimes committed is extremely important for police to determine where to allocate their resources. For example, if they assigned the same number of police officers to each area within LA, some communities would be disproportionately patrolled. 

This would leave under-patrolled areas with too many crimes for their officers to respond to, which would result in a slow response rate, an inefficient use of police funds, and an increase in preventable crimes. However, if we can pinpoint the main locations where common crimes take place, these issues could be significantly reduced.

#### Manipulations to dataset: 

We made two main modifications to our dataset:

1. **Categorizing Crime Descriptions**:

The "Crm Cd Desc" column, which describes the type of crime, needed broader classifications. For example, it contained descriptions like "Theft from Motor Vehicle," "Theft from Person," "Theft, Coin Machine," etc. These slight differences were irrelevant to our initial calculation, so we grouped them under broader categories like "Theft" to aggregate similar types of crimes.

2. **Calculating Crime Type Percentages**:

We added a calculated field called "% Crm Cd Desc (group)" to determine the percentage of specific crimes reported, relative to the total cases. This was necessary for creating pie chart visualizations. We calculated this by counting the number of unique IDs for each crime type and dividing that by the total number of unique IDs in the dataset. The formula used was: “COUNT([Dr No]) / TOTAL(COUNT([Dr No]))”


#### Analysis and Results: 

We created four charts to identify the main location of the most common types of crime:

1. **Pie Chart**:
   - This chart showed that theft was the most common crime, accounting for 48.89% of all crimes.
   - Within the "Theft" category, there were various sub-categories to consider.

2. **Bar Chart**:
   - This chart revealed that stolen vehicles were the most common type of theft.

3. **Symbol Map**:
   - This map displayed the locations of vehicle thefts.
   - We found that "77th Street" was the area most prone to vehicle thefts, with "Newton" being a close second.

4. **Pie Chart**:
   - This chart showed that 86.82% of vehicles stolen around "77th Street" and "Newton" were taken from the street (as opposed to other locations like parking decks or driveways).

Finally, we sorted the results by street name. This sorting revealed that the three streets most affected by car thefts were "Broadway," "Central Ave," and "Main Street."

### Insights & Suggestion:
These findings indicate specific streets where police should focus their efforts. For example, "Broadway" has had 83 cars stolen since 2020, whereas "Woodlawn" and "West 84th" each only had 1 car theft in the same period. By allocating more resources to streets like "Broadway," police can respond to reports faster, use their funds more efficiently, and enhance safety for community members in these areas.

## Insight 2
### How have the monthly counts of identity theft incidents between genders changed?

<img width="479" alt="image" src="https://github.com/thai-tran-le/MIST4610-Project-2/assets/148096037/5db0ac6c-d880-4c1b-a78f-f81e51e3bfdf">

#### Importance:

This question compares identity theft incidents affecting different genders over time to identify patterns, trends, or anomalies. The pandemic accelerated the shift to digital services and online financial activities, leading to an increase in scams and data breaches. By analyzing trends specific to different demographics, cybersecurity experts and policymakers can improve online safety protocols and adjust legal frameworks to better support victims. Service providers and financial institutions can also enhance their fraud detection systems to reduce these crimes. This analysis highlights the need for a tailored cybersecurity approach to address the unique challenges faced by different demographics.

#### Manipulations to Dataset:

We made two main modifications to our dataset:

1. **Filtering Outliers**:
   - We excluded the month of November 2023 because it displayed results outside the expected range, likely due to incomplete data for that month.

2. **Adjusting Date Format**:
   - We modified the "Date Occ" column to show discrete values for months and years instead of continuous ones, allowing us to present data more accurately at specific points in time.

#### Analysis and Results:

The graph indicates a significant divergence in identity theft trends between females and males from 2020 to 2023. 

- **Females (Pink Line)**:
  - The trend was relatively stable in 2020.
  - There was a sharp increase in reported identity theft cases beginning in 2021, peaking sharply and then dropping rapidly. This suggests a temporary but intense vulnerability or a series of events that particularly affected females.

- **Males (Blue Line)**:
  - The trend remained relatively flat throughout the same period, indicating a steady rate of identity theft cases without dramatic peaks.

The linear graph is optimal for visualizing this data as it depicts the rate of change, emphasizing the rapid growth of identity theft incidents between the two groups. This is crucial for analysts and decision-makers to understand the magnitude and timing of the events and to investigate potential causes and remedies for the observed disparities.

### Insights & Suggestions:

These findings indicate the importance of targeted cybersecurity measures. For example, the sharp increase in identity theft incidents among females in 2021 suggests a need for specific interventions during that period. By understanding these trends, authorities can allocate resources more effectively, enhance protective measures, and develop targeted awareness campaigns to reduce identity theft incidents across different demographics.

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
