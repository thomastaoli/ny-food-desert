# Food Desert in NYC
In this project, I tried to visualize the location of grocery stores in NYC and try to answer a simple question: where are NYC's food deserts.

## Data Collection Process

While it sounds arbitrary, I made a list of all the grocery stores I visited and planned to visit, and asked a bunch of New Yorkers from different boroughs about where do they get food.
Then I went to their websites and scraped the store locators, putting them into a csv file including street address and zip code. 

## Cleaning
While I tried to keep my research objects within the five boroughs, an interesting part of this process is I used ChatGPT to identify and eliminate addresses in Nassau County and NJ. What I found was that both people working for the grocery stores and GPT aren't too familiar with the geography of Queens (which forced me to learn more about my city also).

With the time available for this project, I ended up being able to include over 300 retail locations in the file. Then I put the street addresses into DataWrapper (which is a shorcut) to get the geo coordinates of the stores.

## Data Analysis
Do find out which neighborhoods have the least grocery stores, I downloaded the geojson file of Neighborhood Tabulation Areas (NTA, 2020 version) and ran codes to see how many locations are within each polygon.
The city also published NTA based lifestyle survey data and geo locations of FRESH program incentive areas (which can be considered as government recognized food desert). I combined both for possible correlation.

## Visualization
I mostly used DataWrapper for mapping in this project, as it has comprehensive geo database of the city which saved a lot of time. Meanwhile, I also used Illustrator for further processing.
The highlight of the project is the use ai2html, so that the NYC map fits smaller screens better, as I put Staten Island on the upper left corner.

## Future Work
There were many things I could have done better for this project, and hope to work on in time to come:
1. Include more food retail places. Some neighborhoods in the city, such as China Town and Flushing, have many individual grocery stores, which are not reflected in the project.
2. Combine the number of grocery stores with more census data, such as population and income.
