# Mapping the Art of Displacement

### About the Workshop

To explore the themes of place, movement, and migration underpinning ***The Amplification Project: Digital Archive for Forced Migration, Contemporary Art, and Action***, this workshop will introduce students to Kepler.gl and Flowmap.gl, two web-based GIS tools that create dynamic, interactive maps. This is a ***no-code*** workshop, as Kepler.gl and Flowmap.gl work entirely in the browser. All you need is an internet connection and computer. No special equipment or programs or installations needed. You don't even need to make an account.


#### The Amplification Project

[The Amplification Project](https://www.theamplificationproject.org/) is a participatory, community-led digital archive where art and stories of forced migration and refugeehood find sanctuary and amplification. Founded in 2019 by an international group of artists, curators, activists, and an archivist, we create space for voices that are too often silenced, distorted, or reduced to statistics.


#### Project Data

Data for The Amplification Project is contained in the content management system used for the archive. Three CSV files in this repository are pre-prepared datasets that contain information about the artworks in the archive and geographic data (lat-long coordinates) associated with artists,locations pulled from artwork descriptions, and fields used for maps on the Amplification Project site. 

The files are named according to which program they should be used in (explained more below):

* 1 Data.csv - used for Kepler
* 2 Flowmap_Places.csv - used for Flowmap
* 3 Flowmap_Flows.csv - used for Flowmap


### What are Kepler.gl and Flowmap.gl?

Kepler.gl and Flowmap.gl (also known as Flowmap Blue) are modern JavaScript-based open-source spatial and web mapping tools. They are supported by the OpenJS Foundation and built upon Deck.gl for high-performance data visualization. Their no-code and robust user interfaces and interactive features (including support for 3D graphics) make them an easy entry point into web mapping for beginners. 

Before we begin uploading data, please take a look at these links and explore some of the examples so you get a better picture of Kepler, Flowmap, as well as, for the curious, the entire Deck.gl ecosystem. 

* [Kepler.gl](https://kepler.gl/)
* [Flowmap.gl](https://www.flowmap.blue/)
* [Deck.gl](https://deck.gl/)

Once you have taken a minute to explore Kepler and Flowmap (and Deck if interested), we'll move to a quick dive into the data required for creating the maps and what ours looks like.


### Preparing Geographic Data for Kepler.gl and Flowmap.gl

For Kepler and Flowmap all we need to get us mapping are a few columns in a spreadsheet (the CSVs in this repo) that have simple point coordinates: latitude and longitude. Let's look at the first column in the Data.csv that has geographic information:

![Img_1](/imgs/Img_1.png)


These details show geographic coordinates associated with an artist's birth city (also note the duplicates, but don't worry about them). In addition to these coordinates, there are numerous other columns that have geographic cooordinates, such as the one below that has place names and geographic coordinates extracted from the artwork description. 


![Img_2](/imgs/Img_2.png)


Because the columns are all named differently, Kepler will treat them as different files and create a layer for each of them. Let's go ahead and do that beginner with Kepler.



### Uploading Data into Kepler


Uploading data into Kepler is very straightforward. Follow the below steps:

1. Go to [Kepler.gl](https://kepler.gl/)
2. Click the "Get Started" blue button. A dialog box will open that gives you options for how to add your data.
3. Because we already have the data here on Github, select the "Load Map Using URL" option at the top, and place the below link in the white field with grey "URL" text in it next to the green fetch button: https://raw.githubusercontent.com/DataStorytellingLab/Mapping-Art-of-Displacement/refs/heads/main/Data.csv
4. Click the green fetch button, and you should see something like the below: 

![Img_3](/imgs/Img_3.png)


Congratulations, you have made your map! 



### Points, lines, and arcs in Kepler. 

What you have so far is a pretty basic map with a number of points. Look at the sidebar and you should see that there are many layers in the map already that correspond to the data in the CSV file. Now notice that underneath each layer you will see the terms **point**, and maybe **line** and **arc** in the layers towards the bottom. This is the vector shape Kepler "thinks" your data should be. Most of the time it is correct. But there are many different shapes you can place on the map, though depending on what kind of data you have. To see how this works, click on any layer and you will see options for styling that layer appear, e.g. **Basic**, which tells you what the map mark type is; **fill color** which is what it sounds like; and adjustments like **opacity**. Click on **basic** and select a different shape, say **Hexbin** and then increase the **radius**. See what happens. 

Now scroll down in the sidebar until you see the last two layers, which should say they have the type **arc** and **line** instead of point. Nothing is probably showing up so far. Go to the layer that says **arc** and click on the grey eye icon to make it visible. You should now see lines that are connecting the birthplace of the artist to one of the places extracted from the description of the artwork. If you make the **line** layer visible you will also see connecting lines, but they will be flat instea of an arc.  

Your map should look like this minus the colors of the lines, which we'll get into shortly.

![Img_4](/imgs/Img_4.png)



### Changing colors, strokes, basemaps, tooltips, and filters in Kepler.

Kepler gives you many options for map customization - sometimes too many and they can be nested in the layers. So let's focus on just a couple things. The first is color. As you can see in the screenshot above I was able to adjust the color of the arc based upon the **source** and **target** options. Go ahead and play around with choosing different colors for either this layer or another layer. You may also specify color-coding based upon a field in the data, e.g. assign specific colors to different artists. 

You may also change the styling of lines. In the arc layer, underneath the color option, you will see something called **stroke**. This adjusts the thickness of the arc line. Play with the sizing using the slider underneath.

Now go to one of the point layers and do the same thing. You will notice that you can change the color of the points using the **fill color** option, or assign colors based on a field in the dataset. To change the size of the point, adjust the slider under where it says **radius**. 

By default Kepler assumes a dark basemap because it is cool and edgy. But you may, of course, change that. At the top of the sidebar you will see four icons. Click on the one furthest to the right that looks like a semi-folded map, and you will now see options for different basemaps, as in the screenshot below. 

![Img_5](/imgs/Img_5.png)

You've probably noticed that when hovering over a point or arc a tooltip with some data from the dataset appears. Kepler "guesses" what the most useful information might be, but more often than not you will want to have data in the tooltip that is meaningful. To adjust these, click on the icon to the immediate left of the one you used to change the basemaps. This is the **interactions** menu. You should see a text area called **Tooltip** and within it the fields that are being pulled from the Data.csv file. Go ahead and delete ones you might not want. Click anywhere in the box and you will see a drop down menu with all the fields from the data set. You will see that information populate in the tooltip, as in the screenshot below:

![Img_6](/imgs/Img_6.png)

The final thing to explore is the icon to the left of interactions, which is the **filter** icon. You can add filters to get very specific views or slices of your dataset.

There are many more things you can do with Kepler, but the above should give you a good foundation for further exploration. 



### Exporting your Map.

Now, what if you want to save your map? You have a couple options. At the very top of the sidebar menu you will see a **download** icon (the down-pointing arrow). Click on that and you be presented with four options for your map: Export Image, Export Data, Export Map, and Share Map URL.

Export image and export data are quite straighforward and what they sound like, so I'd like to focus on: **Export Map**.

**Export Map** allows you to export the entire map file as a single HTML page that retains all of the interactivity. To save it do the following:

* Under "Map Format" select HTML (if not already selected by default).
* Skip Mapbox access token.
* Select "Map Mode." The option on the left will give you a reader's view, meaning that the sidebar used to edit the map does not appear. If you want to keep editing capabilities choose the option on the right, or the editor's view.
* Click the green "Export" button. It should download to your computer. Open it up, and the fully-functioning map should appear in your browser.   

![Img_7](/imgs/Img_7.png)

The final export option, **Share Map URL** requires either a Carto or Dropbox account to generate a shareable URL. If you want to use this option you will need to have or create an account with either of those. 



### Uploading Data in Flowmap

Now let's explore how to make a map using Flowmap. Because Flowmap is meant for visualizing connections and movement, the data has to be prepared in a more specific way than Kepler. You'll see that we have two CSV files already prepared: **Flowmap_Places.csv** and **Flowmap_Flows.csv**. You can think of these as similar to sources and targets. **Flowmap_Places** defines the source, with an id, name, and coordinates. **Flowmap_Flows** creates the connections between the places.

To get a map going in Flowmap, follow the below instructions:

* Go to [Flowmap](https://www.flowmap.blue/).
* Click on "How to Make a Flowmap" in the menu bar at the top.
* Scroll down past the instructions on creating a Google sheet and click on the link that says "In browser Flow Map" near the bottom of the page.
* You will see the screen below:

![Img_8](/imgs/Img_8.png)

* The input box on the left is where the **Flowmap_Places** data goes, while the input box on the right is where the **Flowmap_Flows** go. To add the data into the boxes, copy the data from the two csv files. It's best to copy them from the raw extensions to avoid any formatting that Github might add:
  * **Flowmap_Places**: https://raw.githubusercontent.com/DataStorytellingLab/Mapping-Art-of-Displacement/refs/heads/main/Flowmap_Places.csv
  * **Flomap_Flows**: https://raw.githubusercontent.com/DataStorytellingLab/Mapping-Art-of-Displacement/refs/heads/main/Flowmap_Flows.csv

***NB: The "count" in the Flowmap_Flows.csv file is randomly generated and for demonstration purposes only!***

The data should be like the below:

![Img_9](/imgs/Img_9.png)

Click on the "Visualize" buttom on the lower right. And you should see your Flowmap as below! 

![Img_10](/imgs/Img_10.png)



### Adding animations and filtering locations.

In Flowmap you can do a couple things very quickly that take a bit more work in Kepler: filtering your data and adding animations. At the bottom left of the screen you will see a small gear icon link. Click on that to open a menu where you can adjust some of the look and feel of your "flows." To animate your connections, toggle the "Animate flows" on. You will see your connections animated or "flowing." 

In the upper right there is a box to filter your locations. Flowmap automatically parses your data to enable filtering. Go ahead and select one or two locations and filter down the map. 

Congratulations, you have built your first animated Flowmap!

![Img_11](/imgs/Img_11.png)



### Conclusion

These are just a few things you can do with Kepler and Flowmap without ever having to code and right in the convenience of your browser. While they have their limitations, they are great and nice-looking introductory platforms for those wanting to do a bit of mapping as well some low-key exploratory data analysis. 
