# Chicago-Crime-Analyzer

## Problem Statement
The increasing complexity and volume of crime data present significant challenges for law enforcement agencies and policymakers. Understanding patterns in criminal activities, identifying high-risk locations, and analyzing trends over time are crucial for effective decision-making. However, the lack of accessible insights from raw crime data hinders the ability to allocate resources efficiently, predict future crime occurrences, and enhance community safety. Furthermore, assessing the effectiveness of arrests and understanding the impact of different crime types remain underexplored. This project aims to address these challenges by analyzing the provided dataset to uncover actionable insights and trends, ultimately aiding in crime prevention and fostering safer communities. 

## Objectives
1. Clean and handle missing values to ensure dataset consistency for accurate analysis.
2. Store the processed data in a SQL database and extract at least 10 insights using SELECT queries.
3. Develop an interactive Power BI dashboard analysing the processed crime data.
4. Create 10 diverse charts in Python for comprehensive data visualization. 

## Data Set Explanation
The dataset contains records of reported crimes in Chicago. Each record includes details such as the type of crime, location, arrest status, and other relevant information. The fields in the dataset are as follows:

- ID: Unique identifier for each crime incident.
- Case Number: Unique case number assigned to each incident.
- Date: Date and time when the crime occurred.
- Block: Block where the crime occurred.
- IUCR: Illinois Uniform Crime Reporting code assigned to the crime type.
- Primary Type: Primary classification of the crime.
- Description: Detailed description of the crime.
- Location Description: Description of the location where the crime occurred.
- Arrest: Indicates whether an arrest was made (TRUE/FALSE).
- Domestic: Indicates whether the crime was domestic-related (TRUE/FALSE).
- Beat: Police beat where the crime occurred.
- District: Police district where the crime occurred.
- Ward: Ward where the crime occurred.
- Community Area: Community area where the crime occurred.
- FBI Code: FBI code classification for the crime.
- X Coordinate: X coordinate of the crime location.
- Y Coordinate: Y coordinate of the crime location.
- Year: Year when the crime was reported.
- Updated On: Date when the record was last updated.
- Latitude: Latitude of the crime location.
- Longitude: Longitude of the crime location.
- Location: Combined latitude and longitude in a string format. 

