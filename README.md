# Udacity Nanodegree Project Submission For Data Visualization
## Summary 

This data visualization is about the famous Titanic catastrophe and the 
question if the survivors and the dead have respective common properties.
And indeed there is a correlation between passenger class, sex and the 
destiny of the passenger. So the goal of my visualization is to show
this correlation. 

## Design

First, I started to explore the dataset for correlations between the properties 
of a passenger and his fate. I found that young female passengers from the first
class had best chances to survive, whereas male from the third class had the most
deaths. Exploring the data further I found that the values for sex and passenger 
class are complete, but for age there are more than 170 values missing. That is why I
excluded age from my factors for the passenger categories and came up with
the following 6 passenger categories:
 - male first class
 - male second class
 - male third class
 - female first class
 - female second class
 - female third class

To each category belong the sums how many survived and how many died. 

Since position is the best visual encoding for humans to distinguish,
I chose to use position-y for the number of passengers and the visual 
encoding color hue to code the destiny: survived or not. A bar chart would match best 
to use position-y and color-hue with pairs of bars for each category:
one bar for the survivors and one for the dead. 

Before I could start with the coding of the chart, I had to gather the
data for each category. For that I loaded the original data in a sql database
and generated the grouped values with the following statement:

	select pclass,sex,survived,count(*) from titanic_training_data group by pclass,sex,survived order by pclass,sex,survived;

Then I used dimple.js to create the bar chart. Since I want to show the correlation between
 the categories and survival, the categories should be sorted by survived or died, depending
 on user interaction: a click on the legend would change the sort order to the correspondig destiny.
 Of course dimple.js shows automatically nice tooltips and a connection to the axis for the bar
 the mouse is over. 

## Feedback
I interviewed three reader about the chart here is what they said:

### Reader 1:
 - The colors are confusing, because usually blue means male and red means female and here they mean survived or died
 - Maybe percent values would make the passenger classes (or categories) more comparable
 - The message is not quite clear
 - Instead of letting the reader switch the sorting, the reader could switch between absolute and percent values
 
### Reader 2:
 - The chart and the message are quite clear
 - Absolute values are best

### Reader 3:
 - Why do the bar-pairs not match: some blue bars are men, some are women?
 - Maybe it is better to show only survived men or died women
 - Would it be possible to show percent values?
 
The feedback drove me to the conclusion to show percent values and let the reader
switch between survived and died. From this follows that male and female keep their
color, so no more confusion about the sex. 


## Resources 
 - www.dimplejs.org
 - www.d3js.org

