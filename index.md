**Andy Green**  
**12/21/2020**

*I completed this analysis as part of my final project for course PPOL 563: Data Visualization for Data Science, at Georgetown University in Fall 2020. The code, raw data, and Tableau workbooks used to produce the visualizations on this page can all be found in the repository at the "View on GitHub" link above.*

<br>

## Introduction

The Consumer Financial Protection Bureau describes the mortgage market as “the single largest market for consumer financial products and services in the United States.”<sup>[1](#footnote1)</sup>  It is estimated that 37% of all households had at least one mortgage on their property as of 2015, as compared with 26% of households that own their home outright, and 37% that rent.<sup>[2](#footnote2)</sup>  Due to the prevalence of mortgages and the high cost of purchasing a home relative to other consumer spending, mortgages are also responsible for an outsized portion of Americans’ total household debt. The Federal Reserve Bank of New York estimates that mortgage debt accounts for about $9.8T of $14.3T in total household debt (69%), significantly eclipsing the next largest categories of student loan debt ($1.54T) and auto loan debt ($1.34T).<sup>[3](#footnote3)</sup>

In addition to their outsized role in household debt, mortgages also play a crucial role in allowing consumers to build wealth. As of 2016, housing made up roughly 60% of the median family’s assets.<sup>[4](#footnote4)</sup>  Additionally, economists argue that investing in homeownership generates strong financial returns relative to other investment options, and that the wealth-building potential of homeownership makes it a key lever for enabling families to achieve the American Dream.<sup>[5](#footnote5)</sup>

Given the integral role homeownership plays in building wealth, it is notable that significant disparities exist in homeownership rates between race and ethnicity groups. Among families under 35 years old, 46% of white families own their home, as compared to 17% of Black families and 28% of Hispanic families.<sup>[6](#footnote6)</sup>  Homeownership rates increase for all race/ethnicity groups as families get older, but significant disparities persist. Among families between the ages of 35 and 54, 73% of white families own their home, as compared to 50% of Black families and 52% of Hispanic families.<sup>[7](#footnote7)</sup>  Research shows that these disparities in homeownership rates play a crucial role in contributing to the overall racial wealth gap in the United States, whereby the median white family has roughly 8x as much wealth as the median Black family and 5x as much wealth as the median Hispanic family.<sup>[8](#footnote8)</sup> 

Over the course of this analysis, I explore how these disparities by race and ethnicity play out in terms of mortgage applications, focusing specifically on applications for new home purchases in Washington, D.C. in 2017. I leverage data on mortgage applications that were collected under the Home Mortgage Disclosure Act (HMDA), whereby financial institutions must collect and disclose loan-level data on mortgage applications they receive from consumers.<sup>[9](#footnote9)</sup>   This is a particularly rich data source, containing information such as the dollar value of the loan, the race/ethnicity of the applicant(s), and the outcome of the application, for the vast majority of mortgage applications submitted in the United States.<sup>[10](#footnote10)</sup>  I use these data to investigate disparities in the rates at which consumers in various race/ethnicity groups apply for mortgages, the dollar value of the loans they apply for, and the frequency with which they are denied loans. (For more information on how I preprocessed the data prior to conducting these analyses, please refer to Appendix A).

Additionally, because the dataset includes information on the census tract in which the property is located, I am able to analyze the role of race and ethnicity in mortgage applications from a spatial standpoint. Specifically, I analyze how the composition of applications by race and ethnicity in any given census tract compares to the current population demographics of that tract. Such comparisons can provide additional context to some of the district-wide trends highlighted by other portions of the analysis, and they help highlight which parts of the city may be experiencing demographic changes. The findings from this portion of the analysis may be relevant to conversations about gentrification and cultural displacement in Washington, D.C.

<br>

## Visualizations – Disparities by Race and Ethnicity

The first portion of my analysis focuses on the rates at which consumers in various race/ethnicity groups apply for mortgages. I start by calculating the percentage of mortgage applications for new home purchases that are made by consumers in each race/ethnicity group. These percentages are then compared with demographic data on the population of Washington, D.C. by race and ethnicity,<sup>[11](#footnote11)</sup>  to identify which groups are over-represented or under-represented in mortgage applications relative to the total population. The results are shown in Figure 1.

<br>

*Figure 1 – Disparities in Application Rates by Race and Ethnicity*

[![](/race_ethnicity_applications.png)](https://github.com/andygreen-1/HMDA_Data_Race_Ethnicity/blob/gh-pages/race_ethnicity_applications.png)


The graph shows significant disparities in application rates by race and ethnicity. While 45% of Washington D.C.’s population identifies as Black, only 19% of applications were from Black consumers. Hispanic consumers were also under-represented, making up only 6% of applications, but 11% of the total population. On the other hand, 60% of applications were from white consumers, despite only 37% of the population identifying as white. 

Of course, one year of data on mortgage applications is not necessarily a perfect proxy for overall homeownership, as it doesn’t take into account any preexisting differences in homeownership among different race/ethnicity groups. Since Washington, D.C.’s population growth in recent years has been driven by an influx of white residents,<sup>[12](#footnote12)</sup>  it is possible that many Black residents already have mortgages or own their homes outright, and the disparities we see in mortgage applications in 2017 are more reflective of these demographic changes. However, the fact that the results in this analysis comport with what we know about disparities in homeownership rates – both nationally and in Washington, D.C. specifically<sup>[13](#footnote13)</sup>  – suggests that the disparities highlighted by Figure 1 may be significant.

The next portion of my analysis focuses on disparities in the dollar value of loans that consumers of different race/ethnicity groups have applied for. Figure 2 uses a box plot to help visualize these disparities. For each group, the bottom and top of the box indicate the values at the 25th and 75th percentile, respectively, while the line in the middle of the box represents the median value. The points located above the vertical line extending from each box represent values that are significantly larger than the bulk of the distribution for that group.

<br>

*Figure 2 – Box Plot of Loan Amount by Race/Ethnicity*

[![](/race_ethnicity_loan_amount.png)](https://github.com/andygreen-1/HMDA_Data_Race_Ethnicity/blob/gh-pages/race_ethnicity_loan_amount.png)


The plot shows significant disparities in the dollar value of loans by race and ethnicity. White consumers have the highest median loan value ($499K), followed by Asian consumers ($383K), Hispanic consumers ($352K), and Black consumers ($320K). Additionally, the box plot shows a significant number of applications for loans valued between $1M and $2M for white consumers, but relatively few loans for other race/ethnicity groups in this range.

The next portion of my analysis investigates disparities in the rates at which consumers in different race/ethnicity groups have their applications denied. Figure 3 shows the denial rates for each of the race/ethnicity groups.

<br>

*Figure 3 – Denial Rates by Race/Ethnicity*

[![](/race_ethnicity_denials.png)](https://github.com/andygreen-1/HMDA_Data_Race_Ethnicity/blob/gh-pages/race_ethnicity_denials.png)


The chart shows that Black and Hispanic consumers are denied at significantly higher rates than white and Asian consumers. Among all applications submitted by Black consumers, 11.2% were denied, while 9% of all applications submitted by Hispanic consumers were denied. On the other hand, only 3.9% of white consumers’ applications and 5.9% of Asian consumers’ applications were denied.

Taking it a step further, I also investigate the reasons why consumers were denied on their mortgage applications, and whether these reasons may differ by race/ethnicity group. Figure 4 shows the breakdown of the reasons why applicants were denied loans for each race/ethnicity group.

<br>

*Figure 4 – Breakdown of Denial Reasons by Race/Ethnicity*

<iframe seamless frameborder="0" src="https://public.tableau.com/views/treemap_denial_reasons_16083227565410/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '900' scrolling='no' ></iframe>

*If there any issues with rendering the above dashboard on your screen, please use* [*this link*](https://public.tableau.com/views/treemap_denial_reasons_16083227565410/Dashboard1?:language=en&:display_count=y&:origin=viz_share_link) *to view it directly on Tableau Public.*

<br>

The visualization shows that denial reasons tend to be relatively similar across race/ethnicity groups, with a few exceptions. For Black, white, and Asian consumers, collateral and debt-to-income ratio are the two largest categories. For Hispanic consumers, collateral is the second largest category, while the “Other” category is the largest. It also seems as though credit history is a significant factor for Black and Hispanic consumers (16% for each), while it’s less prevalent for white (8%) and Asian consumers (6%).

It’s worth noting that the sample size for this portion of the analysis is relatively small. In addition to the fact that we’re now working with a small percentage of all applications (i.e., just the ones that were denied), the financial institutions are also not required to provide their reason for denial in the HMDA data, and many choose not to do so. As a result, further analysis should be done with a larger sample size before making any concrete conclusions on this particular portion of the analysis.

<br>

## Visualizations – Spatial Analysis

Because the dataset includes information on the location of each prospective home purchase, I can also investigate the role of race and ethnicity in mortgage applications from a spatial standpoint. I begin by analyzing how the composition of applications by race/ethnicity in a geographic area compares to the existing population demographics of that area. Figure 5 explores this relationship at the census tract level. Specifically, it shows the relationship between the percentage of a census tract’s population that is non-white (i.e., all groups except for white, non-Hispanic; shown on the x-axis), and the percentage of applications from white consumers (shown on the y-axis). Using the dropdown menu on the right, you can change the dashboard such that the y-axis shows the percentage of applications from Black consumers, as opposed to white consumers; the x-axis measure does not change.

If you live in Washington, D.C. and are curious where your census tract falls on the graph, the dashboard contains functionality to help you find it. You can start by using [this handy tool](https://geocoding.geo.census.gov/geocoder/geographies/address?form) to look up the census tract number associated with your address. After entering your address in the tool, you can scroll down to the “Census Tracts” section and look for the number listed next to “BASENAME”. Then, you can enter this number in the “Highlight Census Tract” field on the right side of the dashboard to locate your tract.

<br>

*Figure 5 – Relationship Between Population Demographics and Applicant Demographics by Census Tract*

<iframe seamless frameborder="0" src="https://public.tableau.com/views/CensusTractApplicationsbyRaceEthnicity/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '900' scrolling='no' ></iframe>

*If there any issues with rendering the above dashboard on your screen, please use* [*this link*](https://public.tableau.com/views/CensusTractApplicationsbyRaceEthnicity/Dashboard1?:language=en&:display_count=y&:origin=viz_share_link) *to view it directly on Tableau Public.*

There are two main insights that can be gathered from the graph. First, the graph shows that white consumers make up a majority of applications in most census tracts in Washington, D.C. This is indicated visually by the fact that most points are located above the 50% value on the y-axis. This finding also tracks with the top-line stat that white consumers accounted for 60% of all applications (as indicated by Figure 1). Second, the graph shows that applications by white consumers only begin to drop off in census tracts with a very high percentage of non-white residents. This is indicated visually by the steep drop-off in the (theoretical) trend line along the right side of the graph.

Taking it a step further, I also analyze how these relationships play out geographically across Washington, D.C. The map in Figure 6 contains three different metrics, and it is color-coded according to which of the three is selected in the dropdown menu on the right. The map shows which tracts have the highest percentage of white applicants, which tracts have the highest percentage of white residents, and which tracts have the largest discrepancies between the two. The map also contains the same functionality for highlighting a given census tract that was present in the earlier dashboard.

<br>

*Figure 6 – Map of Population Demographics and Applicant Demographics by Census Tract*

<iframe seamless frameborder="0" src="https://public.tableau.com/views/DCMapMortgageApplicationsbyRaceEthnicity/Dashboard1?:embed=yes&:display_count=yes&:showVizHome=no" width = '1000' height = '900' scrolling='no' ></iframe>

*If there any issues with rendering the above dashboard on your screen, please use* [*this link*](https://public.tableau.com/views/DCMapMortgageApplicationsbyRaceEthnicity/Dashboard1?:language=en&:display_count=y&:origin=viz_share_link) *to view it directly on Tableau Public.*

Toggling through the different metrics contained in the dropdown menu highlights a few main points. First, the “Percentage of Applications – White Consumers” metric shows that white consumers make up a large proportion of applications across much of Washington, D.C., with the exception of the census tracts in wards 7 and 8 (East of the Anacostia River, or the Southeast portion of the map). These census tracts, which have predominantly non-white populations, correspond with those in the bottom-right section of the graph in Figure 2. Next, the “Percentage of Population – White Residents” metric shows that the census tracts in Northwest D.C. and the Capitol Hill area have large proportions of white residents, while much of the rest of the city does not. Finally, the “Difference of Application and Population Percentages” metric, which is calculated by simply subtracting the population percentage metric from the application percentage metric, highlights the neighborhoods that have a large percentage of applications from white consumers, despite having a relatively small proportion of white residents currently. The map shows that Northeast D.C., and some of the Northwest neighborhoods that are close to Northeast, are the areas with the largest discrepancies between these two metrics. The census tract with the largest discrepancy is 79.03, which is near RFK Stadium in Northeast D.C. In this tract, 17% of the population is white, while 90% of applications came from white consumers. 

The trends highlighted by this portion of the analysis may be relevant to conversations about gentrification and cultural displacement in the city. A recent study from the National Community Reinvestment Coalition (NCRC) found that Washington, D.C. was the most gentrified city in the country by some measures, and that gentrification was accompanied by the displacement of 20,000 Black residents between 2000 and 2013.<sup>[14](#footnote14)</sup>  While the measures contained in this analysis are certainly not direct measures of gentrification or cultural displacement, they may serve as rough indicators of neighborhoods that may be at risk of experiencing these phenomena. Indeed, the NCRC’s map showing which parts of the city experienced gentrification and Black displacement appear to line up moderately well with the graph in Figure 6.<sup>[15](#footnote15)</sup> 

<br>

<br>

## Appendix A: Filtering the Data and Constructing the Race/Ethnicity Variable

For the purposes of this analysis, the raw dataset was filtered to include only the following observations:

- Loans for 1-4 family dwellings (as opposed to multifamily dwellings or manufactured housing)
- Loans for new home purchases (as opposed to refinancing or taking out a loan for home improvements)
- Loans for under $50M (removing a handful of outliers with huge loan values)
- Loans where the race and ethnicity of the applicant(s) are known
  - Among observations where the race and ethnicity of the applicant(s) are known, the 4 groups included in the visualizations account for about 92% of all observations. The remaining 8% of observations are split between American Indian / Alaskan Native, Native Hawaiian or Other Pacific Islander, and Multiple Races. These observations were included in the analysis itself, but do not appear in the final visualizations.












## References

<a name="footnote1">1</a>: Consumer Financial Protection Bureau. (2019, January). *Ability-to-Repay and Qualified Mortgage Rule Assessment Report.* Consumer Financial Protection Bureau. [https://files.consumerfinance.gov/f/documents/cfpb_ability-to-repay-qualified-mortgage_assessment-report.pdf.](https://files.consumerfinance.gov/f/documents/cfpb_ability-to-repay-qualified-mortgage_assessment-report.pdf)

<a name="footnote2">2</a>: Levitin, A. J. (2018). *Consumer finance markets and regulation.* Wolters Kluwer.  

<a name="footnote3">3</a>: Federal Reserve Bank of New York. (2020, August 6). *Total Household Debt Decreased in Q2 2020, Marking First Decline Since 2014.* Federal Reserve Bank of New York. [https://www.newyorkfed.org/newsevents/news/research/2020/20200806.](https://www.newyorkfed.org/newsevents/news/research/2020/20200806)

<a name="footnote4">4</a>: Bricker, J., Moore, K. B., & Thompson, J. P. (2019). Trends in Household Portfolio Composition. *Finance and Economics Discussion Series, 2019(069)*, 1–51. [https://doi.org/10.17016/feds.2019.069.](https://doi.org/10.17016/feds.2019.069)

<a name="footnote5">5</a>: Goodman, L. S., & Mayer, C. (2018). Homeownership and the American Dream. *Journal of Economic Perspectives, 32(1)*, 31–58. [https://doi.org/10.1257/jep.32.1.31.](https://doi.org/10.1257/jep.32.1.31)

<a name="footnote6">6</a>: Bhutta, N., Chang, A. C., Dettling, L. J., & Hsu, J. W. (2020, September 28). *Disparities in Wealth by Race and Ethnicity in the 2019 Survey of Consumer Finances.* Board of Governors of the Federal Reserve System. [https://www.federalreserve.gov/econres/notes/feds-notes/disparities-in-wealth-by-race-and-ethnicity-in-the-2019-survey-of-consumer-finances-20200928.htm.](https://www.federalreserve.gov/econres/notes/feds-notes/disparities-in-wealth-by-race-and-ethnicity-in-the-2019-survey-of-consumer-finances-20200928.htm)

<a name="footnote7">7</a>: Ibid.

<a name="footnote8">8</a>: Ibid.

<a name="footnote9">9</a>: Consumer Financial Protection Bureau. *The Home Mortgage Disclosure Act.* Consumer Financial Protection Bureau. [https://www.consumerfinance.gov/data-research/hmda/.](https://www.consumerfinance.gov/data-research/hmda/)

<a name="footnote10">10</a>: Ibid.

<a name="footnote11">11</a>: Census Bureau. *Hispanic or Latino Origin by Race: American Community Survey, 2017.* Census Bureau. [https://data.census.gov/cedsci/table?g=0400000US11&tid=ACSDT1Y2017.B03002&hidePreview=false.](https://data.census.gov/cedsci/table?g=0400000US11&tid=ACSDT1Y2017.B03002&hidePreview=false.)

<a name="footnote12">12</a>: Rabinowitz, K. (2017, March 2). *A decade of demographic change in D.C.: Which neighborhoods have changed the most?* D.C. Policy Center. [https://www.dcpolicycenter.org/publications/demographic-change-d-c-neighborhoods/.](https://www.dcpolicycenter.org/publications/demographic-change-d-c-neighborhoods/)

<a name="footnote13">13</a>: Salviati, C. (2017, August 21). *The Racial Divide in Homeownership.* Apartment List. [https://www.apartmentlist.com/research/racial-divide-homeownership.](https://www.apartmentlist.com/research/racial-divide-homeownership)

<a name="footnote14">14</a>: Richardson, J., Mitchell, B., & Franco, J. (2019, March 19). *Shifting Neighborhoods: Gentrification and cultural displacement in American cities.* National Community Reinvestment Coalition. [https://ncrc.org/gentrification/.](https://ncrc.org/gentrification/)

<a name="footnote15">15</a>: Ibid.
