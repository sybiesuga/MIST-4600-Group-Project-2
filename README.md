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
The dataset captures every reported crime incident across all 8 wards of Washington D.C. for the full year 2025. Offense types range from property crimes (theft, burglary, motor vehicle theft) to violent crimes (robbery, assault, homicide, sex abuse, arson). The data provides rich geographic, temporal, and categorical detail suitable for multi-dimensional analysis. Data types are a mix of integers (WARD, DISTRICT, PSA, CCN), floats (coordinates), and strings (OFFENSE, METHOD, SHIFT, BLOCK, etc.)

Two Questions:

How does crime type distribution vary across D.C.'s 8 wards, and which wards face the highest burden of violent vs. property crime?
Why it's important:

Washington D.C. is divided into 8 wards with significant differences in demographics, income levels, and population density. Understanding how crime types are distributed across wards has major social and policy implications. City officials and the Metropolitan Police Department can use this analysis to allocate patrol resources more effectively, and residents can make more informed decisions about community safety. The disparity between property crimes (theft, burglary) and violent crimes (robbery, assault, homicide) across wards reveals systemic inequities that relate to broader economic and social factors. This question directly leverages the WARD and OFFENSE columns.

<img width="1046" height="629" alt="Screenshot 2026-04-10 at 8 41 27 PM" src="https://github.com/user-attachments/assets/6789dc5c-ae8b-45ae-be16-a19d30fa4680" />

Does the time of day (shift) influence the type of method used in crimes, and are certain offense categories more likely to involve weapons during specific shifts?
Why it's important:

The intersection of time-of-day and weapon use in crime is critical for understanding when and how residents are most at risk. From a public safety standpoint, knowing whether gun-related crimes spike during midnight or evening shifts — or whether knife crimes are more common during day shifts — allows law enforcement to deploy armed response units strategically and can inform city-wide policies on nightlife safety and late-night transit. It also has economic implications: businesses operating late-night hours in high-risk areas may need additional security investment. This question leverages the SHIFT, METHOD, and OFFENSE columns.

><img width="1005" height="304" alt="Screenshot 2026-04-10 at 8 43 05 PM" src="https://github.com/user-attachments/assets/d32043e9-95f1-4f2e-a112-44559f3a9b3f" />

Manipulation Applied:

The following manipulations and calculated fields were applied in Tableau:

Crime Category (Calculated Field): A custom dimension was created to group offenses into two high-level categories:

Violent Crime: HOMICIDE, ROBBERY, ASSAULT W/DANGEROUS WEAPON, SEX ABUSE
Property Crime: THEFT/OTHER, THEFT F/AUTO, MOTOR VEHICLE THEFT, BURGLARY, ARSON

This grouping allows for cleaner comparative analysis between crime types.
Month Extraction: The REPORT_DAT field was parsed to extract month, enabling time-series analysis of crime trends across the year.
Weapon Used (Binary Flag): A boolean calculated field was derived from the METHOD column: incidents coded as GUN or KNIFE were flagged as "Weapon Involved = Yes," while OTHERS was flagged as "No." This simplified the weapon-use analysis for Question 2.
Crime Count per Ward: A simple COUNT measure of CCN (the unique incident identifier) was used as the primary metric for incident volume, aggregated at the WARD level.


Analysis and Results:

Question 1: Crime Distribution Across D.C. Wards
Visualization: Stacked bar chart — Wards (x-axis) vs. Count of Incidents (y-axis), color-encoded by Crime Category (Violent vs. Property).
Findings:
Ward 2 recorded the highest total incident count, driven predominantly by property crime, likely reflecting its dense commercial and tourist activity (downtown/Penn Quarter area). Wards 7 and 8, located in the eastern and southeastern parts of D.C., show a disproportionately higher share of violent crimes relative to their total incident count, pointing to structural disparities in those communities. Ward 3 (upper northwest) had the lowest total crime volume overall.

Question 2: Weapon Use by Shift and Offense Type
Visualization: Heat map — Offense Type (rows) vs. Shift (columns), with color intensity representing the proportion of incidents involving a weapon (GUN or KNIFE).
Findings:
Gun involvement was highest during the MIDNIGHT shift, particularly for ROBBERY and ASSAULT W/DANGEROUS WEAPON offenses, suggesting that violent armed crime peaks in late-night hours. Homicides showed elevated weapon involvement across all three shifts, but with a notable concentration at MIDNIGHT. Property crimes (THEFT/OTHER, THEFT F/AUTO) had near-zero weapon involvement across all shifts, confirming they are predominantly non-confrontational offenses.

References

District of Columbia Metropolitan Police Department. (2025). Crime Incidents 2025. Retrieved from https://catalog.data.gov/dataset
