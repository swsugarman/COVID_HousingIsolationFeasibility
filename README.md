# What Housing Determinents Affected COVID Case Counts  

## Introduction

On the West Coast, the metropolitan areas of COVID-19 case counts soared in the LA Metro Area while the metropolitan area of San Francisco, Sacramento, Portland, and Seattle experienced much smaller surges during the same time periods. Governmental policies in 2020 were nearly identical in California's cities and were very similar across the West Coast in California, Oregon, and Washington (and to lesser degrees in Nevada and Colorado) due to the Western States Pact (https://en.wikipedia.org/wiki/Western_States_Pact). Yet despite this standardization of public health policies across the West Coast, widely varying surge levels occurred across different metropolitan areas. 

One of the most important tools for limiting pandemic spread and surge levels is to have individuals with possible COVID exposure or a positive COVID test undergo a 14 day isolation period. While a few limited jurisdictions had isolation hotels set up for the homeless or at-risk groups, the standard guidance was that individuals should isolated at home upon notification of a positive test result or possible exposure. The CDC's requirements for home isolation include:

* There is a bedroom where the patient can recover without sharing immediate space with others.
* There is a separate bathroom for the patient. If this is not feasible, care should be taken to disinfect the bathroom after each use.

Maintaining proper home isolation is only feasible if the housing unit has at least one half bathroom and one bedroom more than the number of people living in the household. While a studio apartment may safely accomomodate the isolation of an individual living alone, a studio would be an infeasible housing unit for isolation if there were two people residing in it. Similarly, a two bedroom one bathroom housing unit with two or more residents could not feasibly maintain isolation as there would not be a bathroom that could be solely dedicated to the use of the isolated individual. In an Annals of Internal Medicine letter, researchers concluded that 'More than 1 in 5 U.S. homes, housing about one quarter of all Americans, lack sufficient space and plumbing facilities to comply with recommendations to isolate or quarantine to limit household spread of COVID-19.' They also found significantly greater disparities among BIPOC, apartment dwellers, and poorer individuals. 

Using the American Housing Survey's metropolitan-level data on household sizes, bedrooms, and bathrooms, I will calculate each metropolitan area's proportion of households able to feasibly follow the CDC Isolation guidance. 

## American Housing Survey
The American Housing Survey (AHS) is sponsored by the Department of Housing and Urban Development (HUD) and conducted by the U.S. Census Bureau. The survey has been the most comprehensive national housing survey in the United States since its inception in 1973, providing current information on the size, composition, and quality of the nation’s housing and measuring changes in our housing stock as it ages. The AHS is a longitudinal housing unit survey conducted biennially in odd-numbered years, with samples redrawn in 1985 and 2015 .

The survey provides up-to-date information about the quality and cost of housing in the United States and major metropolitan areas. The survey also includes questions about:

*the physical condition of homes and neighborhoods,
*the costs of financing and maintaining homes, and
*the characteristics of people who live in these homes.


## Data Dictionary

| Field | Description |
| :--- | :--- |
| BEDROOMS | Number of bedrooms in unit |
| BATHROOMS | Number of bathrooms in unit |
| NUMPEOPLE | Number of persons living in this unit |
| NUMELDERS | Number of persons age 65 and over living in this unit |
| MULTIGEN | Type of multigenerational household |
| NUMSUBFAM | Number of subfamilies living in this unit |
| NUMSECFAM | Number of secondary families living in this unit|
|CONTROL| AHS 2015 control number aka internal census. gov household ID number|
| OMB13CBSA | CBSA Metropolitan Area | 
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


## Important Links

* [Final Report Notebook](report.ipynb)
* [EDA Notebook](eda.ipynb)
* [CDC](https://www.cdc.gov/coronavirus/2019-ncov/hcp/guidance-home-care.html) - CDC Guidance on Home Isolation and Care 
* [Census](https://www.census.gov/library/stories/2021/04/were-american-homes-ready-for-the-pandemic.html?utm_campaign=20210413msacos1ccstors&utm_medium=email&utm_source=govdelivery) - Were American Homes Ready for the Pandemic?
* [Annals of Internal Medicine](https://www.acpjournals.org/doi/10.7326/M20-4331) - Feasibility of Separate Rooms for Home Isolation and Quarantine for COVID-19 in the United States
