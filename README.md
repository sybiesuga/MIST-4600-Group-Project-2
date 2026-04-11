# MIST-4600-Group-Project-2
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

Two Questions:

How does crime type distribution vary across D.C.'s 8 wards, and which wards face the highest burden of violent vs. property crime?
Why it's important: 

Washington D.C. is divided into 8 wards with significant differences in demographics, income levels, and population density. There are significant social and policy implications to understanding how the distribution of the type of crimes across the 8 wards has. This information can help individuals make informed decisions regarding the safety of the community and also help the Metropolitan Police Department and city officals distribute resources and officers more efficiently. The difference between violent crimes (robbery, assult, homicide) and property crimes (theft, burglary) between wards indicates if there are systematic injustices that are related to the more general economic and social factors. 

<img width="1046" height="629" alt="Screenshot 2026-04-10 at 8 41 27 PM" src="https://github.com/user-attachments/assets/6789dc5c-ae8b-45ae-be16-a19d30fa4680" />

Does the time of day (shift) influence the type of method used in crimes, and are certain offense categories more likely to involve weapons during specific shifts?
Why it's important:

Being able to see if there is a correlation between time-of-day and weapons used in crime is important for understanding when and how residents are the most at risk. For the safety of the public, knowing which weapons such as if knife crimes are more frequent during day shifts vs night shifts or if gun-related crimes increases during the evening or midnight shifts allows law enforements to strategically deploy their armed response units strategically and can inform the general public on what time or area to avoid and provide safety precautions. This can also help businesses that opens late or in areas that are considered high crimes to implement more security and protections. 

><img width="1005" height="304" alt="Screenshot 2026-04-10 at 8 43 05 PM" src="https://github.com/user-attachments/assets/d32043e9-95f1-4f2e-a112-44559f3a9b3f" />

Manipulation Applied:

The following manipulations and calculated fields were applied in Tableau:

Crime Category (Calculated Field): This was a custom dimension that was created to group offenses to two categories:

Violent Crime: HOMICIDE, ROBBERY, ASSAULT W/DANGEROUS WEAPON, SEX ABUSE
Property Crime: THEFT/OTHER, THEFT F/AUTO, MOTOR VEHICLE THEFT, BURGLARY, ARSON

This allows for an easier viewing of the different types of crimes and what was more frequent without needing any familiarity with the dataset. 

% of Weapons Used (Calculated Field/Binary Field):  A boolean calculated field was derived from the METHOD column which measure the proportion of incidents that involed a weapon which in this case is either GUN or KNIFE (1) or no weapon was present (0) and is grouped by offense type and shift. This formula returns a number between 0 and 1 that is shown as a percentage. 

Crime Count per Ward: A simple COUNT measure of CCN was used as the primary metric for incident volume, aggregated at the WARD level.


Analysis and Results:

Question 1: Crime Distribution Across D.C. Wards

Visualization: Stacked bar chart — Wards (x-axis) vs. Number of Incidents (y-axis), color-encoded by Crime Category (Violent vs. Property).
Findings:
Based on the bar chart, Ward 2 recorded the highest total incident driven mainly by property crime. This makes sense as Ward 2 was located in downtonw of D.C. where it has a dense population with tourist attractions.  Wards 7 and 8, located in the eastern and southeastern parts of D.C., shows that there is a deeper structural disparities in those regions that could be contributed to a multitude of factors such as lower median income or limited access to protection. Ward 2 has the lowest overall crime rate as it's located in the upper northwest of D.C. and considered one of the safest and most affluent residential areas. Which means Ward 3 has a higher socioeconomic status and more protected. 

Question 2: Weapon Use by Shift and Offense Type

Visualization: Heat map — Offense Type (rows) vs. Shift (columns), with a scale of red representing the proportion of incidents involving a weapon (GUN or KNIFE).
Findings:
Across all shifts, weapon involement has the highest amonst violent crime categories. Acrross all three shifts, Assult W/Dangerous Weapon consistently display high weapon involvement with 81.6% DAY, 79.4% EVENING and 84.9% for MIDNIGHT. The most notable pattern was homicide, with 89% of weapon involvement occuring only during the MIDNIGHT shift and no activity during the DAY or EVENING shifts which can be concluded that majority of homicide activity happens late at night and almost always involes a weapon. Additionally, robbery shows a distinct shift-based trend rising from 46.2% during DAY to 55.9% at MIDNIGHT which suggest that armed robbery is more prevelent late at night but is still frequent during daylight. Nearly no weapons were used in property crimes such as Theft/Other (.04%-1.6%) and Theft F/Auto (.3%-1.4%) during all shifts indicates that there are primarily non-confrontational offenses. Since arson is considered as an indirect offense, it recorded 0% weapon involement across all shifts. 

References

District of Columbia Metropolitan Police Department. (2025). Crime Incidents 2025. Retrieved from https://catalog.data.gov/dataset
District of Columbia Office of Planning. (n.d.). What's My Ward? Retrieved from https://planning.dc.gov/whatsmyward
