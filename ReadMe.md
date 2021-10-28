Environmental Justice Metadata
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
        -   [CDC Missing Data
            Replacements](#cdc-missing-data-replacements)
        -   [Firearm Fatalities](#firearm-fatalities)
-   [Spatial Data by Census Tract/Block
    Group](#spatial-data-by-census-tractblock-group)
    -   [Census Tract GIS Shapefile](#census-tract-gis-shapefile)
        -   [Census Tract Population](#census-tract-population)
        -   [Current Environmental
            Hazards](#current-environmental-hazards)
        -   [US EPA Environmental Justice
            Index](#us-epa-environmental-justice-index)
        -   [US EPA Safe Water Drinking
            Data](#us-epa-safe-water-drinking-data)
        -   [US EPA Environmental Quality Index
            (EQI)](#us-epa-environmental-quality-index-eqi)
        -   [US EPA Future Scenarios](#us-epa-future-scenarios)
    -   [Jobs and Economic Indicators](#jobs-and-economic-indicators)
        -   [Farm Income and Debt to Asset
            Ratio](#farm-income-and-debt-to-asset-ratio)
        -   [Industry Based Job Numbers](#industry-based-job-numbers)
        -   [Overall Industry Salaries](#overall-industry-salaries)
    -   [Aqueduct Water Risk Atlas](#aqueduct-water-risk-atlas)
    -   [Future Economic Data](#future-economic-data)
    -   [Land Use Change](#land-use-change)
        -   [Percent Cropland Lost and
            Gained](#percent-cropland-lost-and-gained)
    -   [100 Year Floodplain DEM](#100-year-floodplain-dem)

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
- American Community Survey (ACS)  
- Area Health Resources Files (AHRF)  
- Foundation for AIDS Research (amfAR)  
- U.S. Census County Business Patterns (CCBP)  
- Centers for Disease Control and Prevention Interactive Atlas of Heart
Disease and Stroke (CDC Atlas)  
- Centers for Disease Control and Prevention Wide-ranging ONline Data
for Epidemiologic Research (CDC WONDER)  
- County Health Rankings (CHR)  
- Civil Rights Data Collection (CRDC)  
- Medicare Advantage Penetration (MAP)  
- National Environmental Public Health Tracking Network (NEPHTN)  
- National Center for Health Statistics (NCHS) Urban-Rural
Classification Scheme  
- Nursing Home Compare (NHC)  
- Social Vulnerability Index (SVI)  
- U.S. Cancer Statistics (USCS)

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

### CDC Missing Data Replacements

<table class="striped">
<caption>
Average Defaults Used for Missing Data
</caption>
<thead>
<tr>
<th style="text-align:left;">
State
</th>
<th style="text-align:left;">
Urbanization
</th>
<th style="text-align:right;">
Suicide
</th>
<th style="text-align:right;">
Homicide
</th>
<th style="text-align:right;">
DrugOD
</th>
<th style="text-align:right;">
Alcohol
</th>
<th style="text-align:right;">
Diabetes
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Arkansas
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
13.2
</td>
<td style="text-align:right;">
23.4
</td>
<td style="text-align:right;">
16.9
</td>
<td style="text-align:right;">
5.34
</td>
<td style="text-align:right;">
57.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
17.8
</td>
<td style="text-align:right;">
7.2
</td>
<td style="text-align:right;">
14.5
</td>
<td style="text-align:right;">
9.40
</td>
<td style="text-align:right;">
31.9
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
19.8
</td>
<td style="text-align:right;">
12.4
</td>
<td style="text-align:right;">
17.9
</td>
<td style="text-align:right;">
10.00
</td>
<td style="text-align:right;">
29.7
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
20.3
</td>
<td style="text-align:right;">
9.4
</td>
<td style="text-align:right;">
13.9
</td>
<td style="text-align:right;">
10.20
</td>
<td style="text-align:right;">
40.4
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
21.2
</td>
<td style="text-align:right;">
7.1
</td>
<td style="text-align:right;">
13.9
</td>
<td style="text-align:right;">
10.20
</td>
<td style="text-align:right;">
41.6
</td>
</tr>
<tr>
<td style="text-align:left;">
Illinois
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
8.7
</td>
<td style="text-align:right;">
14.0
</td>
<td style="text-align:right;">
22.0
</td>
<td style="text-align:right;">
8.50
</td>
<td style="text-align:right;">
22.1
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
11.0
</td>
<td style="text-align:right;">
3.4
</td>
<td style="text-align:right;">
17.4
</td>
<td style="text-align:right;">
7.40
</td>
<td style="text-align:right;">
19.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
14.7
</td>
<td style="text-align:right;">
7.0
</td>
<td style="text-align:right;">
25.5
</td>
<td style="text-align:right;">
11.80
</td>
<td style="text-align:right;">
24.8
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
13.9
</td>
<td style="text-align:right;">
5.2
</td>
<td style="text-align:right;">
19.7
</td>
<td style="text-align:right;">
9.60
</td>
<td style="text-align:right;">
21.7
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
16.6
</td>
<td style="text-align:right;">
2.6
</td>
<td style="text-align:right;">
17.8
</td>
<td style="text-align:right;">
10.20
</td>
<td style="text-align:right;">
28.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
17.5
</td>
<td style="text-align:right;">
2.3
</td>
<td style="text-align:right;">
15.4
</td>
<td style="text-align:right;">
6.90
</td>
<td style="text-align:right;">
33.6
</td>
</tr>
<tr>
<td style="text-align:left;">
Indiana
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
14.6
</td>
<td style="text-align:right;">
17.4
</td>
<td style="text-align:right;">
35.6
</td>
<td style="text-align:right;">
14.40
</td>
<td style="text-align:right;">
26.9
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
15.3
</td>
<td style="text-align:right;">
5.8
</td>
<td style="text-align:right;">
24.9
</td>
<td style="text-align:right;">
9.90
</td>
<td style="text-align:right;">
27.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
14.9
</td>
<td style="text-align:right;">
7.5
</td>
<td style="text-align:right;">
21.7
</td>
<td style="text-align:right;">
12.90
</td>
<td style="text-align:right;">
32.1
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
15.4
</td>
<td style="text-align:right;">
4.0
</td>
<td style="text-align:right;">
21.1
</td>
<td style="text-align:right;">
11.80
</td>
<td style="text-align:right;">
28.3
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
16.1
</td>
<td style="text-align:right;">
3.2
</td>
<td style="text-align:right;">
22.9
</td>
<td style="text-align:right;">
9.30
</td>
<td style="text-align:right;">
39.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
17.3
</td>
<td style="text-align:right;">
2.7
</td>
<td style="text-align:right;">
20.9
</td>
<td style="text-align:right;">
8.30
</td>
<td style="text-align:right;">
39.3
</td>
</tr>
<tr>
<td style="text-align:left;">
Iowa
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
15.7
</td>
<td style="text-align:right;">
3.5
</td>
<td style="text-align:right;">
14.5
</td>
<td style="text-align:right;">
12.80
</td>
<td style="text-align:right;">
22.8
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
12.6
</td>
<td style="text-align:right;">
2.3
</td>
<td style="text-align:right;">
8.1
</td>
<td style="text-align:right;">
10.90
</td>
<td style="text-align:right;">
22.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
17.7
</td>
<td style="text-align:right;">
3.0
</td>
<td style="text-align:right;">
10.9
</td>
<td style="text-align:right;">
14.40
</td>
<td style="text-align:right;">
36.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
14.8
</td>
<td style="text-align:right;">
1.5
</td>
<td style="text-align:right;">
7.5
</td>
<td style="text-align:right;">
11.20
</td>
<td style="text-align:right;">
40.5
</td>
</tr>
<tr>
<td style="text-align:left;">
Kentucky
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
17.0
</td>
<td style="text-align:right;">
13.3
</td>
<td style="text-align:right;">
41.7
</td>
<td style="text-align:right;">
13.00
</td>
<td style="text-align:right;">
27.5
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
16.2
</td>
<td style="text-align:right;">
2.6
</td>
<td style="text-align:right;">
45.2
</td>
<td style="text-align:right;">
12.30
</td>
<td style="text-align:right;">
29.7
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
15.2
</td>
<td style="text-align:right;">
5.5
</td>
<td style="text-align:right;">
35.1
</td>
<td style="text-align:right;">
12.30
</td>
<td style="text-align:right;">
29.1
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
17.1
</td>
<td style="text-align:right;">
4.9
</td>
<td style="text-align:right;">
17.3
</td>
<td style="text-align:right;">
10.20
</td>
<td style="text-align:right;">
31.0
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
18.7
</td>
<td style="text-align:right;">
5.0
</td>
<td style="text-align:right;">
28.6
</td>
<td style="text-align:right;">
9.70
</td>
<td style="text-align:right;">
35.7
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
18.9
</td>
<td style="text-align:right;">
5.1
</td>
<td style="text-align:right;">
28.5
</td>
<td style="text-align:right;">
9.80
</td>
<td style="text-align:right;">
44.8
</td>
</tr>
<tr>
<td style="text-align:left;">
Louisiana
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
11.8
</td>
<td style="text-align:right;">
34.8
</td>
<td style="text-align:right;">
39.0
</td>
<td style="text-align:right;">
6.60
</td>
<td style="text-align:right;">
25.7
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
15.4
</td>
<td style="text-align:right;">
10.4
</td>
<td style="text-align:right;">
33.2
</td>
<td style="text-align:right;">
8.30
</td>
<td style="text-align:right;">
20.5
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
14.3
</td>
<td style="text-align:right;">
13.5
</td>
<td style="text-align:right;">
19.3
</td>
<td style="text-align:right;">
7.60
</td>
<td style="text-align:right;">
26.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
16.7
</td>
<td style="text-align:right;">
9.9
</td>
<td style="text-align:right;">
21.9
</td>
<td style="text-align:right;">
7.40
</td>
<td style="text-align:right;">
36.5
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
16.8
</td>
<td style="text-align:right;">
10.3
</td>
<td style="text-align:right;">
20.6
</td>
<td style="text-align:right;">
8.40
</td>
<td style="text-align:right;">
38.0
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
16.8
</td>
<td style="text-align:right;">
8.2
</td>
<td style="text-align:right;">
15.7
</td>
<td style="text-align:right;">
6.20
</td>
<td style="text-align:right;">
35.6
</td>
</tr>
<tr>
<td style="text-align:left;">
Minnesota
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
12.2
</td>
<td style="text-align:right;">
4.0
</td>
<td style="text-align:right;">
17.4
</td>
<td style="text-align:right;">
13.70
</td>
<td style="text-align:right;">
20.5
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
12.9
</td>
<td style="text-align:right;">
1.4
</td>
<td style="text-align:right;">
11.3
</td>
<td style="text-align:right;">
10.00
</td>
<td style="text-align:right;">
18.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
20.5
</td>
<td style="text-align:right;">
2.0
</td>
<td style="text-align:right;">
20.0
</td>
<td style="text-align:right;">
25.10
</td>
<td style="text-align:right;">
35.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
13.0
</td>
<td style="text-align:right;">
1.4
</td>
<td style="text-align:right;">
10.7
</td>
<td style="text-align:right;">
11.20
</td>
<td style="text-align:right;">
19.0
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
15.3
</td>
<td style="text-align:right;">
1.9
</td>
<td style="text-align:right;">
12.1
</td>
<td style="text-align:right;">
11.90
</td>
<td style="text-align:right;">
28.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
17.5
</td>
<td style="text-align:right;">
2.3
</td>
<td style="text-align:right;">
12.9
</td>
<td style="text-align:right;">
13.70
</td>
<td style="text-align:right;">
40.5
</td>
</tr>
<tr>
<td style="text-align:left;">
Mississippi
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
14.1
</td>
<td style="text-align:right;">
9.6
</td>
<td style="text-align:right;">
18.1
</td>
<td style="text-align:right;">
5.90
</td>
<td style="text-align:right;">
44.3
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
15.5
</td>
<td style="text-align:right;">
12.4
</td>
<td style="text-align:right;">
14.2
</td>
<td style="text-align:right;">
7.40
</td>
<td style="text-align:right;">
28.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
14.5
</td>
<td style="text-align:right;">
8.4
</td>
<td style="text-align:right;">
12.6
</td>
<td style="text-align:right;">
3.20
</td>
<td style="text-align:right;">
26.4
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
12.7
</td>
<td style="text-align:right;">
14.1
</td>
<td style="text-align:right;">
10.4
</td>
<td style="text-align:right;">
7.10
</td>
<td style="text-align:right;">
44.9
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
14.3
</td>
<td style="text-align:right;">
11.8
</td>
<td style="text-align:right;">
11.6
</td>
<td style="text-align:right;">
6.60
</td>
<td style="text-align:right;">
39.8
</td>
</tr>
<tr>
<td style="text-align:left;">
Missouri
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
17.8
</td>
<td style="text-align:right;">
28.5
</td>
<td style="text-align:right;">
33.7
</td>
<td style="text-align:right;">
13.80
</td>
<td style="text-align:right;">
22.8
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
17.4
</td>
<td style="text-align:right;">
8.2
</td>
<td style="text-align:right;">
26.5
</td>
<td style="text-align:right;">
7.80
</td>
<td style="text-align:right;">
20.5
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
21.6
</td>
<td style="text-align:right;">
4.5
</td>
<td style="text-align:right;">
24.2
</td>
<td style="text-align:right;">
12.70
</td>
<td style="text-align:right;">
24.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
17.7
</td>
<td style="text-align:right;">
5.4
</td>
<td style="text-align:right;">
13.6
</td>
<td style="text-align:right;">
7.40
</td>
<td style="text-align:right;">
28.7
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
20.8
</td>
<td style="text-align:right;">
4.5
</td>
<td style="text-align:right;">
18.5
</td>
<td style="text-align:right;">
7.30
</td>
<td style="text-align:right;">
33.9
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
20.7
</td>
<td style="text-align:right;">
4.9
</td>
<td style="text-align:right;">
16.7
</td>
<td style="text-align:right;">
8.70
</td>
<td style="text-align:right;">
35.1
</td>
</tr>
<tr>
<td style="text-align:left;">
Ohio
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
13.0
</td>
<td style="text-align:right;">
11.2
</td>
<td style="text-align:right;">
40.1
</td>
<td style="text-align:right;">
10.10
</td>
<td style="text-align:right;">
27.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
14.3
</td>
<td style="text-align:right;">
2.7
</td>
<td style="text-align:right;">
33.3
</td>
<td style="text-align:right;">
8.90
</td>
<td style="text-align:right;">
24.8
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
16.5
</td>
<td style="text-align:right;">
6.9
</td>
<td style="text-align:right;">
41.9
</td>
<td style="text-align:right;">
11.80
</td>
<td style="text-align:right;">
34.2
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
16.5
</td>
<td style="text-align:right;">
5.3
</td>
<td style="text-align:right;">
41.9
</td>
<td style="text-align:right;">
9.80
</td>
<td style="text-align:right;">
44.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
16.5
</td>
<td style="text-align:right;">
2.8
</td>
<td style="text-align:right;">
32.0
</td>
<td style="text-align:right;">
9.20
</td>
<td style="text-align:right;">
40.5
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
15.9
</td>
<td style="text-align:right;">
3.4
</td>
<td style="text-align:right;">
27.1
</td>
<td style="text-align:right;">
8.30
</td>
<td style="text-align:right;">
40.1
</td>
</tr>
<tr>
<td style="text-align:left;">
Tennessee
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
11.8
</td>
<td style="text-align:right;">
18.1
</td>
<td style="text-align:right;">
28.1
</td>
<td style="text-align:right;">
10.20
</td>
<td style="text-align:right;">
25.9
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
16.8
</td>
<td style="text-align:right;">
4.6
</td>
<td style="text-align:right;">
23.9
</td>
<td style="text-align:right;">
9.40
</td>
<td style="text-align:right;">
20.1
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
17.9
</td>
<td style="text-align:right;">
6.1
</td>
<td style="text-align:right;">
34.6
</td>
<td style="text-align:right;">
14.70
</td>
<td style="text-align:right;">
29.8
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
18.5
</td>
<td style="text-align:right;">
5.2
</td>
<td style="text-align:right;">
23.9
</td>
<td style="text-align:right;">
13.40
</td>
<td style="text-align:right;">
31.8
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
21.3
</td>
<td style="text-align:right;">
3.9
</td>
<td style="text-align:right;">
24.7
</td>
<td style="text-align:right;">
13.20
</td>
<td style="text-align:right;">
37.4
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
21.7
</td>
<td style="text-align:right;">
5.5
</td>
<td style="text-align:right;">
25.3
</td>
<td style="text-align:right;">
11.50
</td>
<td style="text-align:right;">
40.4
</td>
</tr>
<tr>
<td style="text-align:left;">
Wisconsin
</td>
<td style="text-align:left;">
Large Central Metro
</td>
<td style="text-align:right;">
12.4
</td>
<td style="text-align:right;">
14.7
</td>
<td style="text-align:right;">
36.0
</td>
<td style="text-align:right;">
15.50
</td>
<td style="text-align:right;">
25.6
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Large Fringe Metro
</td>
<td style="text-align:right;">
13.8
</td>
<td style="text-align:right;">
1.6
</td>
<td style="text-align:right;">
15.9
</td>
<td style="text-align:right;">
9.30
</td>
<td style="text-align:right;">
22.8
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Medium Metro
</td>
<td style="text-align:right;">
14.4
</td>
<td style="text-align:right;">
1.8
</td>
<td style="text-align:right;">
17.1
</td>
<td style="text-align:right;">
11.00
</td>
<td style="text-align:right;">
18.0
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Small Metro
</td>
<td style="text-align:right;">
16.5
</td>
<td style="text-align:right;">
2.0
</td>
<td style="text-align:right;">
15.8
</td>
<td style="text-align:right;">
13.30
</td>
<td style="text-align:right;">
24.3
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
Micropolitan (Nonmetro)
</td>
<td style="text-align:right;">
16.2
</td>
<td style="text-align:right;">
1.5
</td>
<td style="text-align:right;">
16.3
</td>
<td style="text-align:right;">
14.10
</td>
<td style="text-align:right;">
29.0
</td>
</tr>
<tr>
<td style="text-align:left;">
</td>
<td style="text-align:left;">
NonCore (Nonmetro)
</td>
<td style="text-align:right;">
18.0
</td>
<td style="text-align:right;">
1.8
</td>
<td style="text-align:right;">
13.2
</td>
<td style="text-align:right;">
16.80
</td>
<td style="text-align:right;">
35.5
</td>
</tr>
</tbody>
</table>

### Firearm Fatalities

The same five year span was used to calculate all firearm fatalities
from the CDC Wonder Data.

# Spatial Data by Census Tract/Block Group

There are several different geospatial analysis that need to be done to
get the spatial and environmental data into this analysis.

## Census Tract GIS Shapefile

The Census tract shapefiles were downloaded from the [TIGER
Shapefile](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html)
website. The individual state census tracts were then
[merged](https://www.esri.com/arcgis-blog/products/arcgis-desktop/mapping/merging-multiple-shapefiles-into-a-single-shapefile/)
in ArcMap 10.8.1. All shapefiles with 0 acres of land area were removed
from analysis (located mostly in coastal counties and in the Great Lakes
Region).

### Census Tract Population

The overall estimatd census block population was pulled from the [2019
American Community Data Survey](https://data.census.gov/cedsci/) on the
census bureau website. Population density (per/km) was calculated from
the total land area of the census block. This shapefile for total
population density was converted into a raster file.

### Current Environmental Hazards

Energy infrastructure and pipeline shapefiles from the [US Energy
Administration](https://www.eia.gov/maps/layer_info-m.php) were accessed
and downloaded into a map. All pipeline shapefiles were buffered to 5
km, and then the raster was clipped by the buffer, and the values for
each county was extracted using zonal statistics at the county level.

### US EPA Environmental Justice Index

Every year, the EPA puts out the
[EJScreen](https://www.epa.gov/ejscreen/download-ejscreen-data)
environmental justice index is a geodatabase that is at the US Census
Tract or Block level. Socio-economics and demographic data are included
(for this study, they were not used, as they were present in the Social
Determinents of Health spreadsheet). Present data risk includes:

-   Percentage of Houses built before 1960 (lead paint proxy).  
-   Lifetime cancer risk from inhalation of air toxics (NATA).  
-   Air toxics respiratory hazard index.  
-   Diesel particulate matter level in air.  
-   PM2.5 levels in air, µg/m3.  
-   Ozone summer seasonal avg
-   Traffic proximity and volume.  
-   Proximity to RMP sites (chemical spill risk locations).
-   Proximity to TSDFs sites (Haz-mat facilities)
-   Proximity to NPL sites (National Priorities List facilities)  
-   Wastewater discharge.

### US EPA Safe Water Drinking Data

The [EPA Safe Water
Dashboard](https://ordspub.epa.gov/ords/sfdw/f?p=108%3A200%3A%3A%3A%3A%3A%3A)
has a quarterly lookup of the total number of drinking water violations
in a specified state, as well as the total amount of nitrate violations,
with the average nitrate value. The total amount of quarterly violations
were averaged over a one year period, along with the nitrate data
values. The data were aggregated by zip code, and then by county.

### US EPA Environmental Quality Index (EQI)

As seen above, the EJ Screen contains mostly air quality parameters
because of many different data overlap concerns and issues. Prior to the
EJScreen, the EPA had an [Environmental Quality
Index](https://www.epa.gov/healthresearch/environmental-quality-index-eqi).
This index quantified environmental risks into five major categories:
air, water, land, built, and sociodemographic environments, at a county
level, calculating and overall principal components value.

### US EPA Future Scenarios

The US EPA has a [Social Vulnerability
Report](https://www.epa.gov/cira/social-vulnerability-report) from their
Climate Change Impacts and Research Analysis group. This report breaks
down future climate risk by census district from:

-   Air Quality and Health  
-   Extreme Temperature and Health  
-   Extreme Temperature and Labor  
-   Coastal Flooding and Property  
-   Inland Flooding and Property

These CSV files were cleaned and merged together in R to get average
data per county for present and future risks.

## Jobs and Economic Indicators

The [Bureau of Economic Analysis](https://apps.bea.gov/itable/index.cfm)
has several different values measuring income, jobs, and personal
finances at a county level data from 2001-2019.

### Farm Income and Debt to Asset Ratio

### Industry Based Job Numbers

Traditionally speaking, rural America relied heavily on manufacturing in
proportion to Urban America. The CAEMP25N data table has all of the jobs
in each county, from the total jobs (Line Code 10), percentages of each
industry were divided by a total, and the linear space time trend
(slope), and initial percentages (intercept) were used for economic
output in these categories:

-   Farm Jobs (Line Code 70)  
-   Mining Jobs (Line Code 200)  
-   Manufacturing Jobs (Line Code 500)

### Overall Industry Salaries

## Aqueduct Water Risk Atlas

The World Resources Institute has an [Aqueduct Water
Resources](https://www.wri.org/applications/aqueduct/water-risk-atlas)
Risk atlas that looks at all of the potential threats that impact water
use both currently and in the future. For 2030 and 2040 data, the RMP
8.5 scenario (worst case projections) for the major variables were
calculated with zonal statistics in ArcMap 10.8.

## Future Economic Data

Future scenarios from the RMP 8.5, were used from the “Estimating
Economic Damage from Climate Change in the United States” by Hsiang,
Kopp, Rising, Jina et al. (2017). There is a [Zenodo
repository](https://zenodo.org/communities/economic-damage-from-climate-change-usa/?page=1&size=20)
that has the downloadable percentiles (q50 is used in this analysis, as
the likely middle ground) from multiple Monte Carlo simulations at the
county level for three different time periods (2020-2039), (2040-2059),
(2080-2099) for:

-   Future Crop Yields  
-   Violent Crime Futures  
-   Property Crime Futures
-   High Risk Job Hour Lost  
-   Low Risk Job Hour Lost  
-   Age related Mortality  
-   All-age mortality

## Land Use Change

### Percent Cropland Lost and Gained

The [Resource Watch Land Cover
Dataset](https://www.researchsquare.com/article/rs-294463/v1) has 30 m
satellite resolution data that looks at cropland gained (from 2000-2003
and 2016-2019) over a 19 year period. Both of these rasters are averaged
and clipped to the county level.

## 100 Year Floodplain DEM

These mapping products were derived through terrain analysis and a
technique of pattern classification performed on [hydrologically
conditioned
DEMs](https://data.4tu.nl/articles/dataset/100-year_flood_susceptibility_maps_for_the_continental_U_S_derived_with_a_geomorphic_method/12693680/1?file=24033335)
by Manfreda, S., and Troy, T.J., in 2017.
