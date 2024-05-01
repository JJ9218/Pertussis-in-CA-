# Pertussis in CA

## Table of Contents

- [Background](#background)
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Key Aim](#key-aim)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)

### Background
Pertussis, also reffered to as whooping cough, is a highly contagious airborne disease transmitted from person to person. The bacteria that causes whooping cough, Bordetella pertussis, disrupts the upper respiratory system by releasing toxins that cause airways to swell and damage to the cilia. Symptoms typically develop within 5-10 days of infection, manifesting in its early stages as a mild cough, low-grade fever, runny or stuffed nose, and apnea. In its later stages (1-2 weeks after infection), symptoms may develop into uncontrolled coughing fits (paroxysms). Coughing fits can last up to 10 weeks, but typically occurs between 1-6 weeks. Younger children are disproportionately impacted by severe pertussis, and it is recommended for pregnant women in their third trimester to receive the Tdap vaccine booster, and for infants to receive DTaP series as early as 6 weeks. 

In California, over 11,000 cases were reported in 2014, resulting in two infant deaths and hundreds of hospitilizations. This highlighted the importance of increasing vaccination rates for child care facilities and primary schools, as schools with low vaccination rates have increased risk of pertussis outbreaks. Pertussis is a vaccine-preventable disease and with effective measures taken for schools and child care facilities, children are at a lower risk of being exposed and infected with the bacterial disease. 

### Project Overview
This project aims to address the importance of the DTaP vaccine for children in child care facilities and primary schools and its impact on reducing pertussis outbreaks in schools. It analyzes the correlation between average vaccination rates and case counts for child care and kindergarten schools from 2011-2020. 

### Data Sources
The data is sourced from California's Department of Public Health. By law, students are required to provide proof of immunization under the California Health and Safety Code Section 120325-75. Along with this policy, the California Code of Regulation Section 6075 requires annual reporting of student immuninizations. 
1. Data reports for [Kindergarten](https://www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/tk-12-reports.aspx#) vaccination rates
2. Data reports for [Child Care Facilities](https://www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/childcare-reports.aspx#) vaccination rates
3. Data reports for [Vaccine-Preventable Disease](https://data.chhs.ca.gov/dataset/vaccine-preventable-disease-cases-by-county-and-year) cases by county and year

### Tools
 - Excel- Data Inspection, Data Cleaning
  - Python - Data Cleaning, Data Analysis, and Visualizations

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
The initial step within this data analysis was configuring the mean of case counts and vaccination rates for child care facilities and kindergarten schools in CA every year from 2011-2020. 
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
For both child care facilities and kindergarten schools in CA, there was a steady increase in vaccination rates from 2011-2020 overall.
![kcplot](https://github.com/JJ9218/Pertussis-in-CA-/assets/163039134/ac3bdf94-2fa2-4e4d-8451-5eadac0f5ee2)

However, the case counts did not reflect any direct correlation to vaccination rates over the years.  
![CaseCounts](https://github.com/JJ9218/Pertussis-in-CA-/assets/163039134/40fc8fe2-4363-4576-9152-19a1eb380319)

TO statistically assess this, a linear regression was condcuted to consider any potential correlation between vaccination rates and case counts of pertussis from 2011-2020. This table indicates a strong correlation of an increase of vaccination rates over the years, yet rejects the hypothesis of case counts decreasing as vaccination rates increased over the years. 

![Correlation](https://github.com/JJ9218/Pertussis-in-CA-/assets/163039134/ec700cf2-0e92-437c-a9ca-bd9456677b7f)

Results indicate that there was no significant correlation between DTaP vaccination rates and pertussis case counts over the years. The hypothesized outcome would have reflected a negative coreelation, where DTaP vaccination rates would be set an increasing rate while pertussis case counts decreased over the years. 

These reults highlight that there is further research to be conducted as to consistent incidence of pertussis cases regardless of increasing vaccination rates. 


### Recommendations
Some considerations: 
Given the results, were there other ways that could have prevented pertussis cases? mechanisms for reducing airborne pathogens in schools (air filters), ventilation. Which schools are being disproportionately impacted from pertussis cases, and should there be an assessment for ventilation/filtration systems within the schools? Importance of ventilation and filtration for airborne pathogens. study with boston schools.
Schools should report cases as well.
Questions to CDPH guidance


### Limitations
When it comes to case rates, we have do not have data specifying age demographics. We know that pertussis disporotionally impacts children, especially in childcare and kindergarten. While we have vaccination rates specifically for this age group, this analysis would be more accurate with the inclusion of age groups or grade level to fully confirm the association between vaccine rates and case counts. California's Department of Public Health indicate that in 2014, over 11,000 cases were reported including 2 infant deaths. This outbreak also led to hundreds of hospitilzations. When vaccination rates were low in schools, there was an increased risk for infants and children becoming infected wih pertussis. While we know young children are disporportionately impacted with pertussis cases, our analysis would be strengthened if age demographics or grade level was incldued in the pertussis case count dataset.  

Another limitation is the amount of schools who did not report vaccination rates. For kindegarten schools in CA, 4.2% failed to report vaccination rates, and 8.3% for childcare facilities. While this number is relatively low in comparison to the schools and facilities that have reported, having this information for the analysis would have strengthened the hypothesis of vaccination rates having an impact on cases. 

### References
1. CDC. “About Whooping Cough (Pertussis).” Centers for Disease Control and Prevention, Centers for Disease Control and Prevention, 4 Aug. 2022, www.cdc.gov/pertussis/about/index.html.
2. California Department of Public Health. “Pertussis.” California Department of Public Health, www.cdph.ca.gov/Programs/CID/DCDC/pages/immunization/pertussis.aspx#.
3. California Department of Public Health. “Transitional Kindergarten & 7th Grade-Reports.” California Department of Public Health, www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/tk-12-reports.aspx#.
4. California Department of Public Health. “Child Care/ Preschool Reporting Data.” California Department of Public Health, www.cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/School/childcare-reports.aspx#.
5. California Department of Public Health. “Vaccine Preventable Disease Cases by County and Year - Dataset - California Health and Human Services Open Data Portal.” California Health and Human Services Open Data Portal, data.chhs.ca.gov/dataset/vaccine-preventable-disease-cases-by-county-and-year.
