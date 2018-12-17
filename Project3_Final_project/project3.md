---
title: Final Project
---



Below are images created using GeoDa. GeoDa is a free spatial analysis and autocorrection software you can download for free [here](http://geodacenter.github.io/download.html).

These images are based on the NUMPOINTS variable which is a count of violent crimes in each of the hexagons created over baltimore. This select dataset was created in the previous ["Project 2"](https://huntt1.github.io/Project2_BaltMap/Project2.html). You might notice that the grid of Baltimore has much larger hexagons than in Project 2. It was resampled to be more visible.

![capture6](https://user-images.githubusercontent.com/42807766/49627451-e1a24780-f9ac-11e8-850a-5f9c0f1beba4.PNG)


Below is a graph showing the Moran's I of the Baltimore crime dataset. This is a measure of how related or random the data set is. A Moran's I of 1 would be an extremely clustered dataset. A Moran's I of -1 would be if the points were perfectly dispersed. A Moran's I of 0 is a random placement of the data. As you can see below, the Moran's I of Baltimore Violent Crime Data is fairly high at 0.637. 

![capture5](https://user-images.githubusercontent.com/42807766/49627452-e1a24780-f9ac-11e8-8c40-7ddb379314f1.PNG)



The below two images show the signifigance and cluster maps for this baltimore crime data file. The general theme is what you would expect, the more populous downtown area has higher clusters of crimes and are highly significant. The one out of place high-high area is along route 129 and 140 leaving the city in the northwest. 

![capture4](https://user-images.githubusercontent.com/42807766/49627453-e1a24780-f9ac-11e8-865e-b2a7a820012b.PNG)


![capture3](https://user-images.githubusercontent.com/42807766/49627454-e1a24780-f9ac-11e8-8659-65d641d5c02a.PNG)


Then you're like wait what else can i do with this data. 

I then changed up from using the grid I had created to show crime, and used a Baltimore Neighborhood shapefile set to show Baltimore violent crimes. This changes the Moran's I considerably, from high clustering to no clustering. The original grid had a Moran's I of 0.637 while the neighborhood Moran's I was a much closer to 0 at 0.132.

This is a prime example of the Modified areal unit problem. The shape and size of the statistical areas that we compare directly affects what our outcome is.


![nhood4](https://user-images.githubusercontent.com/42807766/49780459-9b1a5900-fcdc-11e8-9cc6-b041657a0345.PNG)
![nhood3](https://user-images.githubusercontent.com/42807766/49780460-9b1a5900-fcdc-11e8-9923-131290fac794.PNG)
![nhood2](https://user-images.githubusercontent.com/42807766/49780457-9b1a5900-fcdc-11e8-8c1f-730e04a8d270.PNG)
![nhood1](https://user-images.githubusercontent.com/42807766/49780458-9b1a5900-fcdc-11e8-9bf1-514372d095fb.PNG)


Here is a nice little map showing Violent Crime by neighborhood
![neighborhoodcrime2](https://user-images.githubusercontent.com/42807766/49778670-3c50e180-fcd4-11e8-96b5-9c3ec35e1751.png)

<b> Now to go a different direction </b>

Inspired by Dr. Mahmoudi's [Badassness Map of Portland](http://dillonm.io/files/PortlandBadassnessMap2011March.pdf) where he took 8 factors to define if an area was badass.
In my redux of this, I tried to map things i thought were spooky or scary in Baltimore. 
This included
- Haunted Buildings
- Cemeteries
- Funeral Homes/Crematoriums
- Courts
- Speed Cameras
- Arsons (2017)

<medium> Data Sources: </medium>

It took a while to collect this data, and lots of sorting through datasets with over a million points. Haunted buildings were taken from [A googled website](https://www.hauntedrooms.com/top-11-haunted-places-baltimore-md). Cemeteries were hand picked by looking at satellite imagery and creating my own data. Funeral Homes/Crematoriums was created the same way, with googling and looking at satellite imagery. Courts was taken from [This Baltimore Data](https://catalog.data.gov/dataset/courthouses-86077) and also added in Federal courts not included in that data. Speed Camera data was taken from [Open Baltimore Data](https://data.baltimorecity.gov/Transportation/Baltimore-Fixed-Speed-Cameras/dz54-2aru). Arson data was taken from [Baltimore Crime Data](https://www.baltimorepolice.org/crime-stats/open-data) and slightly edited to remove faults.


Rat data might be in the final project, it's a lot of reportings.

![scary_point3_3](https://user-images.githubusercontent.com/42807766/49969720-36871600-fef7-11e8-8848-0d9f3603d77a.png)


In this map, Cemeteries and Haunted Buildings have double weight.

![spooky7](https://user-images.githubusercontent.com/42807766/49983310-f4c69180-ff2f-11e8-888e-cc8a4b9dc0e6.png)

