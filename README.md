# The Impact of Streetlight Outages on Crime Rate in Chicago 

The United States incarcerates more people than any other country and relatedly, is ranked 49th in the world for crime rate. Though mass incarceration and criminal justice reform are currently very costly, there may be low-cost interventions that can help decrease crime rate in American cities. We can apply the nudge theory, a theory popularized by scholars Richard Thaler and Cass Sunstein, to positively change crime trends. As they describe it in Nudge: “A nudge…is any aspect of the choice architecture that alters people’s behavior in a predictable way…the intervention must be easy and cheap to avoid” (Thaler and Sunstein, 6). Thus, we can look at making small changes to the design of public spaces, and in this case, the use of streetlights. Streetlights, especially night lighting, can potentially reduce crime rate and improve perceived safety among pedestrians. In this project, I will examine the relationship between public lighting and crime rates in Chicago, a city with a crime rate higher than the national average and known to be the most gang-infested city in the US. The main questions I will try to answer are:

1.	What is the relationship between streetlight outages and crime? In other words, if a streetlight outage occurs, does crime increase or decrease?
2.	How much does crime increase or decrease with streetlight outages?
3.	Is the relationship uniform across all of Chicago, or is the increase/decrease only in certain areas? 

Previous research on the relationship between streetlights and crime rate has produced mixed conclusions. This past April, researchers from UChicago Urban Labs released results from their randomized experiment on street lighting in New York City and found that lighting can reduce outdoor nighttime index crimes by 36% and overall index crimes by 4% in affected communities. A study in 2000 conducted by the Illinois Criminal Justice Information Authority, however, found that reported offenses actually increased after installing streetlights in Chicago. Researchers from another study in England and Wales found no evidence in association between streetlighting and the aggregate count of crime. While most of previous research including the above three focused on statistical analysis, I will be using GIS to bring forward new findings.

I use data from the City of Chicago Data Portal for both crime and streetlight outages, specifically the following datasets:
1. Crimes – 2001 to present
2. 311 Service Requests – Street Lights – All Out – Historical
3. 311 Service Requests – Street Lights – One Out – Historical
4.	Boundaries – Wards (2015-)

I focused on outages and crimes that were reported in 2016 because the homicide rate increased dramatically in that year after remaining steady between 2010 and 2015; in fact, it because the highest homicide rate in Chicago since the mid-1990s. Since crimes in outdoor locations are more likely to have been impacted by streetlight outages, I examined crimes committed on location types like street and sidewalk. I further narrowed down the crime types to assault, homicide, motor vehicle theft, and robbery, as these are not only some of the most prevalent crimes in Chicago but also ones that could plausibly be affected by outages (and occurred outdoors). 

Beyond streetlight outages, there may be many more factors that affect crime rates. In reality, there are likely neighborhoods that have both high crime and are susceptible to a lot of outages. Calculating the raw correlation between outages and crimes for all of Chicago isn’t appropriate because I would be overlooking confounding variables. Instead, I created a 50-meter buffer around each streetlight that experienced an outage. I chose this buffer distance by looking at the average streetlight coverage (10 meters), average block length in Chicago (200 meters), and the average block width in Chicago (100 meters). I was then able to compare the crime rate in each buffer during the outage to the crime rate in the same buffer for periods before or after each outage. This way, each buffer acts as its own control, so I do not need to control for aforementioned factors that affect crime rates throughout Chicago. Specifically, I compare the crime rate during each outage to the crime rate over the rest of the year during which there were no outages. Before I made that calculation, though, I calculated three other metrics to give even more perspective. In summary, I calculated and compared the following metrics:
1)	The rate of crimes committed during an outage with respect to crimes committed within a buffer 
2)	The rate of crimes committed during an outage within a buffer with respect to crimes committed within that same buffer
3)	The rate of crimes committed during an outage with respect to all crimes committed in Chicago in 2016
4)	The rate of crimes committed during an outage with respect to the outage time period
5)	The rate of crimes committed pre-/post-outage with respect to the non-outage time period

After calculting these metrics using Python, I mapped the results and comparisons in QGIS. 
