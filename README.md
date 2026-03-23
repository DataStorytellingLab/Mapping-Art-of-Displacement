# Mapping the Art of Displacement
Instructions for mapping the Amplification Project and using Kepler.gl and Flowmap.gl to create lightweight, no-code interactive maps.

### About

This is a no-code workshop, as Kepler.gl and Flowmap.gl work entirely in the browser. All you need is an internet connection and computer. No special equipment or programs or installations needed. You don't event to make an account.

### Amplification Project Data

#### The Amplification Project

[The Amplification Project](https://www.theamplificationproject.org/) is participatory, community-led digital archive where art and stories of forced migration and refugeehood find sanctuary and amplification. Founded in 2019 by an international group of artists, curators, activists, and an archivist, we create space for voices that are too often silenced, distorted, or reduced to statistics.

#### Project Data

Data for the Amplification project is contained in the content management system used for the archive. The three csv files in this repository are pre-prepared datasets that contain information about the artowrks in the archive and geographic data (lat-long coordinates) associated with artists, locations pulled from artwork descriptions, and fields used for maps on the Amplification Project site. 

The files are named according to which program they should be used in (explained more below):

* 1 Data.csv - used for Kepler
* 2 Flowmap_Places.csv - used for Flowmap
* 3 Flowmap_Flows.csv - used for Flowmap

### What are Kepler.gl and Flowmap.gl?

Kepler.gl and Flowmap.gl (also known as Flowmap Blue) are modern JavaScript-based open-source spatial and web mapping tools. They are supported by the OpenJS Foundation and built upon Deck.gl for high-performance data visualization. Their no-code and robust user interface and interactive features make them an easy entry point into web mapping for beginners. 

Before we begin uploading data, please take a look at these links and explore some of the examples so you get a better picture of Kepler, Flowmap, as well as, for the curious, the entire Deck.gl ecoysystem. 

* [Kepler.gl](https://kepler.gl/)
* [Flowmap.gl](https://www.flowmap.blue/)
* [Deck.gl](https://deck.gl/)

Once you have taken a minute to explore Kepler and Flowmap (and Deck if interested), we'll move to a quick dive into the data required for creating the maps and what ours looks like.

### Preparing Geographic Data for Kepler.gl and Flowmap.gl

For Kepler and Flowmap all we need to get mapping are a few columns in a spreadsheet (the csvs in this repo) that have simple point coordinates: latitude and longitude. Let's look at the first column in the Data.csv that has geographic information:

![Img_1](/imgs/Img_1.png)


This shows geographic coordinates associated with an artist's birth city (also note the duplicates but don't worry about them). In addition to these coordinates, there are numerous other columns that have geographic cooordinates, such as the one below that has place names and geographic coordinates extracted from the artwork description. 


![Img_2](/imgs/Img_2.png)


Because the columns are all named differently, Kepler will treat them as different files and create a layer for each of them. 


### Uploading Data into Kepler.gl

Uploading data into Kepler is very straightforward. Follow the below steps:

1. Go to [Kepler.gl](https://kepler.gl/)
2. Click the "Get Started" blue button. A dialgoue box will open that gives you options for how to add your data.
3. Because we already have the data here on Github, select the "Load Map Using URL" option at the top put the below link in the white field with "URL" in it next to the green fetch button: https://raw.githubusercontent.com/DataStorytellingLab/Mapping-Art-of-Displacement/refs/heads/main/Data.csv
4. Click the green fetch button, and you should see something like the below: 

![Img_3](/imgs/Img_3.png)


Congratulations, you have made your map! 

### Points, lines, and arcs in Kepler. 

You should see in the sidebar there are many layers in the map already tha correspond to the data in the csv file. Notice that underneath each layer you will the terms **point** and maybe **line** and **arc** towards the bottom. This is vector shape Kepler "thinks" your data should be. Most of the time it is correct. To see how this works, click on any layer and you will see options for styling that layer appear, e.g. **Basic**, which tells you what the map mark type is and **fill color** which is what it sounds like. Click on **basic** and select a different shape, say **Hexbin** and then increase the radius. 



### Changing colors, strokes, tooltips, and interactions in Kepler.

Text

### Exporting your project as a fully functioning single HTML file.

Text

### Uploading Data in Flowmmap.gl

Text

### Adjusting shapes, filtering locations, and adding animations.

Text

