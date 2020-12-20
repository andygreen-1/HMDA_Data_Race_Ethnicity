**Andy Green**  
**12/21/2020**

*I completed this analysis as part of my final project for course PPOL 563: Data Visualization for Data Science. The code, raw data, and Tableau workbooks used to produce the visualizations can all be found in the repository at the "View on GitHub" link at the top of this page.*

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

![](/race_ethnicity_applications.png)

[![](/race_ethnicity_applications.png)](https://github.com/andygreen-1/HMDA_Data_Race_Ethnicity/blob/gh-pages/race_ethnicity_applications.png)







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
