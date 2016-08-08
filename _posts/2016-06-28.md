---
layout: post
title: Project Benson
---

Our first project at Metis was to make a recommendation to a fictional client (WomenTechWomenYes) on the best places and times to advertise for their upcoming summer gala.  Given this (intentionally) vague request, we got to work.  The first question was what factors, and more importantly, data sources, should we consider in making our recommendation?

#### Who are we targeting?
The biggest challenge was to determine who our target demographic was.  We made a few hypotheses and assumptions regarding who WTWY wanted donating to and attending their gala.  
* We assumed that wealthy people are more charitable and willing to support a cause, and may be more inclined to support a cause related to their work.  
* We assumed that people in the technology sector would be more willing to support and attend an event sponsored by WTWY.  
* We assumed people in computer science bachelor's programs at local colleges would also be interested in supporting WTWY.  
Our ideal WTWY supporter would be wealthy, and/or supportive of tech initiatives given their own background.

#### Where are these people?
The next step was finding out more about our ideal WTWY supporter.  We first looked at a dataset from the American Community Survey 2006-2010, which provided median income by zipcode.  We decided to rank the zipcodes in descending order, and selected zipcodes that had a median income greater than $70k per year.  Next, we looked up the addresses of universities and colleges offering comp. sci. programs, and large tech companies (i.e. Facebook, Google, LinkedIn, etc.).  We then went through both lists and looked for subway stops within these zipcodes and looked for some overlap between the two lists.  We ended up generating a list of 31 stops that were either wealthy, tech-y, or both.  

#### What stops do these people use?
Now for the data!  We dug into the publically available datasets from the MTA, in which data is collected on entries and exits every 4 hours at all stops.  This was just the data source we needed to learn more about our WTWY supporters.  Given that we expected WTWY to campaign throughout the month of July for an August gala date, we merged the datasets from the month of July 2015, to give us a best estimate of the traffic we expect in July 2016.  We found several anomalies in the data, such as negative counts, or counts greater than 10,000 per 4 hours (New York is busy, but not that busy).  We calculated the total entries and exits for the entire month of July using the hourly data and ranked the 31 subway stops we previously identified.

![total monthly traffic]({{ site.baseurl }}/images/total_traffic-1.png "total monthly traffic")

We weren't surprised at some of the busiest stations but we needed to make some decisions.  Penn Station, while very busy, wouldn't be conducive to stopping and talking to people when they're rushing to work, or running to catch their train home.  We decided to eliminate this stop from the list, and also combine the two Union Square stops.  We ended up with the following top 5 stations to target:  
  
1.  34 Street - Herald Square  
2.  14 Street - Union Square  
3.  86 Street  
4.  47-50 Streets - Rockefeller Center  
5.  72 Street  

#### When are these stations busiest throughout July?
Now that we had a solid list to work with, it was time to dive deeper into the data.  We summed entries and exits to give us the variable total traffic, which was our main variable of interest.  We first plotted this data over the entire course of the month, to make sure there weren't any changes related to holidays, seasons, etc.  Here we plotted total traffic per day over the course of July.  

![86th street july]({{ site.baseurl }}/images/86streetmonth.png "86th street monthly traffic")

Based on these plots, it looked as though traffic was fairly normal over the course of July, with some exception for the July 4th holiday.  We then wanted to look at traffic over the course of a week - what days are busiest?  Here we plotted mean total traffic per day over the course of a week.

![86th street by week]({{ site.baseurl }}/images/86streetweek.png "86th street weekly traffic")

We found that Tuesday - Thursdays were typically the busiest days of the week, not a huge surprise.  However, in order to tailor our recommendation, we need to know more about traffic over the course of a day.  We chose the top 2 busiest days for each station, and then looked at total traffic per 4 hour blocks of time.  Here we plotted mean traffic per 4 hours for the corresponding day over the course of the day.

![86th street by day]({{ site.baseurl }}/images/86streetthursday.png "86th street on thursday")

From these plots, we were able to make some very specific recommendations on what stations to target and when.  We generated a table of the top two busiest days per station, and what 4 hour block of time on those days contained the most traffic. 

Overall, this project was a really nice introduction into how data can be harnessed to make specific recommendations for a client or company.  It gave me a greater appreciation for just how messy real life data is, and how much of a project is dedicated to getting your data into a form that can actually be used.  

