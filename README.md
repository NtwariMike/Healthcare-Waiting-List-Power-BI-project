# Healthcare-Waiting-List-Power-BI-project

I created a responsive and dynamic dashboard with a summary page and a detailed page whcih shows key metrics such as average wait list for different age groups, monthly trends etc. For this project we used power BI to create the reports

<img width="666" alt="Cmplete dashboard 2" src="https://github.com/NtwariMike/Healthcare-Waiting-List-Power-BI-project/assets/150134943/57c7e499-ff6e-4bc3-8ed6-343ca6c90ea1">
<img width="670" alt="Complete dasnboard" src="https://github.com/NtwariMike/Healthcare-Waiting-List-Power-BI-project/assets/150134943/74967a7d-fefe-40ae-a4d6-69caf461692c">

## 1.Requirement gathering
### Overall objectives

#### Project goals
- Track the current status of the patient waiting list
- Analyze the historical monthly trend of waiting lists in inpatient and outpatient categories
- Detailed specialty level and age profile analysis

#### Data scope
- 2018-2021

#### Metrics required 
- Average and Median waiting list   
- Current total wait list

#### Views required
- Summary page
- Detailed page for granular analysis

## 2.Data Collection
### The primary data sets used are,
1.	<B>Inpatient:</B> contains data from 2018-2021
2.	<B>Outpatient:</B> Contains data from 2018-2021
3.	<B>Specialty Mapping:</B> Summarizes the specialty names into groups

## 3.Data transformation and modeling

<b>Data type:</b> I changed data types for dates from text to date using locale (English(India))
<b>Combined the two data (Inpatient and outpatient):</b> First I made sure they had the same number of columns and column names, and the column data type had to be the same. I renamed the new data set as <B>ALL_DATA</B> 
### Data Modelling:
Because we have many specialties, so we grouped them to allow us to visualize them.
We created a relationship between all data and specialty mapping based on the specialty name in all_data and specialty in specialty mapping (Many to one relationship)( The arrow has to move from the child table to the parent table)

## 4.Data Visualization Blueprint
- We designed how we would organize our visuals (You get to understand what type of visuals you need to tell your story)
- We designed the background images using the following
  - Looked for nice background images from Stock.Adobe.com
  - Extracted the image colors using Color.adobe.com
  - Created the desired background using Power point/ slides
  - Extracted the ppt/slides background as image
  - Inserted the image in Power BI then disabled all the visual background in Power BI

## 5. Created the Views needed

 ### We designed the visuals needed, we created some maesures to help us display the neccessary data. These are some formulas used
 
 <b>- Switch(expression, value1, result1, value2, result2,….)
 - Values(tablename[Columnname])
 - Edate(startdate, months)
 - Calculate(expression, Condition)
 - SUM(values), AVERAGE(Values), Median(values)
 - IF(ISBLANK(CALCULATE(SUM(tablename[columnname]), tablename[columnname] = condition)), “value to be returned if true”, “value to be returned if false”)</b>

## 6.Summary

Lastly we created two pages:

<b>Summary Page</b>
- <b>Donut chart:</b> Average and Median wait list for case type(Inpatient, outpaient and daycase)
- <b>Barchart:</b> Average or Median wait list of different age groups
- <b>Card:</b> Top 5 specialty with high total wait list
- <b>Line chart:</b> Total monthly trends of wait list per case type

<b>Detailed page
- Matrix table:</b> Contains data for all the wait list in differents periods per case type
