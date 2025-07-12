# DS_Capstone_Template
Template Repository for Data Science Capstone Projects


Tableau Public Dashboard: https://public.tableau.com/app/profile/andrew.castaldi/viz/US_Traffic_Accidents_2016-2023/MainDashboard?publish=yes

First thing to note is that I used a new data file for the population of each state.  It was pulled from CENSUS website and is used in the state summary dashboard for calculating the state accident ratio (Number accidents / Population).  I used the population from 2023.

In the jupyter notebook I used Pyspark as we were dealing with 7.8million rows of data.  It was a large file and this helped with the processing.  

I checked for null values which there were a lot.  So I looked at columns that would not be useful in the data analysis and removed them (End_Lat, End_Lng) which were both half Null values along with unnecessary data.  I removed those with some other.  I normalized a few columns such as wind Direction (which later was dropped) and weather_Condition.  That was a big normalization.  Based on the normalized data I was able to fill in some Null values such as precipitation.  If it was Null but the weather condition was Clear/Cloudy, it would be filled with 0.0.

After all the data cleaning and validation, I dropped all Null values.  Less than 10% of the data.

I created new columns as well that i felt were important, or wanted to explore.  Such as time of day, season, etc.   

I created a few new dataframes for the dashboard.  Such as a Weather DF which summmarizes data by weather category, State to summarize State info, and severity DF to get summary of severity values.

I wasn't sure if we needed a model for preditions, since we aren't really predicting anything, instead just looking at the data and finding trends.  Either way, i did some of the statistical calculations ANOVA and Chi-squared for the assignment.

I had problems with Tableau public becuase it wanted a file < 1GB of data.

I hope all this makes sense and you enjoy the project.




Below information is also found in Jupyter Notebook.  Above information is not.
OVERVIEW
Bottom Line Up Front - Traffic accidents are on the rise.  Especially during colder weather where adverse weather like snow/sleet/freezing rain are more likely.  The Winter season is the worst for traffic accidents of recent.  Since the pandemic in 2020 there has been a significant increase in traffic accidents, especially in winter time.  What is interesting is prior to the pandemic traffic accidents were most common during rush hour times, however since the pandemic that has switched.  Now that people are commuting less to work and working from home, the majority of accidents occur outside of rush hour times.  This is slowly trending back to prior to the pandemic due to work situations returning to normal and people going back into the office.  One thing that has stayed relatively consistent with minimal increase is traffic accidents around traffic features which entails more signage and slower speeds.  This trends in the direction of preventing accidents rather than no signage or slowing of speeds.  Although some of these situations such as weather is out of our control, there are preventative measure that can be put in place or incentives to minimize traffic accidents as best as possible.  There are three solutions at the bottom to help prevent traffic incidents correlated to the three identified trends stated in this paragraph




BUSINESS UNDERSTANDING
We are looking at traffic accident data from 2016 - March 2023.  This is an interesting set of data as it covers the start of the Covid-19 pandemic which really took off in mid 2020.  So even though we see the immediate impact the pandemic had on driving incidents, the end of the data does not cover the full normalization back to every day living and still catches the tail end of the pandemic.  Although we can't see what the data is like now, we can still spot trends and see preventative measure to put into place to minimize traffic.  Things such as signage, weather, distance, time of day, all play a role in traffic accidents and we will clearly identify and display that here.  Traffic accidents happen all across the United States, although as may be expected, are more frequent in highly populated areas.  Although we have calculated an Accidnet Ratio per state and possibly could lead to further investigation on what those states are doing to lead to less accidents per person.



Data for below recommendations is in Tableau and/or Jupyter Notebook
BUSINESS INSIGHT/RECOMMENDATION 1 - Weather related
The data shows that more severe accidents happen when there is more distance covered during the accident.  This can be seen in the case where there is perceipitation, specifically icy conditions like hail, rain, freezing rain, snow, sleet.  Accidents that occur during these situations have a higher chance of being more severe than other.  With this information it is important especially during conditions that cause longer accident collisions to be more preemptive with preventative measures, such as salting the roads, snow plows.  Although there is no way of stopping people from going out in these conditions, the more prepared we can be for them, the less likely there is to be an accident.


BUSINESS IMPACT/RECOMMENDATION 2 - Traffic Features on Road increase
Accident traffic is on the rise.  The is the case in most every scenario, however the rate at which it is rising is not at such a high rate when it comes to accidents at traffic features.  Traffic features can refer to the following (Amenity, Bump, Crossing, Give way, junction, no exit, railway, roundabout, station, stop, traffic signal, turning loop).  In these scenarios there are a lot more signage on the road which is clearly leading to less accidents rather than normal conditions.  So in order to prevent more accidents it would be more useful to have more signage in high accident areas such as traffic signals, stop signs, slowing down when necessary signs.  More signage, and slowing of speed is leading to less traffic accidents.


BUSINESS INSIGHT/RECOMMENDATION 3 - Rush Hour Improvements
Traffic accidents are on the rise.  But a lot of accidnets happen during rush hours time (monday thru Friday 6am-10am & 4pm-8pm).  Even thought his time accounts for only 33.33% of available time to travel during the week - it accounts for about 45% of all accidents.  Outside the rush hour time window, accidents stayed on an increase each year, however during the rush hour window there was a dip during rush hour times in 2020 due to the pandemic.  During the pandemic less people were commuting to work, and since more people were working from home.  However now that we are getting back to normal working weeks with more people are traveling into the office, the accidents during rush hour are back on the rise.  In order to prevent this or minimize it there should be incentives for commuters to not be driving to work.  This could be by partnering with mass transit to incentivise people to commute via mass transit.  Another option is congestion pricing to deter people from traveling into work by charging a fee.  This not only would minimize the number of accidents, but it would also help with the pollution of the earth from burning less fossil fuels.






CONCLUSION
to more driving and therefore more accidents.  But as things still level out in normality there should be a more consistent trend.  Even though there are clear trends here.  Such as weather is a big point of accidents.  It seems that lack of signage is too.  Rush hour data would be better to gather now, but still there was a major change in rush hour data.  Just before the pandemic, rush hour accounted for more than 50% of all accidents.  Since then, it still contributes a lot and is back on the rise to catching up with accidents outside of rush hour, but not the same majority volume it was prior to the pandemic.  There are definitely clear improvements that could be made here, but no one imporvement that would fix everything.  Each improvement would take time to put into place but would be beneficial.  If there was an interesting in putting more traffic features on the roads, there would need to be a further deeper analysis into each state or location to see where these features would be most beneficial.  High accident areas would be the focus there.
