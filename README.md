# Data Analysis Internship Overview
For this project I used the data I obtained from my internship with Sally Owens for Illinois State Senate to create a map to show how many voter there were per zip code in the 46th District. I was only able to get the data from the Peoria County Election Commission, so therefore it isn't the complete set of voter data in the district.
Since this data is straight from the Peoria County Election Commission, it is a reputable source. Each day I would be sent a small file with the voter data from the day before and would give a report, via a pivot table in a Microsoft Execl Sheet to Sally Owens and her team to get an understanding of where they should do more outreach.
## Daily Process
When I would get the daily file it would have information on the voter from the day before, so I would have to filter to data to get what I need. I would filter the data to get the voter information from just the 46th district. Once it was filtered and in a separtate sheet, I created a pivot table showing how many voters there were in each precinct and how many outstanding vote by mail ballots there were. 
## End of Election Project
### SQL
At the end of the election we got a complete file with every voter, which ended up being around 118,600 voters total. Since this was a large dataset I opted to use BigQuery rather than Microsoft Excel. Once I created a dataset and table for the data a queried to get the information I wanted.
```{SQL}
select 
LastName, FirstName, MiddleName, ResidenceAddress, ResidenceCity, ResidenceState, ResidenceZipCode, PrecinctID, VoterID, DistrictName_2
from
`corded-rope-430400-g3.voter_data.11_11`
where 
DistrictName_2 = '46th Legis.'
```
This query gave me the narrowed down fields I wanted so that I had a more managable dataset. I downloaded the CSV file of the results that contained just the data from the 46th district.
### Tableau Data Vizualization
- When I finished downloading the new dataset I uploaded it to TableauPublic to create a data viz to show how many votes there were per zipcode in an interactive map. I had to change the ResidenceCity, ResidenceState, and ResidenceZipCode from strings to their own geographical roles so that they could be used to create the map. 
- To get the map started, I drug the Residence State into the Rows section (columns turn to longitude and rows turn into latitude) which gave me the map of a highlighted map of Illinois. To get an outline of the Zip Codes I drug the Residence Zip Codes to the detail section.
- I wanted to add the count of each voter ID (how many votes there are), so I drug it to the color section of zip code layer and picked a gradient so there was a clear visualization of which zip codes had the most votes. This also made it so when you hover over each section in shows a label with the state, zip code, and votes. 
- Additionally I added points labeling each city to help better vizualize the areas these zip codes  are. There is a legend on the side to make finding each city easier. Here is a link to the project
<https://public.tableau.com/app/profile/mia.craghead/viz/Map-CountofVotersperZipCodeinthe46thDistrictIllinois/Dashboard1>
