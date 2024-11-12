# Data Analysis Internship Overview
- For this project, I used data obtained from my internship with Sally Owens for Illinois State Senate to create a map showing the number of voters per zip code in the 46th District. I was only able to get data from the Peoria County Election Commission, so this is not the complete set of voter data for the district. Since this data comes directly from the Peoria County Election Commission, it is a reputable source. Each day, I received a small file with the previous day’s voter data and used it to create a report, via a pivot table in a Microsoft Excel sheet, for Sally Owens and her team to help identify areas for further outreach.
- During my internship with Sally Owens for Illinois State Senate, I contributed in several ways beyond data analysis. In addition to creating reports and visualizations, I assisted with data entry tasks, ensuring voter data was accurately recorded and updated in our systems. I also used NationBuilder to manage outreach efforts, helping to organize and maintain the campaign’s voter database.
- Alongside data-focused work, I supported various clerical duties, such as helping assemble and organize invitations and campaign mailings. I also provided support at campaign events, helping with setup, engaging with attendees, and ensuring smooth operations. These responsibilities allowed me to gain hands-on experience in campaign operations, providing valuable insight into both the strategic and logistical aspects of political campaigns.
## Daily Process
When I received the daily file, it contained information on voters from the previous day, so I had to filter the data to extract what I needed. I filtered the data to include only voter information from the 46th District. Once filtered and placed in a separate sheet, I created a pivot table showing the number of voters in each precinct and the number of outstanding vote-by-mail ballots.
## End of Election Project
### SQL
At the end of the election, we received a complete file containing information on every voter, totaling around 118,600 voters. Since this was a large dataset, I opted to use BigQuery rather than Microsoft Excel. After creating a dataset and table for the data, I queried it to extract the information I needed:
```{SQL}
select 
LastName, FirstName, MiddleName, ResidenceAddress, ResidenceCity, ResidenceState, ResidenceZipCode, PrecinctID, VoterID, DistrictName_2
from
`corded-rope-430400-g3.voter_data.11_11`
where 
DistrictName_2 = '46th Legis.'
```
This query provided the narrowed-down fields I wanted, resulting in a more manageable dataset. I then downloaded a CSV file of the results containing only data from the 46th District.
### Tableau Data Vizualization
- After downloading the new dataset, I uploaded it to Tableau Public to create a data visualization showing the number of votes per zip code on an interactive map. I needed to change the ResidenceCity, ResidenceState, and ResidenceZipCode fields from strings to their respective geographic roles so they could be used to create the map.
- To start, I dragged ResidenceState into the Rows section (columns become longitude and rows become latitude), which generated a highlighted map of Illinois. To outline the zip codes, I dragged ResidenceZipCode to the Detail section.
- Next, I added the count of each VoterID (to show the number of votes) by dragging it to the Color section of the zip code layer. I applied a gradient to make it clear which zip codes had the most votes. This also enabled a label to appear when hovering over each section, displaying the state, zip code, and vote count.
- Additionally, I added points labeling each city to help visualize the areas these zip codes cover. There is a legend on the side to make locating each city easier. Here is a link to the project.
<https://public.tableau.com/app/profile/mia.craghead/viz/Map-CountofVotersperZipCodeinthe46thDistrictIllinois/Dashboard1>
