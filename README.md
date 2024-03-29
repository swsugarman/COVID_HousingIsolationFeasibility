# Housing Feasible for Isolation and COVID Case Counts  

## Introduction

On the West Coast, the metropolitan areas of COVID-19 case counts soared in the LA Metro Area while the metropolitan area of San Francisco, Sacramento, Portland, and Seattle experienced much smaller surges during the same time periods. Governmental policies in 2020 were nearly identical in California's cities and were very similar across the West Coast in California, Oregon, and Washington (and to lesser degrees in Nevada and Colorado) due to the Western States Pact (https://en.wikipedia.org/wiki/Western_States_Pact). Yet despite this standardization of public health policies across the West Coast, widely varying surge levels occurred across different metropolitan areas. 

One of the most important tools for limiting pandemic spread and surge levels is to have individuals with possible COVID exposure or a positive COVID test undergo a 14 day isolation period. While a few limited jurisdictions had isolation hotels set up for the homeless or at-risk groups, the standard guidance was that individuals should isolated at home upon notification of a positive test result or possible exposure. The CDC's requirements for home isolation include:

>* There is a bedroom where the patient can recover without sharing immediate space with others.
>* There is a separate bathroom for the patient. If this is not feasible, care should be taken to disinfect the bathroom after each use.

Maintaining proper home isolation is only feasible if the housing unit with more than one resident has at minimum of one and a half bathrooms and has sufficient bedrooms to set aside at least one bedroom for isolation and still have a minimum one bedroom for every two people living in the household. While a studio apartment may safely accomomodate the isolation of an individual living alone, a studio would be an infeasible housing unit for isolation if there were two people residing in it. Similarly, a two bedroom one bathroom housing unit with two or more residents could not feasibly maintain isolation as there would not be a bathroom that could be solely dedicated to the use of the isolated individual. In an Annals of Internal Medicine letter, researchers concluded that 'More than 1 in 5 U.S. homes, housing about one quarter of all Americans, lack sufficient space and plumbing facilities to comply with recommendations to isolate or quarantine to limit household spread of COVID-19.' They also found significantly greater disparities among BIPOC, apartment dwellers, and poorer individuals. 

Using the American Housing Survey's metropolitan-level data on household sizes, bedrooms, and bathrooms, I will calculate each metropolitan area's proportion of households able to feasibly follow the CDC Isolation guidance. The American Housing Survey, the most in-depth and comprehensive national housing, has been conducted by the US Census Bureau on behalf of the Department of Housing and Urban Development (HUD) since 1973 biennially in odd-numbered years. The housing unit samples were redrawn in 2015 and covering a representative national sample as well as the Top 15 metopolitan areas (by size) and the Next 20 metropolitan areas (a set of metropolitan areas ranging from 16th to 51st largest by population) that are including in the survey in opposing biennial cycles. Due to the challenges of data processing and maintaining the privacy of respondents, the 2019 public use microdata files are not scheduled for release until Fall 2021 and the 2017 released files do not contain household-level microdata sufficient for this analysis.


## Datasets

** 2015 American Housing Survey Public Use Microdata Flat Files from Census.gov including the National Public Use File (ahs2015n.csv) and Metropolitan Public Use File (ahs2015m.csv) downloaded from https://www.census.gov/programs-surveys/ahs/data/2015/ahs-2015-public-use-file--puf-.html
** OMB2013CBSA code crosswalk from https://public.opendatasoft.com/explore/dataset/core-based-statistical-areas-cbsas-and-combined-statistical-areas-csas/download/?format=xls&timezone=America/Los_Angeles&lang=en&use_labels_for_header=true
**  USAFacts.org US COVID-19 cases and deaths by state from https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/

## Data Dictionary

| Field | Description |
| :--- | :--- |
| American Housing Survey 2015 |
| :--- | :--- |
|CONTROL| AHS 2015 control number aka internal census. gov household ID number|
| OMB13CBSA | CBSA Metropolitan Area numerical code | 
| VACANCY| Vacancy status |
| BLD | Type of housing unit| 
| UNITSIZE | Unit size in square feet | 
| TOTROOMS| Total number of rooms in unit |
|BEDROOMS| Number of bedrooms in unit |
| BATHROOMS |Number of bathrooms in unit | 
|HSHLDTYPE|Type of household|
|NUMPEOPLE|Number of persons living in this unit| 
|NUMADULTS|Number of persons age 18 and over living in this unit|
|NUMELDERS|Number of persons age 65 and over living in this unit|
|NUMYNGKIDS|Number of children under age 6 living in this unit|
|NUMOLDKIDS|Number of children age 6 through 17 living in this unit|
|NUMVETS|Number of veterans living in this unit|
|NUMNONREL|Number of nonrelatives living in this unit|
|MULTIGEN|Type of multigenerational household|
|GRANDHH|Flag indicating grandparent headed household with no parent present|
|NUMSUBFAM|Number of subfamilies living in this unit|
|NUMSECFAM|Number of secondary families living in this unit|
|DISHH|Flag indicating disabled person household|
|WASHER|Flag indicating unit has a working washing machine| 
|DRYER|Type of clothes dryer|
|FRIDGE|Flag indicating unit has a working refrigerator| 
|COOKTYPE|Type of cooking equipment|
|KITEXCLU|Flag indicating the unit's kitchen facilities are for the exclusive use of the household|
|BATHEXCLU|Flag indicating the unit's bathroom facilities are for the exclusive use of the household|
| :--- | :--- |
| USAFacts.org US COVID-19 cases and deaths by state |
| :--- | :--- |
|CountyFIPS|Federal standard numerical identifier composed of a two digit stateFIPS numerical code and a three digit county identifying code |
|StateFIPS | Federal standard two digit numerical identifier for every state and territory |
|Population | Census population data by county then summed by metropolitan area|
|Cases | Total confirmed COVID-19 cases by county as reported to the CDC by 6/9/2021 |
| :--- | :--- |
| OMB2013CBSA code crosswalk |
| :--- | :--- |
| CBSA Code| CBSA Metropolitan Area numerical code |	
|CBSA Title | CBSA Metropolitan Area official title |
|County/County Equivalent | County name |
| State Name| State |
|FIPS State Code|Federal standard two digit numerical identifier for every state and territory|
|FIPS County Code|Federal standard numerical identifier composed of a two digit stateFIPS numerical code and a three digit county identifying code|

## Important Links

* [Final Report Notebook](report.ipynb)
* [EDA Notebook](eda.ipynb)
* [CDC](https://www.cdc.gov/coronavirus/2019-ncov/hcp/guidance-home-care.html) - CDC Guidance on Home Isolation and Care 
* [Census](https://www.census.gov/library/stories/2021/04/were-american-homes-ready-for-the-pandemic.html?utm_campaign=20210413msacos1ccstors&utm_medium=email&utm_source=govdelivery) - Were American Homes Ready for the Pandemic?
* [Annals of Internal Medicine](https://www.acpjournals.org/doi/10.7326/M20-4331) - Feasibility of Separate Rooms for Home Isolation and Quarantine for COVID-19 in the United States

