# Udacity Nanodegree Project Submission For Data Visualization
## Summary 

This data visualization is about the famous Titanic catastrophe and the 
question if the survivors and the dead have respective common properties.
And indeed there is a correlation between passenger class, sex and the 
destiny of the passenger. So the goal of my visualization is to show
this correlation. 

## Design
explain any design choices you made including changes 
to the visualization after collecting feedback

First, I started to explore the dataset for correlations between the properties 
of a passenger and his fate. I found that young female passengers from the first
class had best chances to survive, whereas male from the third class had the most
deaths. Exploring the data further I found that the values for sex and passenger 
class are complete, but for age there are more than 170 missing. That is why I
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
encoding color hue to code the destiny: survived or not.A bar chart would match best 
to use position-y and color-hue with pairs of bars for each category:
one bar for the survivors and one for the dead.

Before I could start with the coding of the chart, I had to gather the
data for each category. For that I loaded the original data in a sql database
and generated the grouped values with the following statement:

	select pclass,sex,survived,count(*) from titanic_training_data group by pclass,sex,survived order by pclass,sex,survived;

Then 

## Feedback 
include all feedback you received from others on your visualization from the first sketch to the final visualization

## Resources 
list any sources you consulted to create your visualization
