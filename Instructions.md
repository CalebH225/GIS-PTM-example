These are instructions designed to acompany the provided dataset. 

Please ensure that the lastest stable release of Qgis (or another suitable GIS software) is installed on your computer and that the provided datasets are saved to a known location and unzipped (right-click Extract).
# Beginning:

1.) Begin by opening Qgis. Please be aware that the software can take a while to open, so be patient. 

2.) In the top left corner of Qgis there is a blank page symbol that will open up a new project. feel free to save this project as a title of your choise

3.) In the file explorer for your computer please locate the extracted 'Example points' and 'Example Boundary' folders. Within each there will be several files all with the same name. please locate the file with the .shp file extention. Drag and drop those files into the window of Qgis. This should open up them into the window revealing a series of points and as well as a shape surrounding all of the points.

4.) In the file of the coputer please locate the 'Example Image.gpkg' file. drag and drop this file into the window of Qgis, after a moment the image should appear. 

5.) The left side of the Qgis should have a pane labeled 'layers' with three items: BCH5_points, BHC5_boundary, Example Image. These represent the one raster (image) of the fairway, and the two shapefiles. These represent the boundary of the fairway of within the image, and the location of Spring Dead Spot within the fairway (as selected by Wendell Hutchens and Chase Straw)

6.) Feel Free to explore the functionality from here. the checkmarks beside the layers represent the visibility of the layer. You can re-order the way the layers are stacked by dragging and moving the layer name up and down. The transparency of the boundary file can be adjusted by right clicking on the boundary file in the layers pane and selecting 'Properties'> Symbology and select one of the outline options.

#### From here we will explore a couple of potential methods of utilising this data to create disease maps for Precision Turfgrass Management.

# Buffer circles

Buffer circles are a simple way to create a management area from points for precise treatment. The idea with this management style is that if you have an accurate series of points where a problem is, you only need to spray those individual areas. one drawback of this style is that if any disease is missing on your map you may not treat it if it is not adjacent to another point. 

1.) Highlight the points shapefile in the layers pane by clicking on it. 

2.) Press the 'Vector' tab at the top of Qgis, then the 'Geoprocessing Tools' option, and select 'buffer'. A new dialog window should open with some options.

3.) The input layer option should default to 'BCH5-points', but if it did not please be sure to select it. Change the distance to 1 meter. We will leave all other parameters as default. Press the 'Run' button at the bottom.

4.) This will create an new layer called 'Buffered'. This should include circles (geographically speaking) around each individual point. To clean this up a little bit we will return to the 'Vector' tab, 'Geoprocessing tools' and select 'dissolve'. Ensure that the Buffered layer is selected as input and press 'Run'.

5.) This will result in a new layer called 'Dissolved'. Which has all of those circles combined into individual shapes this layer can be exported to a new shapefile by rightclicking on the Dissolved layer and selecting export.

#### This created a map with a 1m boundary around each of the points of located disease this can be exported, and imported into Precision turfgrass management technology

# Heatmapping

Heatmapping is a great way to generate blocks of areas with high amounts of disease incidence. This can make for less complex maps while still covering the most stressed areas of turfgrass. 

1.) On the top row of icons look for the blue gear symbolizing the Toolbox (you can also press alt+crl+T) to bring up the toolbox pane.

2.) Search 'Heatmap'. This should reveal the "Heatmap(Kernel density estimation)" underneath the Interpolation tab. Click on this to bring up the Heatmap window.

3.) Make sure that the 'BCH5_points' layer is selected under inputs, and change radius to 10 meters. Press the 'Run' button, and close the log window.

This will make a new greyscale raster. While this is useful it can be difficult to interperet. 

4.)To make change the colour to something we are more familiar with we can right click on the Heatmap layer in the layer pane, and select 'Properties'. At the top of the Symbology tab, change the 'Render Type' from 'Singleband Gray' to 'Singleband Pseudocolor'. You can also change Interpolation to Discrete, and Mode(below the legend window) to Equal Interval. This will change from a smooth colour ramp to seperate groups. Press OK.

#### Now you should have a heatmap of the disease incidence on your fairway. From here you can decide which areas raise to an unacceptable level









