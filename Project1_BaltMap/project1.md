---
title: Buildings in Baltimore
feature_image: "https://user-images.githubusercontent.com/42807766/50022544-8bd02f80-ffaa-11e8-8f14-890ca7d37e3c.jpg"
---
<b>Tom Hunt Project One</b>

<strong>First off, I did not stick to really one map and created two ways to present the same dataset. </strong>

![3d map 1](https://user-images.githubusercontent.com/42807766/49382255-f9937600-f6e3-11e8-9f20-ba38ba5dc2ba.PNG)


![neighborhood map alternate version](https://user-images.githubusercontent.com/42807766/49382301-16c84480-f6e4-11e8-8b56-9d614b82e52c.jpg)

![capture1](https://user-images.githubusercontent.com/42807766/49382664-006eb880-f6e5-11e8-89ab-9ec7e13e2f50.PNG)

![capture2](https://user-images.githubusercontent.com/42807766/49382676-08c6f380-f6e5-11e8-9453-ccd80a53d71c.PNG)






<b>One</b> uses counts in neighborhood shapefiles to see density in neighborhoods of Baltimore.

<b>Two</b> uses a grid system to show this same data count but this time the count was within the grid hexagons instead of neighborhoods.

<sub>- I also added an alternate neighborhood map in there that was my first idea using a ESRI background but with no water shapefile.

For the 3D Map, I took a DEM file of Baltimore I had and put my grid map overtop of it to see if ground rent older houses seemed to be in lower or higher elevation. It is somewhat tough to see this on the 3D map just because it is a picture of a 3D map, I wish I could have added the whole thing as an interactive 3D map.

I have included screenshots, but you can see in my files that I used SQL querying to harvest some of the data from these huge databases. I also put a majority of this new data in SpatialLite databases, I think there are four total in my file for the different map ideas I had. I do still have a ton of shapefiles and general "crap" because I was trying a 8 map version of building age in Baltimore that I did not finish.
As far as tools that I used to create this, most that I could think of are listed below.

<em> Create grid, count points, a multitude of different clips (both raster and vector), 3D model viewer, projecting data to different CRS'</em>

The data I used for this project was from [https://data.baltimorecity.gov](https://data.baltimorecity.gov) and [https://gdg.sc.egov.usda.gov/](https://gdg.sc.egov.usda.gov/). The first had the neighborhood and land data while the second link had the water shapefile links to fill the harbor in.

<b> Overall, I think my maps and data analysis show that old buildings with groundrent are most common in a huge ring around the harbor. This is the area that was first built up in Baltimore historically so it makes some sense. There were very little to no older building with groundrent as you went further to the outskirts of the city. The one gap in the data near the harbor is where Orioles and Ravens stadium are currently, this leads me to believe they destroyed some very old houses to build the stadiums. I also wonder how they dealt with the groundrent of demolished homes since there is a stadium on the previously groundrent land.
