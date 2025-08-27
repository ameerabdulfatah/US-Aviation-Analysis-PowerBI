U.S. Aviation Infrastructure Analysis - Power BI Project
Project Overview
This project involves the analysis of the Aviation Facilities dataset, a comprehensive database of all official aerodromes in the United States, sourced from the U.S. Department of Transportation (USDOT) / Bureau of Transportation Statistics (BTS) National Transportation Atlas Database (NTAD). The data is updated every 28 days from the Federal Aviation Administration (FAA).

The goal of this project was to develop a three-page Power BI dashboard to provide a holistic view of the aviation landscape, moving from a high-level geographic overview to a deep, actionable analysis of risk, safety, and facility capabilities.

Problem Statement
Efficient and safe aviation infrastructure is critical for national transportation and commerce. Airport authorities and federal regulators often lack a unified, interactive tool to assess the operational status, ownership complexities, and potential risks across thousands of airports. This project aims to bridge that gap by creating a dynamic dashboard to support data-driven decision-making for resource allocation, safety oversight, and strategic development.

Data Cleaning & Preprocessing
The raw dataset, while comprehensive, required significant preprocessing to be ready for analysis. The initial dataset contained 19,952 rows and 93 columns. The cleaning process, documented in the provided Jupyter Notebook (Aviation_Project.ipynb), involved several key steps:

Handling Missing Values:

Column Removal: Columns with over 80% missing values that were not critical to the core analysis (e.g., TPA, PHONE_NO, ICAO_ID) were removed to reduce noise. This streamlined the dataset from 93 columns to 64.

Row Removal: Rows with more than 50% missing data were dropped to ensure the integrity of the remaining entries.

Imputation: For remaining essential columns with sparse missing data, numerical fields (like ELEV) were filled with the median, while categorical fields (like STATE_NAME) were filled with the mode.

Feature Engineering (in Power BI):

Calculated Airport Age (Power Query): A new column, Airport Age, was engineered using a Power Query M formula to calculate the age of each airport from its ACTIVATION_DATE. This enabled historical and demographic analysis.

Calculated Inspection Status (DAX): A DAX calculated column, Inspection Status, was created to dynamically categorize each airport as "Inspection Recent" or "Inspection Overdue (>2 Years)" based on the LAST_INSPECTION date. This became a cornerstone of the risk analysis.

After cleaning and preprocessing, the final dataset used for the Power BI dashboard consisted of 19,808 rows and 64 columns, with no missing values in the key analytical fields.

Dashboard Deep Dive
(This section remains the same as before, detailing the purpose and insights of each of the three pages.)

Page 1: U.S. Aviation: Geographic & Ownership Overview
Purpose: To provide a high-level, geographic snapshot of all aviation facilities, answering the questions "Where are the airports?" and "Who owns them?".

Key Insights: Visualizes the high concentration of airports in states like Texas and California and shows that the vast majority of airports are publicly or privately owned, with a small military footprint.

Page 2: Operational Status & Airport Demographics
Purpose: To analyze the operational characteristics of the airports, focusing on their current status, age, and intended use.

Key Insights: Reveals that over 98% of airports are operational. The age distribution shows a significant boom in airport construction between 40-80 years ago. The dashboard also breaks down airport use by state, showing the split between public and private facilities.

Page 3: Risk, Safety & Capabilities Analysis
Purpose: To provide an actionable analysis of potential risks and facility capabilities, designed for regulatory bodies and airport authorities.

Key Insights:

Publicly owned airports have a significantly higher number of overdue inspections compared to other ownership types.

Airports with a military presence (Joint-Use) are proportionally far more likely to have major airframe repair facilities than civilian-only airports.

Charging landing fees is a common practice for Private and Public airports but is extremely rare for military facilities.

Tools Used
Python (Pandas): For initial data cleaning and preprocessing.

Microsoft Power BI: Power Query for final transformations, DAX for calculated columns, and report building for visualizations.
