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

## 10 Insights using SELECT queries
### 1.  Top 5 most reported crimes at nights
![image](https://github.com/user-attachments/assets/e2c17b26-cc5f-4f37-aff3-5e5d540bc3f7)
- The most frequently reported crimes during night time are Battery, theft, criminal damage and narcotics. 
- This highlights the critical need for enhanced night patrolling to ensure the safety of individuals traveling at night.

### 2.  Top 3 districts with highest murder crimes
![image](https://github.com/user-attachments/assets/8b17cc9d-85ae-431e-aa61-edb2ff4c9336)
- The districts with the highest murder rates, have been identified as 11,7 and 6. 
- Measures aimed at reducing weapon circulation and raising awareness about emergency helplines are effective strategies for enhancing community safety and to ensuring prompt rescue services.

### 3.  Distribution of crime across zones
![image](https://github.com/user-attachments/assets/5fc67e41-91ca-4a91-93f1-3172acd76817)
- The analysis reveals that most crimes occur in the South Zone while the East zone seems relatively safe with lowest crimes. 
- High-crime areas require targeted interventions and strategic planning by officials to enhance safety and significantly reduce crime incidents.


### 4.	Distribution of crime on December nights across zones
![image](https://github.com/user-attachments/assets/3abd084e-62fc-4a7d-b261-8d5addd30c67)
- Crime incidents on freezing December nights further expose security vulnerabilities in the South Zone. 
- This trend suggests potential gaps in security measures, especially during adverse weather conditions that may slow down patrolling and emergency response times. 
- Strengthening security personnel with proper training and resources to operate efficiently in harsh weather is crucial to maintain consistent vigilance and public safety.

### 5.	Human trafficking cases reported in East zone 
![image](https://github.com/user-attachments/assets/00d212d7-2e1d-4214-becd-7b868d04d4b1)
- The unresolved human trafficking cases reported in the East Zone, where no arrests have been made even two years after being reported, serve as a stark reminder of the need for urgent action. 
- This situation underscores critical shortcomings in tracking and apprehending offenders involved in such heinous crimes.


### 6.	The only arrested case reported on 2024 new year in North zone
![image](https://github.com/user-attachments/assets/38b340f9-1f4a-4eb8-8289-6550069ed48a)
- On New Year's Eve 2024, the only reported arrest was related to narcotics. 
- However, the data lacks precise information about the crime spot, which is a critical detail for effectively curbing narcotics supply, particularly among teenagers. Ensuring detailed documentation and targeted measures are vital to mitigate the narcotics threat and protect vulnerable groups.


### 7.	Crime Incident in District 31 (Block Code: 0000X)
![image](https://github.com/user-attachments/assets/6dfef3e0-3f59-4097-a3ec-f047140a4d77)
- Cases reported in District 31, specifically in block 0000X, involved theft and battery occurring at the Airport Terminal. 
- The swift action taken by authorities led to the arrest of the offenders within days, highlighting the effectiveness of the safety measures and surveillance systems in place at the location. 
- Such efficiency serves as a model for other high-crime-prone areas, emphasizing the importance of technology and vigilance in ensuring public safety.


### 8.	Domestic violence case reported in the city
![image](https://github.com/user-attachments/assets/2024881e-7186-4ead-b1d5-8b9396c6ee13)
- The only reported case of domestic violence in the city, which occurred in 2001, presents two possible interpretations: either domestic violence is being effectively controlled, or such incidents are significantly underreported.
- Conducting an anonymous, women-centric social survey could provide deeper insights into the actual prevalence of such cases.

### 9.	Location with highest narcotics-related crimes
![image](https://github.com/user-attachments/assets/09e7b18a-1249-454e-8312-3a4df9431e4d)
- A district in the South zone has been identified as the hotspot for narcotics-related crimes. 
- To effectively tackle this issue, conducting an age-specific survey can help identify the most vulnerable demographics, particularly teenagers. 
- Additionally, implementing targeted awareness programs, rehabilitation initiatives, and stricter enforcement can further aid in curbing drug-related crimes.

### 10.  Kidnapping case in district-1
![image](https://github.com/user-attachments/assets/ebb44337-e800-4e22-b2ac-f5d86b859c91)

- Kidnapping incidents reported in the district ‘1’ remain unresolved, as the offenders have not been apprehended by officials. 
- This raises serious concerns about the safety and security of residents in the region. Deploying specialized task forces to prioritize and expedite the resolution of kidnapping cases, coupled with enhanced surveillance in these regions, is essential to reducing such crimes.

## Data visualizations in Python
### 1.	Crime distribution Insights from a box plot
![image](https://github.com/user-attachments/assets/850cc6a4-0af2-496c-9826-0182f228d6b4)
- The box plot analysis reveals significant crime disparities across districts, with one outlier district reporting as few as 10 incidents, while the minimum crime count among other districts exceeds 10,000. 
- The highest crime rate recorded in a single district reaches approximately 35,000 incidents.
- This uneven crime distribution underscores the need for area-specific approach and policing strategies.

### 2.	Crime distribution across top 40 blocks  
![image](https://github.com/user-attachments/assets/2521f8b6-06ed-4584-8017-1e5ee0483552)
- A bar chart visualizing the top 40 high-crime blocks reveals that only five blocks report crime incidents exceeding 500, while the remaining blocks have fewer than 500 incidents. 
- This stark contrast highlights the need for targeted crime prevention measures in these five high-crime blocks.

### 3.	Overall arrest rates 
![image](https://github.com/user-attachments/assets/58e3e4a1-90cf-4446-99e1-a4b67db8d386)
- The pie chart reveals that the overall arrest rate in the city stands at only 23.7%, which is significantly low.
- This suggests a significant gap in law enforcement effectiveness, pointing to the need for more efficient strategies to identify and apprehend offenders. 

### 4.	Arrest rates over the years
![image](https://github.com/user-attachments/assets/4a3366fa-53a5-4758-8fdd-4cb7b3b02a14)
- This bar graph displays crimes reported and corresponding arrests over the years, excluding 2001, 2023, and 2024, which had extremely high case numbers to enhance visualization.
- The data indicates that 2011 had the lowest crime rate, and the total incidents staying below 1,000 between 2002 and 2015.
- Notably, the arrest rate remained consistently low throughout the years, highlighting a concerning trend that requires attention through official meetings and crime record analysis.

### 5.	Domestic crime rates
![image](https://github.com/user-attachments/assets/8e652aa9-e870-4289-8390-2e816440b0cc)
- The column chart illustrates that domestic crime cases in the city amount to around 1 lakh, while non-domestic crime cases significantly outnumber this, with approximately 4 lakh cases.
- This stark disparity indicates that non-domestic crimes are a major concern in the city, accounting for a far greater proportion of criminal activity.
- Measures focused on controlling non-domestic crimes are crucial for enhancing community safety.

### 6.	FBI crime incidents and arrest rates
![image](https://github.com/user-attachments/assets/d84b2b77-3237-4384-b503-63dd836d573a)
- This heatmap displays the total number of cases for each respective FBI code along with their corresponding arrest counts which remain consistently low across all incidents.
- A single crime and corresponding arrest are reported under FBI Code 27, while the highest arrest rates are observed in FBI Codes 19, 18, and 16.
- FBI Code 6 records the highest number of incidents, with approximately 100,000 reported crimes, yet only 13,000 arrests—indicating a notably low arrest rate.
- This underscores the urgent need for a more targeted approach in identifying offenders based on the severity of crimes associated with each code. 

### 7.	Crime distribution across beats
![image](https://github.com/user-attachments/assets/f39896a9-3521-45d0-aae5-2ae0e63d94ce)
- The scatter plot highlights significant variations in crime incidents across beats, with some areas reporting high cases while others have almost none.
- High-crime beats can adopt strategies from low-crime areas to enhance crime prevention, while resource allocation should prioritize high-crime zones for better enforcement.
- Analyzing low-crime beats can offer valuable insights into effective crime reduction measures for broader implementation.

### 8.	Homicide over the years
![image](https://github.com/user-attachments/assets/441a8005-086d-4b45-bdd5-ddaa98ab4972)
- The homicide crime trend has shown a notable decline in recent years, even as overall crime rates remain high. 
- Homicide cases dropped below 200 in 2024, indicates successful crime control measures targeting homicides. 
- The peak in 2021 warrants further analysis to understand the underlying motives and weapons used, offering valuable insights for strengthening crime prevention and public safety measures.

### 9.	Crime involving children across districts
![image](https://github.com/user-attachments/assets/ec42822e-a41c-4198-9ee5-d6f9deab3375)
- Crime incidents ranging between 30 to 200 across districts and above 50% of total crimes in several districts indicate that no district is completely safe for children, which is a serious concern. 
- Data on total crimes and child related incidents across districts show that District 8 has the highest number of cases (above 200), while District 20 has the lowest (below 50).
- This highlights the urgent need for child-specific policies and regulations to enhance the city's safety for children.

### 10. Histogram of crime distribution across districts
![image](https://github.com/user-attachments/assets/a3b8eca1-b7e8-404f-9f17-a51afd2a1184)
- A histogram analysis reveals that over 35,000 crimes occurred in two districts, while 30,000 crimes were recorded in five districts. 
- In contrast, one district reported only around 10 cases and the remaining districts experienced crime incidents ranging between 10,000 and 30,000. 
- This data can assist officials in identifying crime-prone districts and formulating targeted strategies to reduce crime rates effectively.

## Recommendations to reduce crimes and enhance public safety
-	Strengthen night patrolling to ensure safety, especially for late-night travellers and implement area-specific policing strategies based on crime distribution data.
-	Target high-crime areas with strategic planning and interventions while improving offender tracking and apprehension to address gaps in law enforcement.
-	Limit weapon circulation and increase public awareness of emergency helplines, alongside conducting anonymous social surveys to better understand gender-based crimes.
-	Enforce child-specific policies to protect vulnerable groups and introduce rehabilitation programs and stricter enforcement to combat drug-related offenses.
-	Leverage surveillance systems and data-driven crime analysis to enhance response times and crime prevention strategies.
-	Regularly review and assess regulations and measures implemented to mitigate crime, evaluating their effectiveness to refine strategies and adapt as needed.


