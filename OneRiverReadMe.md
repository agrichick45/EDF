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
    -   [Deaths of Despair and Suicide Trend and
        Patterns](#deaths-of-despair-and-suicide-trend-and-patterns)
        -   [Death of Despair](#death-of-despair)
    -   [Including Plots](#including-plots)

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

## Deaths of Despair and Suicide Trend and Patterns

### Death of Despair

Defined as Drug Overdoses, Alcohol Related Deaths, Suicides, and
Homicides, getting reliable county level estimates can be difficult,
especially in rural areas. The CDC suppresses any county information
where there are not at least 10 of each individual type of deaths. In
areas with low population density, it can take 20+ years to get to 10 of
these deaths. So, to fill in these blank data rates, the [2013 Urban and
Rural
classification](https://www.cdc.gov/nchs/data_access/urban_rural.htm)
average values were used by county type (Metropolitan Core,
Micropolitan, non-core, etc.) as a substitution. This was done in about
100 columns.

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

## Including Plots

You can also embed plots, for example:

![](OneRiverReadMe_files/figure-gfm/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
