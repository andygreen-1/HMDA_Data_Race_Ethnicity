# The Role of Race and Ethnicity in Mortgage Applications in Washington, D.C.

This repository contains the code, raw data, and Tableau workbooks used to produce the visualizations for my final project in course PPOL 563: Data Visualization for Data Science, at Georgetown University in Fall 2020. The project uses data visualization to investigate the role of race and ethnicity in mortgage applications in Washington, D.C. in 2017.

The completed visualizations, along with narrative text providing context and interpretations of the visualizations, can be found on this [GitHub page](https://andygreen-1.github.io/HMDA_Data_Race_Ethnicity/).

You can find a brief summary of the files available in the repository below:

* DC_Mortgage_Data_2017.Rmd: R Markdown file used to clean the data, conduct analyses, and produce the three static visualizations that are part of the project
* Data_Inputs: Directory containing the raw data used to produce the visualizations
    * hmda_2017_dc_all-records_labels.csv: Mortgage application data that makes up the core of the analysis
        * Source: [Consumer Financial Protection Bureau](https://www.consumerfinance.gov/data-research/hmda/historic-data/)
    * dc_demographic_data.csv: Population demographics of Washington, D.C. in 2017
        * Source: [Census ACS](https://data.census.gov/cedsci/table?g=0400000US11&tid=ACSDT1Y2017.B03002&hidePreview=false)
    * Census_Tracts_in_2010-shp: Directory containing the shapefile used to create the map visualization
        * Source: [Open Data DC](https://opendata.dc.gov/datasets/6969dd63c5cb4d6aa32f15effb8311f3_8)
* Data_Outputs: Directory containing a series of .csv files that were exported from the .Rmd file and used in the Tableau workbooks to create the three dynamic visualizations
* Vizzes: Directory containing the three static + three dynamic visualizations that make up the project