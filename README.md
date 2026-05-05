# MIST-4600-Group-Project-2 Group 1
UGA MIST 4610 Spring 2026 Group Project Repository

TEAM MEMBERS:
1. Andrew Yancey, - https://github.com/AndyY-64
2. Kristina Lam, - https://github.com/sybiesuga
3. Bryan Yang, - https://github.com/BryanYangUGA
4. Shivani Menon, - https://github.com/shivanimenon
5. Andrew Pruitt, - https://github.com/andrewpruitt033

Dataset and Information:

Source: DC Crime Incidents 2025 — obtained from the U.S. Data.gov open data catalog, published by the District of Columbia Metropolitan Police Department (MPD).
Dimensions: 24,151 rows × 25 columns
Date Range: January 1, 2025 – January 1, 2026

The dataset captures every reported crime incident across all 8 wards of Washington D.C. for the full year 2025. Offense types range from property crimes (theft, burglary, motor vehicle theft) to violent crimes (robbery, assault, homicide, sex abuse, arson). 

CCN: Criminal Complaint Number a unique identifier assigned to each reported incident.

OFFENSE: The type of crime reported (e.g., THEFT/OTHER, ROBBERY, HOMICIDE, ASSAULT W/DANGEROUS WEAPON).

WARD: The ward number (1–8) indicating which district of D.C. the incident occurred in.

METHOD: The method or weapon involved in the offense (e.g., GUN, KNIFE, OTHERS).

SHIFT: The police shift during which the incident was reported (DAY, EVENING, or MIDNIGHT).

REPORT_DAT: The date and time the incident was reported.

BLOCK: The block-level location where the incident occurred.

LATITUDE / LONGITUDE: Geographic coordinates of the incident.

Two Questions:

- How does crime type distribution vary across D.C.'s 8 wards, and which wards face the highest burden of violent vs. property crime?

- How do Ward 3 and Ward 8 differ in the types of offenses committed, and what socioeconomic factors explain those differences?


Why it's important: 

Washington D.C. is divided into 8 wards with significant differences in demographics, income levels, and population density. There are significant social and policy implications to understanding how the distribution of the type of crimes across the 8 wards has. This information can help individuals make informed decisions regarding the safety of the community and also help the Metropolitan Police Department and city officals distribute resources and officers more efficiently. The difference between violent crimes (robbery, assult, homicide) and property crimes (theft, burglary) between wards indicates if there are systematic injustices that are related to the more general economic and social factors. 

<img width="1506" height="942" alt="Screenshot 2026-05-04 at 9 52 15 PM" src="https://github.com/user-attachments/assets/e506d819-2298-4a3e-a114-aa260142e544" />

Ward 3 and Ward 8: Comparing Time of Day to Type of Offenses Used and Neighborhood Concentration:

Washington D.C.'s wards experience different levels and types of crime. Some areas having a higher violent crime rates while other having more property-related crimes. Knowing the differences is crucial for identifying similar patterns and risks. By comparing Ward 3 and Ward 8, it highlights how specific offense types contribute to the overall crime burden in each area. Property crimes such as theft and theft from auto appear more concentrated in Ward 3, while Ward 8 having higher counts in offenses like motor vehicle theft, assault with a dangerous weapon, and robbery. It shows that crime is not only unevenly distributed, but also having differences in severity and impact. Knowing which area experience higher levels of violent crime vs. property crime can help law enforcement to focus their resources more effectively between the Wards.

<img width="1509" height="291" alt="PNG image" src="https://github.com/user-attachments/assets/6f94a886-c807-4363-bd2e-1b53fb64ae2a" />


Manipulation Applied:

The following manipulations and calculated fields were applied in Tableau:

Crime Count per Ward: A simple COUNT measure of CCN was used as the primary metric for incident volume, aggregated at the WARD level.

Analysis and Results:

Question 1: Crime Distribution Across D.C. Wards

Visualization: Choropleth map: Washington D.C. divided into 8 wards, color-encoded by total crime count per ward, where darker shades indicate a higher number of reported incidents and lighter shades indicate fewer. Both violent crimes (homicide, robbery, assault with a dangerous weapon, sex abuse) and property crimes (theft/other, theft from auto, motor vehicle theft, burglary, arson) are displayed simultaneously. A choropleth map was chosen because it most effectively communicates geographic variation in crime volume across D.C.'s 8 wards. A map allows the reader to immediately identify high and low crime areas spatially, which would not be as intuitive in a bar chart or table.

Findings:
Based on the map, Ward 2 recorded the highest total incident driven mainly by property crime. This makes sense as Ward 2 was located in downtown of D.C. where it has a dense population with tourist attractions.  Wards 7 and 8, located in the eastern and southeastern parts of D.C., shows that there is a deeper structural disparities in those regions that could be contributed to a multitude of factors such as lower median income or limited access to protection. Ward 3, located in the upper northwest of D.C., recorded the lowest overall crime rate and is considered one of the safest and most affluent residential areas in the city. 

Question 2: Ward 3 and Ward 8: Comparing Time of Day to Type of Offenses Used and Neighborhood Concentration:

Visualization: Side-by-side bar chart — Offense Type (y-axis) vs. Number of Incidents (x-axis), color-coded by Ward (Ward 3 vs. Ward 8). A side-by-side bar chart was chosen because it allows for a direct visual comparison of offense type frequencies between two specific wards. Placing Ward 3 and Ward 8 bars adjacent to each other for each offense type makes it easy to spot which ward is higher in each crime category, which a pie chart or table would make harder to see at a glance.

Based on the bar chart, wealth and opportunity play a major role in the disparity in crime between Ward 3 and Ward 8. Ward 3 is the wealthiest ward in Washington, DC, with high incomes, low unemployment, and a majority of residents holding college degrees. In contrast, Ward 8 is the poorest ward, with significantly higher unemployment rates, around 30% of residents living in poverty, and far fewer educational and economic opportunities. Research consistently demonstrates that both violent and property crime increase when people lack steady employment and income. This also explains the types of crime seen in each ward: Ward 8's concentrated poverty drives violent offenses like robbery and assault, while Ward 3's relative wealth attracts property crimes like theft and theft from auto. Ward 8 recorded 282 incidents of assault with a dangerous weapon compared to 21 in Ward 3, representing an almost 14x difference. Motor vehicle theft followed a similar pattern, with Ward 8 reporting 571 incidents vs. Ward 3's 97. Conversely, theft/other was the dominant offense in Ward 3 with 1,014 incidents, while Ward 8 recorded only 841.

District of Columbia Metropolitan Police Department. (2025). Crime Incidents 2025. Retrieved from https://catalog.data.gov/dataset

District of Columbia Office of Planning. (n.d.). What's My Ward? Retrieved from https://planning.dc.gov/whatsmyward

Learning Life. (2018, April 4). DC rich and poor: A tale of two wards. Retrieved from https://learninglife.info/wards3and8/

The Tableau packaged workbook containing all visualizations and data connections is available in this repository: Group_Project_2.twbx
