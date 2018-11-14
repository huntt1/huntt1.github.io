# Project 2
Tom Hunt GES486

### Data Source:

 Crime data was from the Baltimore Police Department at the following website https://www.baltimorepolice.org/crime-stats/open-data

The Baltimore City Polygon was from the City of Baltimore Open GIS data site at http://gis-baltimore.opendata.arcgis.com/datasets/9af1e17e8ff8469fa9015abde4f33e75_0

### Tools used
- create grid
- clip
- count points in polygons
- heatmap
- buffer


### Data Analysis:
  For this project, I downloaded Baltimore Crime data from January 2012 to October 2018 from the Baltimore Police Department. I immediately removed the data from 2018 since it was not a full yearself. The remaining data set was 6 full years of Baltimore City Crime Data.

  This was approximatly three hundred and thirty thousand crimes throughout the years which were sorted by year using SQL Query in a SpatiaLite Database by year and then sorted again to remove nonviolent crimes. At the end around sixty thousand crimes in the six year period fit the descritption i was looking for. A diamond grid of Baltimore City was created and crimes were counted in each polygon for each of the six years. This grid crime map was then made into a gif as is seen below. The dark purple is little to no crime and yellow is the high crime areas.

  Data was also removed that was recorded in a abnormal fashion not corresponding to where the actual crimes occured. This includes most hospitals and police stations. Previous to removal, these areas were hotspots on the crime density map.










![output_e8xh54](https://user-images.githubusercontent.com/42807766/48355655-8194db80-e662-11e8-959e-d82e227ac2b0.gif)


![giftake4](https://user-images.githubusercontent.com/42807766/48318551-99bc1a80-e5d0-11e8-9f2f-401e10dd54ee.gif)

That gif was composed from the following 6 maps
 ![2012gif](https://user-images.githubusercontent.com/42807766/48319767-04288700-e5e0-11e8-9d90-3f40805cee2d.png)

 ![2013gif](https://user-images.githubusercontent.com/42807766/48319778-1b677480-e5e0-11e8-83f5-24c64b71f7e7.png)

 ![2014gif](https://user-images.githubusercontent.com/42807766/48319786-2ae6bd80-e5e0-11e8-99db-2ddedc33651d.png)


 ![2015gif](https://user-images.githubusercontent.com/42807766/48320034-f3c5db80-e5e2-11e8-9153-39dbb5b1082b.png)

 ![2016gif](https://user-images.githubusercontent.com/42807766/48320046-0f30e680-e5e3-11e8-995b-3d9c40a9193e.png)

 ![2017gif](https://user-images.githubusercontent.com/42807766/48320056-1f48c600-e5e3-11e8-8e4e-20f13c031c70.png)




## This is the python I wrote to select features of the active layer and add all the project layers
``` python
#this is python created by Tom Hunt to determine high crime areas year to year in baltimore from 2012 to 2017


from qgis.core import *
from qgis.gui import *
from PyQt5.QtGui import *
from PyQt5.QtCore import *
from PyQt5.QtGui import QColor
from PyQt5.QtCore import Qt
from qgis.utils import iface


def load_layer():
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/2012_violent_crimes_density_edited.shp', '2012 Violent Crimes', 'ogr')
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/2013_violent_crimes_density_edited.shp', '2013 Violent Crimes', 'ogr')
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/2014_violent_crimes_density_edited.shp', '2014 Violent Crimes', 'ogr')
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/2015_violent_crimes_density_edited.shp', '2015 Violent Crimes', 'ogr')
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/2016_violent_crimes_density_edited.shp', '2016 Violent Crimes', 'ogr')
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/2017_violent_crimes_density_edited.shp', '2017 Violent Crimes', 'ogr')
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/Balt_City_polygon/baltimore_city_polygon.shp', 'Baltimore City Boundary', 'ogr')
    iface.addVectorLayer('Z:/486/Project_2_New/Shapefiles/Balt_city_harbor_water.shp', 'Baltimore Harbor Water', 'ogr')

  # all the above addvectors are confirmed to work.
    Layer = iface.mapCanvas().currentLayer()
    expr = QgsExpression( "\"NUMPOINTS\"=25" )
    it = Layer.getfeatures( QgsFeatureRequest( expr ) )
    ids = [i.id() for i in it]
    cLayer.setSelectedFeatures( ids)




    #These below are to change the color of the layer,


def change_color():
    active_layer = iface.activeLayer()
    renderer = active_layer.renderer()
    symbol = renderer.symbol()
    symbol.setColor(QColor(Qt.blue))
    active_layer.triggerRepaint()
    iface.layerTreeView().refreshLayerSymbology(active_layer.id())






```
### Crime Heat Map
Below is a heat density map made from the point shapefiles added up from 2012 to 2017. 
![heatmap](https://user-images.githubusercontent.com/42807766/48327009-672f1380-e60a-11e8-9be0-78c8dba09725.png)
 You can see a couple portions of the harbor/downtown area with dark red meaning high crime.
The Darkest red area is where the Royal Farms Arena is, right at the end of the inner harbor.
The other dark red spot to the east of that is a high crime area boxed in by Broadway east to the North, Middle East to the south, Gay Street to the west and Madison Eastend to the East.

### Crime Free Areas in Baltimore
The below map was created using my edited/cleaned up Violent crime point vector file containing all violent crime from 2012-2017. I gave all points a 1000 foot buffer and then dissolved the file. Below we will blow up two of the main violent crime free areas.
![crime_3](https://user-images.githubusercontent.com/42807766/48442800-33b0ce00-e75d-11e8-9f1f-68edf4f99ffe.png)


As you would think, the safest places in Baltimore are parks and industrial areas. cemeteries arent bad either. 



![puta madre](https://user-images.githubusercontent.com/42807766/48457192-c0747f80-e78f-11e8-9cdd-fddbf86c4e5d.png)

### Tuscany-Canterbury
A neighborhood with no violent crimes within 1000 feet


![neighborhood closeup](https://user-images.githubusercontent.com/42807766/48457216-d8e49a00-e78f-11e8-9d83-8c93c97aa923.png)



![capture](https://user-images.githubusercontent.com/42807766/48457239-ebf76a00-e78f-11e8-8e6c-12f4835ba8ee.JPG)











