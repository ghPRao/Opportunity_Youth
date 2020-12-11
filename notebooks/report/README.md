# Report

This directory contains a polished notebook that states the business problem and summarizes your solution, along with high level takeaways.

# South King County Opportunity Youth

This project offers an updated estimate of the number of Opportunity Youth in South King County using the 2017 5-year American Community Survey [(ACS)](https://www.census.gov/programs-surveys/acs/about.html) Public Use Microdata Survey [(PUMS)](https://www.census.gov/programs-surveys/acs/technical-documentation/pums.html).

Note: We could not include the shapefile as it was too large but here is a link on how to download it. https://usa.ipums.org/usa/volii/boundaries.shtml it is the very first download link labeled "2010 PUMAS"


## BACKGROUND

Measuring the successes and barriers faced by our most vulnerable youth is a challenge in the South King County region<sup>1</sup>. While there is a lot of information gathered from K12 districts and colleges about student outcomes, few data exists among Opportunity Youth (OY): young folks between the age 16 through 24 who are disengaged from both work and school<sup>2</sup>. This population is of particular interest to The Seattle Region Partnership (SRP), a multi-sector initiative founded by the Seattle Metropolitan Chamber of Commerce, Seattle Foundation, City of Seattle, and King County<sup>3</sup>.

## PROJECT GOAL

The SRP would like an update on the estimated number of OY in South King County. According to a recent The Seattle Times article, the number of OY in South King County has remained steadfast at 19,000<sup>4</sup>. However, that estimation comes from a report that is over three years old. As Data Science Consultants, your task is to inform the SRP on the current status of OY in South King County using updated data.

## PROJECT

To get a better sense of the area we are analyzing, we have created a map of King County, WA. Each region in King county is highlighted in a different color below. We are using PUMA (Public Use Microdata area code) to specify each region.

<img src="reports/figures/project_one_map_of_king_county.png">

Specifically we will be looking at South King County shown highlighted below

<img src="reports/figures/project_one_map_of_south_king_county.png">

As we start analyzing the data, we filter out for the information we need. In our query we find all the puma regions where the state name is Washington and the county name contains "King" and "South". This way, we get the data for South King County in Washington. We are taking the Puma code, the name (County, city, location), housing unit, person in housing unit, age, education level, and employment status for the data we want to analyze. Each row in the data contains a certain weight of the population so we multiply the number of rows to take the unique weight of each row into consideration.

Once we have the data we need, it is time to start grouping the data. We group the data to opportunity youth status, level of education, and age. We add a column to count the total population of each age group. Now that our data is grouped the way we want it, it's time to move on to the next step - finding meaning in our data.

First we want to find the level of education completed by the Opportunity Youth. We create a pivot table with 3 age groups of oy "16-18", "19-21", "21-24", and the Total. Each row shows the level of education completed. We also create a pivot table showing how much of the population is opportunity youth in each age group and how much of the population is working without a diploma. We calculate the percents of the populations for each category to better understand the data.

Next, we want to compare this current data with the 2016 data and see if there are notable changes. We import a csv of the 2016 information to compare and place a side by side comparison in a chart.

<img src="reports/figures/project_2016vs2017_oy_education_level.png">

Here we notice a difference in population. This is because the 2016 data included Renton City as a part of South King County, whereas we did not. Still, we can get a good comparison using our population sample. We can see a higher percentage of people achieved their GEDs/highschool diplomas, yet not many opportunity youth are able to pursue a higher level of education. In the following visualations we will explore the trends further in opportunity youth education.

First, we will display a chart for level of education by age for youth in South King County. We will put a line of best fit to find the rate at which the general youth in the area are completing their education.

<img src="reports/figures/project_one_scatter_all.png">

Next we will display the same chart, but only with the demographic of none Opportunity Youths.

<img src="reports/figures/project_one_scatter_noy.png">

Lastly we will display the same chart, but only with the demographic of Opportunity Youths.

<img src="reports/figures/project_one_scatter_oy.png">

Looking at these charts we can conclude that Opportunity youths are only able to complete their education at half the rate of non Opportunity youths. This is troubling data. It brings to light the systemic barriars perventing the opportunity youths from achieving higher education, and many times even highschool degrees. This is clearly not an individual problem, but a sociological one. They problem lies within the system which needs to change for those in dire situations to be able to make a living in this world.
