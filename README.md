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

## Data manipulation
To address dataset inconsistencies and missing values, the following steps were implemented:
- Replaced missing values in the ‘Location Description’ column with the existing ‘OTHER’ value. 
- Handled missing location-related data in the ‘X Coordinates, Y Coordinates, Latitude, Longitude, and Location’ columns by grouping records based on ‘Blocks’ and filling blanks with the first non-null value within each group.
- For single-occurrence crime spots with unspecified location details that could not be resolved through grouping, the corresponding records were dropped to maintain data consistency.
- Populated missing data in the ‘Location’ column using formatted data from the corresponding ‘Latitude and Longitude’ columns.
- Identified and removed duplicate records with similar case numbers.
- Dropped the ‘Ward and Community Area’ columns, as they contained more than 60% missing data, making them unsuitable for analysis.

## Data storage in a SQL database
- Established a connection between python and the SQL server.
- Created a table schema (crime_data) within the existing guvi database using Python.
- Imported the cleaned Data Frame into the crime_data table, ensuring seamless data storage for further analysis.
  ![image](https://github.com/user-attachments/assets/bb4991c7-071f-4bc7-acfc-36a8bd8de2d4)

## Power BI dashboard
![image](https://github.com/user-attachments/assets/0a086b5e-27dd-4ebc-871e-98637256e67c) 
- Designed a user-friendly and interactive Power BI dashboard to visualize crime data directly retrieved from the MySQL server, ensuring real-time updates and efficient data representation.
- Displayed key crime metrics using cards highlighting the total reported crimes over the years as 5,47,960 and the count of safer blocks with only one reported crime and a 100% arrest rate as 1294.
- Utilized a funnel chart to identify the top 5 blocks with the highest crime reports as ‘100XX W OHARE ST, 001XX N STATE ST, 035XX S FEDERAL ST, 0000X N STATE ST and 076XX S CICERO AV’ which indicates that the East zone is relatively safe. 
- Tree map showcasing the top 5 most frequently reported crime types as ‘Theft, Battery, Criminal damage, Assault and Narcotics’. The absence of life-threatening crimes like murder among the top reported offenses suggests a positive trend, possibly indicating effective law enforcement efforts in preventing severe crimes. 
- Visualized crime trends over the years using a line chart reveals a crime peak in the year 2001, followed by notable spikes in 2023 and 2024. A significant decline in crime rates between 2002 and 2022, possibly indicating improved community safety and policing efforts. 
- Analyzed crime distribution by time of day with a pie chart, showing the highest crime rates occur between evening and night hours (3 PM to 12 AM). 
- Integrated a real time map to depict crimes hotspots across various blocks in the city, with bubble sizes representing crime density.
- Represented arrest rates by blocks using a column chart identifying 100XX W BALMORAL AVE and 032XX W BELMONT AVE blocks as having the lowest arrest rates, both located in the west zone.
- Created a separate column chart for crime types and arrest rates revealing that the domestic violence cases have a 100% arrest rate, followed by gambling, prostitution, narcotics and liquor law violence. While the non-criminal damage and ritualism related crimes have a 0% arrest rate. 
- Integrated slicers for enhanced interactivity: one to filter data by a range of years and another for toggling domestic crimes (true/false).


