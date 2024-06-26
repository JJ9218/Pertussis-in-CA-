# Pertussis Outbreaks in California
J.Jones, MPH

## Table of Contents

- [Background](#background)
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Key Aim](#key-aim)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Limitations](#limitations)
- [Recommendations](#recommendations)
- [References](#references)

### Background
Pertussis, also reffered to as whooping cough, is a highly contagious airborne disease transmitted from person to person. The bacteria that causes whooping cough, Bordetella pertussis, disrupts the upper respiratory system by releasing toxins that cause airways to swell and damage to the cilia. Symptoms typically develop within 5-10 days of infection, manifesting in its early stages as a mild cough, low-grade fever, runny or stuffed nose, and apnea. In its later stages (1-2 weeks after infection), symptoms may develop into uncontrolled coughing fits (paroxysms). Coughing fits can last up to 10 weeks, but typically occurs between 1-6 weeks. Younger children are disproportionately impacted by severe pertussis; it is recommended for pregnant women in their third trimester to receive the Tdap vaccine booster, and for infants to receive DTaP series as early as 6 weeks. 

In California, over 11,000 cases were reported in 2014, resulting in two infant deaths and hundreds of hospitilizations. This highlighted the importance of increasing vaccination rates for child care facilities and primary schools, as schools with low vaccination rates have increased risk of pertussis outbreaks. Pertussis is a vaccine-preventable disease and with effective measures taken for schools and child care facilities, children are at a lower risk of being exposed and infected with the bacterial disease. 

### Project Overview
This project aims to address the importance of the DTaP vaccine for children in child care facilities and primary schools and its impact on reducing pertussis outbreaks. It analyzes the correlation between average vaccination rates and case counts for child care and kindergarten schools from 2011-2020. 

### Data Sources
The data is sourced from California's Department of Public Health (CDPH). By law, students are required to provide proof of immunization under the California Health and Safety Code Section 120325-75. Along with this policy, the California Code of Regulation Section 6075 requires annual reporting of student immuninizations. CDPH reports cases and outbreaks for infectious diseases of California residents by the disease, county, and year. Laboratories and health care systems are responsible for reporting suspected and confirmed cases to their local health department, which is then reported back to CDPH. 
1. Data reports for [Kindergarten](https://www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/tk-12-reports.aspx#) vaccination rates
2. Data reports for [Child Care Facilities](https://www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/childcare-reports.aspx#) vaccination rates
3. Data reports for [Vaccine-Preventable Disease](https://data.chhs.ca.gov/dataset/vaccine-preventable-disease-cases-by-county-and-year) cases by county and year

### Tools
 - Excel- Data inspection, data cleaning
 - Python - Data cleaning, data analysis, and visualizations

### Data Cleaning and Preparation
The following was performed for data cleaning and preparation:

1. Data inspection
2. Removing unnecessary data
3. Handling missing data
4. Data cleaning and formatting
5. Data merging

### Key Aim
This project aimed to assess if vaccination rates in child care facilties and kindergaten schools had an impact on decreasing pertussis case counts. Conducting this through a statistical analysis can help us make informed decisions such as assessing the effectiveness of preventative measures for infectious diseases. 

### Data Analysis
The initial step within this data analysis was configuring mean case counts and vaccination rates for CA child care facilities and kindergarten schools every year from 2011-2020. 
```Python
kcplot= kcpltmerged
kcplot = kcpltmerged.groupby('Year').mean('DTP_percent')
kcplot
```
Following this, a linear regression was run to determine a potential correlation between vaccination rates and case counts over the years. 
```Python
completemerge2.corr()
```

### Results
For child care facilities and kindergarten schools in CA, there was a steady increase in vaccination rates from 2013-2016. Vaccination rates remained relatively high (over 95%) from 2016-2020. 
![kcplot](https://github.com/JJ9218/Pertussis-in-CA-/assets/163039134/ac3bdf94-2fa2-4e4d-8451-5eadac0f5ee2)

However, the case counts did not reflect any direct correlation to vaccination rates over the years.  
![CaseCounts](https://github.com/JJ9218/Pertussis-in-CA-/assets/163039134/40fc8fe2-4363-4576-9152-19a1eb380319)

To statistically assess this, a linear regression was conducted to consider any potential correlation between vaccination rates and case counts of pertussis from 2011-2020. This table indicates a strong correlation of an increase of vaccination rates over the years, yet rejects the hypothesis of case counts decreasing as vaccination rates increased by the year. 

![Correlation](https://github.com/JJ9218/Pertussis-in-CA-/assets/163039134/ec700cf2-0e92-437c-a9ca-bd9456677b7f)
![Screenshot (10)](https://github.com/JJ9218/Pertussis-in-CA-/assets/163039134/8c853db9-a900-4ec4-bce9-1410ad4ce580)


The hypothesized outcome would have reflected a negative correlation, where DTaP vaccination rates would be set at an increasing rate as pertussis case counts decreased over the years. Results indicate that the correlation between DTaP vaccination rates and pertussis case counts from 2011-2020 did not indicate the intended negative correlation. 

These reults highlight that there is further research needed to determine the reasoning for a consistent incidence of pertussis cases every 3-5 years regardless of increasing vaccination rates. 

### Limitations
California's Department of Public Health reported an increased risk for infants and children becoming infected wih pertussis when vaccination rates were low in schools. The results of this analysis does not support this claim, however, there were several limitations within this dataset that may have impacted this outcome. The vaccine-preventable disease dataset lacked age demographic data which could have given a more accurate determination of which peturssis cases came from child care facilities and schools. Although it is known that pertussis disproportionally impacts children, especially in child care and kindergarten, age demographics within this dataset could have further strengthened an association between vaccine rates and case counts. Other demographic data missing is race and a variable identifying which counties have a low, middle, or high socioeconomic status. It is crucial for the inclusion of these variables to identify potential populations that may be disproportionately impacted from pertussis outbreaks and to adjust approaches to prevention mechanisms. 

Another limitation is the amount of schools who did not report vaccination rates. For kindegarten schools in CA, 4.2% failed to report vaccination rates, and 8.3% for child care facilities. While this number is relatively low in comparison to the schools and facilities that have reported, having this information for the analysis would have strengthened the hypothesis of vaccination rates having an impact on cases. 

### Recommendations
In addition to the inclusion of variables limited in the data sources, CDPH should consider other prevention mechanisms that can decrease airborne pathogens in chidcare facilities and schools. Assessing and implementing ventilation and air filtration systems can be crucial in reducing the spread of airborne diseases including pertussis. Several studies have found the significance of high-grade recirculating heating, ventilating, and air-conditioning (HVAC) particle filters reducing infectious airborne pathogens in indoor spaces. The U.S. Department of Education indicate that improving indoor air quality can reduce airborne disease outbreaks. Mechanisms such as implementing MERV-13 or higher filters within HVAC systems, monitoring CO2 levels, repairing windows for more ventilation, and frequent inspection and management of ventilation and air filtration systems have an impact on ensuring a safer environment for students and staff. 
CDPH should expand their guidance by applying the "Swiss Cheese" model to their approach. The Swiss Cheese model highlights that there are multiple important factors in reducing the spread of infectious diseases, and indicate that an as an addition to being vaccinated, we should also improve other mechanisms for preventing outbreaks (stay at home if you are sick, improve ventilation and filtration in schools, etc.). Assessing these additional mechanisms relating to cleaner indoor air could potentially reduce the incidence of pertussis every 3-5 years in CA. 

Under Title 17, California Code of Regulations §2508 requires schools to report disease outbreaks, including pertussis cases, to their local health departments. It is recommended for CDPH to report case counts for each school publicly to compare with vaccination rates for schools that are widely accessible to the public. Additionally, case count data could also include age and socioeconomic demographics to consider communities disproportionately impacted and an evaluation of refined preventionary mechanisms to assess improvements and barriers. 

### References
1. CDC. “About Whooping Cough (Pertussis).” Centers for Disease Control and Prevention, Centers for Disease Control and Prevention, 4 Aug. 2022, www.cdc.gov/pertussis/about/index.html.
2. California Department of Public Health. “Pertussis.” California Department of Public Health, www.cdph.ca.gov/Programs/CID/DCDC/pages/immunization/pertussis.aspx#.
3. California Department of Public Health. “Transitional Kindergarten & 7th Grade-Reports.” California Department of Public Health, www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/tk-12-reports.aspx#.
4. California Department of Public Health. “Child Care/ Preschool Reporting Data.” California Department of Public Health, www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/childcare-reports.aspx#.
5. California Department of Public Health. “Vaccine Preventable Disease Cases by County and Year - Dataset - California Health and Human Services Open Data Portal.” California Health and Human Services Open Data Portal, data.chhs.ca.gov/dataset/vaccine-preventable-disease-cases-by-county-and-year.
6. “Improving Ventilation in Schools, Colleges, and Universities to Prevent COVID-19.” Improving Ventilation in Schools, Colleges, and Universities to Prevent COVID-19 | U.S. Department of Education, www.ed.gov/improving-ventilation-schools-colleges-and-universities-prevent-covid-19.
7. Azimi, Parham, and Brent Stephens. “HVAC filtration for controlling infectious airborne disease transmission in indoor environments: Predicting risk reductions and operational costs.” Building and environment vol. 70 (2013): 150-160. doi:10.1016/j.buildenv.2013.08.025
8. Roberts, Siobhan. “The Swiss Cheese Model of Pandemic Defense.” The New York Times, The New York Times, 5 Dec. 2020, www.nytimes.com/2020/12/05/health/coronavirus-swiss-cheese-infection-mackay.html.
9. “Disease Information and Exposure Notices for Schools and Child Care.” Disease Information and Exposure Notices for Schools and Child Care - Public Health Providers - County of Santa Clara, publichealthproviders.sccgov.org/schools/exposure-notices-schools-and-child-care#:~:text=Disease%20reporting%20requirements,that%20meet%20the%20criteria%20below.
