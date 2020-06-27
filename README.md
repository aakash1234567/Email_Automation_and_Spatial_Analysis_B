## Eyantra Internship
### Spatial Analysis 
### QGIS MAP SETUP

***1)Start a new project***

***2)Include Layers*** 

**i) India map layer with states**

-Go to layers->add layer->add vector layer

-Select automatic or utf-8 and select the shapefile(shp) from map-master->state->admin2.shp

-Press on add and the file will be added as a layer.

-Similarly follow the steps for DISTRICT map

**ii)Adding markers** 

-Add csv file that has latitude and longitude parameters

-For this select Layer->add layer->add delimited text layer

-Select encoding as UTF-8 select the csv file from desired location

-Give the layer name and add X-value as longitude and Y-value as Latitude

-Press on add and we can see the layer added

-The above method can be used to add elsi_college_database_sheet, tbt_data, lab inaug data_with_tbt

**iii)For adding choropleth Maps**

-Add the csv files like with above procedure and keep the csv files ready

-For choropleth map select DB Manager from toolbar and a new window will pop up 

-Select virtual layer->project layer, all the data files of the project will be shown

-To check the table select the file and click on the table option(from the toolbar).

-Click on the new SQL window from the toolbar(top left corner).

-Write sql query in the given box

-For the lab_inaug_chloromap the query looks

-select s.ST_NM,s.geometry,count(d.lab_inaugurated)

***from elsi_college_database_sheet as d, Admin2 as s***

***where s.ST_NM=d.state and d.lab_inaugurated=1***

***group by d.state;***

-In this we have used elsi_college_database_sheet and Admin2(state file) 

-Now press on execute and a new table will be seen in the output window.

-To load this layer as a new layer in the main file, click on Load as new layer(bottom left corner).

-In the below window add ST_NM (state name) as a column with unique values and select geometry in the geometry column.

-Give the name of the layer as per requirement in layer name( prefix).

-Click on LOAD and the layer will be added in the main file with the same name.

-Go back to the main maps file where you can find the layer that has been added recently.

-Now right click on the layer and click on properties->symbology and select option as graduated
-Values column select count option(column with numeric value of each state).

-Select the mode as per requirement mostly use quantile(for equal distribution)

-Click on classify to see the layer and color next to it in the window

-Select number of breaks required in Classes field.

-Click on Apply and Ok and you will be able to load the file of the choropleth map

-For showing the number in the same map

-Right click on the layer select properties->labels select the column value as count and press on ok and apply.
