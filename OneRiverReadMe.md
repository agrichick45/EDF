Final Clustering Results
================
Mandy Liesch
10/11/2021

-   [Project Objectives](#project-objectives)
-   [Dataset Manipulation:](#dataset-manipulation)
    -   [OneRiver.csv File:](#onerivercsv-file)
        -   [Social Determinants of
            Health](#social-determinants-of-health)
        -   [Social Capital Index](#social-capital-index)
        -   [ESRI County Health Rankings](#esri-county-health-rankings)
        -   [Atlas of Rural America](#atlas-of-rural-america)
    -   [Missing Data](#missing-data)
        -   [Death of Despair](#death-of-despair)
        -   [Diabetes Mellitus Deaths](#diabetes-mellitus-deaths)
        -   [Firearm Fatalities](#firearm-fatalities)

# Project Objectives

There are many different ways to classify “risk” in rural areas. There
are current environmental exposures, socio-economic variables, issues
that result from culture shifts, population dynamic changes, changes in
agricultural resilience, and future risks changes from shifting
climates, crop yield changes, and environmental hazards.

This project focused on a 12 state region: The states along the main
branch of the Mississippi River basin, the Ohio, and Tennessee River.

# Dataset Manipulation:

## OneRiver.csv File:

There are several different datasets that were utilized to build the One
River Dataset:

### Social Determinants of Health

[Social Determinants of
Health](https://www.ahrq.gov/sdoh/data-analytics/sdoh-data.html):
Looking at the
[documentation](https://www.ahrq.gov/sites/default/files/wysiwyg/sdohchallenge/data/sdoh_data_file_documentation.pdf),
it aggregates several sources of health data. Data is availabe at both
county and zip code levels. For this project, we are using the County
data.

Including:  
\* American Community Survey (ACS)  
\* Area Health Resources Files (AHRF)  
\* Foundation for AIDS Research (amfAR)  
\* U.S. Census County Business Patterns (CCBP)  
\* Centers for Disease Control and Prevention Interactive Atlas of Heart
Disease and Stroke (CDC Atlas)  
\* Centers for Disease Control and Prevention Wide-ranging ONline Data
for Epidemiologic Research (CDC WONDER)  
\* County Health Rankings (CHR)  
\* Civil Rights Data Collection (CRDC)  
\* Medicare Advantage Penetration (MAP)  
\* National Environmental Public Health Tracking Network (NEPHTN)  
\* National Center for Health Statistics (NCHS) Urban-Rural
Classification Scheme  
\* Nursing Home Compare (NHC)  
\* Social Vulnerability Index (SVI)  
\* U.S. Cancer Statistics (USCS)

### Social Capital Index

Along with the social determinents of health database, the [Social
Capital Index
(SoCI)](https://www.researchgate.net/publication/337813421_Capturing_Bonding_Bridging_and_Linking_Social_Capital_through_Publicly_Available_Data)
uses 19 indicators of public data to determine which communities are
more capable of disaster resilience, based on how communities are
organized and researched. They use three categories (bonding, bridging,
and linking) to design an overall index by county. The base indicators
that are not well represented with the above dataset were added into the
Social Determinants of Health Dataset.

### ESRI County Health Rankings

In addition, the [ESRI County Health
Rankings](https://www.arcgis.com/home/item.html?id=c514eddc6d584e85bc2f90be25305fc8)
that were not in the other databases were added to the csv datafile.

### Atlas of Rural America

There are still several variables that we want for analysis missing from
the dataset. The USDA Economic Research Services (ERS), publishes a
[Rural Atlas of Rural and Small Town
America](https://www.ers.usda.gov/data-products/atlas-of-rural-and-small-town-america/).
this site looks at variables of people, economic, and jobs data. The
website above documents the maps and processes used to create this
atlas.

## Missing Data

### Death of Despair

This data spanned a 5 year range from 2015-2019. Defined as Drug
Overdoses, Alcohol Related Deaths, Suicides, and Homicides, getting
reliable county level estimates can be difficult, especially in rural
areas. The CDC suppresses any county information where there are not at
least 10 of each individual type of deaths. In areas with low population
density, it can take 20+ years to get to 10 of these deaths. So, to fill
in these blank data rates, the [2013 Urban and Rural
classification](https://www.cdc.gov/nchs/data_access/urban_rural.htm)
average values were used by county type (Metropolitan Core,
Micropolitan, non-core, etc.) as a substitution. This dataset deals with
Non-Ignorable Missingness, meaning that the missing data trends toward
rural areas.

There are 180 counties that are suppressed with Suicide and Homicide
Data:  
- 3 Large Fringe Metro: All in Indiana  
- 3 Medium Metro: All in Iowa  
- 3 Small Metro: All in Kentucky  
- 17 Micropolitan: 6 States  
- 155 Non Core Metro: 12 States

There are 222 counties that are suppressed for Alcohol and Drug
Overdoses:  
- 2 Large Fringe Metro: All in Mississippi  
- 6 Medium Metro: 2 in Arkansas, 4 in Iowa  
- 9 Small Metro: 3 States (KY, LA, MO)  
- 24 Micropolitan: 6 States  
- 183 Non Core Metro: 11 States (Not Ohio)

### Diabetes Mellitus Deaths

Deaths from Diabetes were calculated over the five year span of
2015-2019 from the CDC Wonder Data. Like the Deaths from Despair Data,
there are several counties with less than 10 deaths.

There are 43 Counties with missing Diabetes data:  
- 2 Large Fringe Metro: Both in Indiana  
- 6 Micropolitan: Arkansas, Kentucky, and Illinois  
- 35 Non Core Metro: 7 States

| State       | Urbanization            | Suicide | Homicide | DrugOD | Alcohol | Diabetes |
|:------------|:------------------------|--------:|---------:|-------:|--------:|---------:|
| Arkansas    | Large Fringe Metro      |    13.2 |     23.4 |   16.9 |    5.34 |     57.6 |
| Arkansas    | Medium Metro            |    17.8 |      7.2 |   14.5 |    9.40 |     31.9 |
| Arkansas    | Small Metro             |    19.8 |     12.4 |   17.9 |   10.00 |     29.7 |
| Arkansas    | Micropolitan (Nonmetro) |    20.3 |      9.4 |   13.9 |   10.20 |     40.4 |
| Arkansas    | NonCore (Nonmetro)      |    21.2 |      7.1 |   13.9 |   10.20 |     41.6 |
| Illinois    | Large Central Metro     |     8.7 |     14.0 |   22.0 |    8.50 |     22.1 |
| Illinois    | Large Fringe Metro      |    11.0 |      3.4 |   17.4 |    7.40 |     19.2 |
| Illinois    | Medium Metro            |    14.7 |      7.0 |   25.5 |   11.80 |     24.8 |
| Illinois    | Small Metro             |    13.9 |      5.2 |   19.7 |    9.60 |     21.7 |
| Illinois    | Micropolitan (Nonmetro) |    16.6 |      2.6 |   17.8 |   10.20 |     28.2 |
| Illinois    | NonCore (Nonmetro)      |    17.5 |      2.3 |   15.4 |    6.90 |     33.6 |
| Indiana     | Large Central Metro     |    14.6 |     17.4 |   35.6 |   14.40 |     26.9 |
| Indiana     | Large Fringe Metro      |    15.3 |      5.8 |   24.9 |    9.90 |     27.2 |
| Indiana     | Medium Metro            |    14.9 |      7.5 |   21.7 |   12.90 |     32.1 |
| Indiana     | Small Metro             |    15.4 |      4.0 |   21.1 |   11.80 |     28.3 |
| Indiana     | Micropolitan (Nonmetro) |    16.1 |      3.2 |   22.9 |    9.30 |     39.6 |
| Indiana     | NonCore (Nonmetro)      |    17.3 |      2.7 |   20.9 |    8.30 |     39.3 |
| Iowa        | Medium Metro            |    15.7 |      3.5 |   14.5 |   12.80 |     22.8 |
| Iowa        | Small Metro             |    12.6 |      2.3 |    8.1 |   10.90 |     22.6 |
| Iowa        | Micropolitan (Nonmetro) |    17.7 |      3.0 |   10.9 |   14.40 |     36.6 |
| Iowa        | NonCore (Nonmetro)      |    14.8 |      1.5 |    7.5 |   11.20 |     40.5 |
| Kentucky    | Large Central Metro     |    17.0 |     13.3 |   41.7 |   13.00 |     27.5 |
| Kentucky    | Large Fringe Metro      |    16.2 |      2.6 |   45.2 |   12.30 |     29.7 |
| Kentucky    | Medium Metro            |    15.2 |      5.5 |   35.1 |   12.30 |     29.1 |
| Kentucky    | Small Metro             |    17.1 |      4.9 |   17.3 |   10.20 |     31.0 |
| Kentucky    | Micropolitan (Nonmetro) |    18.7 |      5.0 |   28.6 |    9.70 |     35.7 |
| Kentucky    | NonCore (Nonmetro)      |    18.9 |      5.1 |   28.5 |    9.80 |     44.8 |
| Louisiana   | Large Central Metro     |    11.8 |     34.8 |   39.0 |    6.60 |     25.7 |
| Louisiana   | Large Fringe Metro      |    15.4 |     10.4 |   33.2 |    8.30 |     20.5 |
| Louisiana   | Medium Metro            |    14.3 |     13.5 |   19.3 |    7.60 |     26.2 |
| Louisiana   | Small Metro             |    16.7 |      9.9 |   21.9 |    7.40 |     36.5 |
| Louisiana   | Micropolitan (Nonmetro) |    16.8 |     10.3 |   20.6 |    8.40 |     38.0 |
| Louisiana   | NonCore (Nonmetro)      |    16.8 |      8.2 |   15.7 |    6.20 |     35.6 |
| Minnesota   | Large Central Metro     |    12.2 |      4.0 |   17.4 |   13.70 |     20.5 |
| Minnesota   | Large Fringe Metro      |    12.9 |      1.4 |   11.3 |   10.00 |     18.6 |
| Minnesota   | Medium Metro            |    20.5 |      2.0 |   20.0 |   25.10 |     35.2 |
| Minnesota   | Small Metro             |    13.0 |      1.4 |   10.7 |   11.20 |     19.0 |
| Minnesota   | Micropolitan (Nonmetro) |    15.3 |      1.9 |   12.1 |   11.90 |     28.2 |
| Minnesota   | NonCore (Nonmetro)      |    17.5 |      2.3 |   12.9 |   13.70 |     40.5 |
| Mississippi | Large Fringe Metro      |    14.1 |      9.6 |   18.1 |    5.90 |     44.3 |
| Mississippi | Medium Metro            |    15.5 |     12.4 |   14.2 |    7.40 |     28.2 |
| Mississippi | Small Metro             |    14.5 |      8.4 |   12.6 |    3.20 |     26.4 |
| Mississippi | Micropolitan (Nonmetro) |    12.7 |     14.1 |   10.4 |    7.10 |     44.9 |
| Mississippi | NonCore (Nonmetro)      |    14.3 |     11.8 |   11.6 |    6.60 |     39.8 |
| Missouri    | Large Central Metro     |    17.8 |     28.5 |   33.7 |   13.80 |     22.8 |
| Missouri    | Large Fringe Metro      |    17.4 |      8.2 |   26.5 |    7.80 |     20.5 |
| Missouri    | Medium Metro            |    21.6 |      4.5 |   24.2 |   12.70 |     24.2 |
| Missouri    | Small Metro             |    17.7 |      5.4 |   13.6 |    7.40 |     28.7 |
| Missouri    | Micropolitan (Nonmetro) |    20.8 |      4.5 |   18.5 |    7.30 |     33.9 |
| Missouri    | NonCore (Nonmetro)      |    20.7 |      4.9 |   16.7 |    8.70 |     35.1 |
| Ohio        | Large Central Metro     |    13.0 |     11.2 |   40.1 |   10.10 |     27.6 |
| Ohio        | Large Fringe Metro      |    14.3 |      2.7 |   33.3 |    8.90 |     24.8 |
| Ohio        | Medium Metro            |    16.5 |      6.9 |   41.9 |   11.80 |     34.2 |
| Ohio        | Small Metro             |    16.5 |      5.3 |   41.9 |    9.80 |     44.6 |
| Ohio        | Micropolitan (Nonmetro) |    16.5 |      2.8 |   32.0 |    9.20 |     40.5 |
| Ohio        | NonCore (Nonmetro)      |    15.9 |      3.4 |   27.1 |    8.30 |     40.1 |
| Tennessee   | Large Central Metro     |    11.8 |     18.1 |   28.1 |   10.20 |     25.9 |
| Tennessee   | Large Fringe Metro      |    16.8 |      4.6 |   23.9 |    9.40 |     20.1 |
| Tennessee   | Medium Metro            |    17.9 |      6.1 |   34.6 |   14.70 |     29.8 |
| Tennessee   | Small Metro             |    18.5 |      5.2 |   23.9 |   13.40 |     31.8 |
| Tennessee   | Micropolitan (Nonmetro) |    21.3 |      3.9 |   24.7 |   13.20 |     37.4 |
| Tennessee   | NonCore (Nonmetro)      |    21.7 |      5.5 |   25.3 |   11.50 |     40.4 |
| Wisconsin   | Large Central Metro     |    12.4 |     14.7 |   36.0 |   15.50 |     25.6 |
| Wisconsin   | Large Fringe Metro      |    13.8 |      1.6 |   15.9 |    9.30 |     22.8 |
| Wisconsin   | Medium Metro            |    14.4 |      1.8 |   17.1 |   11.00 |     18.0 |
| Wisconsin   | Small Metro             |    16.5 |      2.0 |   15.8 |   13.30 |     24.3 |
| Wisconsin   | Micropolitan (Nonmetro) |    16.2 |      1.5 |   16.3 |   14.10 |     29.0 |
| Wisconsin   | NonCore (Nonmetro)      |    18.0 |      1.8 |   13.2 |   16.80 |     35.5 |

### Firearm Fatalities

The same five year span was used to calculate all firearm fatalities
from the CDC Wonder Data.
