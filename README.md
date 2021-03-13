# Final Essay related to Project

## [Link for the Project](https://xiaoxixiaxx.github.io/Dashboard_SeattleCarCollision/)

![CarCollision](https://user-images.githubusercontent.com/77243665/110905013-a941f000-82be-11eb-8789-bf8edcf28f66.png)

## Digital Geography for Seattle Car Collisions from 2018 to 2020  

## Introduction
Passed covid-19 pandemic of 2020, while looking forward to the popularization of vaccines, we are also thinking about the changes the epidemic has brought to people and how the epidemic will affect people's daily lives. As we have observed during the epidemic, when we go out and drive on the road, we can obviously feel that there are fewer vehicles on the road and the traffic volume has dropped drastically. The number of people driving cars seems to have been greatly reduced. So, does the reduction in traffic decrease traffic accidents? Will covid-19 affect traffic safety? We started exploring with questions. Related articles give such reports,
> "By the NSC's mark, 2020 is shaping up to be much deadlier for auto accidents than last year. The monthly mileage death rate jumped 26.1% in July 2020 compared to July 2019, according to the NSC, as fatality rates spiked despite the drop in miles driven. (The Rothenberg Law Firm, 2020)"

### A. Goal of the Project
The goal of this Seattle car collisions project comes from thinking about these road safety data. The project displays traffic collision data from 2018 to 2020 in the form of a smart dashboard. Its purpose is to visualize the changes in the number of car collisions and geographic locations in the Seattle area before and after covid-19 through digital geography, and spatially analyze urban traffic safety. In addition, spatially highlighted the road sections where car accidents frequently occur. Provide users with traffic safety information. At the same time, put forward the thinking about whether road safety, urban life, and so on are affected by covid-19.

### B. the major functions

* Side Panel & Chart (responsive design): The interactive Side Panel displays the specific data of car collision from 2018 to 2020 each year, and users can switch options to view. The Chart with responsive design displays the car collision information for each month in three years and compares the correlation and difference between the data at different times in the histogram.

* Heat maps: The heatmap visualization technology displays car collision phenomena as two-dimensional colors of different intensities. Geographical locations with frequent car collisions show stronger colors, while road sections with fewer collisions show weaker colors. Heatmap conveys information about the density of car collision to the users.

* Thematic Maps & Interactive Elements: The design that fits the car collision theme reflects the visual effect. The thematic map highlights the city's traffic roads and shows the specific geographic location of the car collision. The Interactive function allows users to select different themed maps. It is designed by MapBox Studio. 

### C. list of the web map element
* Title
* Toggle full screen
* Scalebar
* Legend
* Basemap switcher
* Zoom in/out.
* Clickable side panel
* Embedded linking

### D. the audience
The intended audience would be citizen. They can learn which road sections are dangerous. Groups concerned about how covid-19 affects people’s lives would be also interested in this project. In addition, the dashboard would be used by Traffic Administration, Urban Planning Bureau, Government department, NHTSA as well. The visualized digital geography and data in the project may become a reference for their social survey. And the visualized information of the project may also be helpful to related institutions, laboratories, or companies engaged in autonomous driving technology research.

### E. the authors
This project was jointly completed by Jin Ning Huang and Xiaoxi Xia. 

### F. the data collected date
The data created on October 15, 2020, updated on December 31, 2020.

### G. list the data sources
* The data comes from [data.seattle.gov](https://data.seattle.gov/dataset/Collisions/nuam-5pkc)
* Publisher: Seattle IT
* Dataset Owner: Seattle City GIS Program
* Data processing: Use Python to grab the available data we need from raw data, such as all data about car crash information from 2018 to 2020. Use QGIS and SQL filtering to convert the available data into shapefile types and generate tile layers of raster format, such as basemaps and heatmaps.
* Data Format：CSV format, Shapefile format, raster format.

## Systematic architecture
In the project, its creation, provision, and use are realized by the physical machine shown in the picture. They are divided into external internet and internal network, including administrator, web client, web server, geospatial server, file server, database server.

![architecture](https://user-images.githubusercontent.com/77243665/110904342-ab577f00-82bd-11eb-93ab-45bc7b0811f1.jpg)

> A web server that acts as a web entry point into your organization's network. This is also called a proxy server. It is protected by firewalls that shield malicious traffic into your internal network. It's also a place where you can put web application code (such as HTML and JavaScript files) for your web maps.
> A geospatial web services server that has specialized software and processing power for drawing maps, responding to feature queries, and performing GIS analysis operations.
> A database and/or file server holding all of your GIS data. This machine might be equipped with redundant storage mechanisms and regular backup scripts that prevent the loss of data.
> Desktop workstations that are used by administrators and internal client applications. These machines will also be used to prepare data, author maps, and sometimes administer the other machines.

In the project, web server provides a place to put HTML, CSS, and JavaScript code, then make a request from database, or file server. Web server delivers it to client. Client server can be handled thing and communicate between client and server. Geospatial web services server draws maps and operates GIS analysis in the project, and it includes, OpenStreetMap, MapBox, QGIS. The theme basemaps are made by MapBox. The tiles of heat maps and tiles of collisions from 2018 to 2020 are generated by QGIS. 

Moreover, the data flowed in between the client and server. The client's operation process is to send data sources in the database and files, and then the geospatial server draws the data set into a map. Our project data source comes from [data.seattle.gov](https://data.seattle.gov/dataset/Collisions/nuam-5pkc) which collects all Seattle car collisions.

## Critique UI/UX 
* The user interface and user experience depend on the map design and interactive functions of the map. 

* The map interface includes 4 different basemaps, which display the base map, satellite map, night scene mode and street theme basemap respectively. Multiple basemaps interfaces give users more choices. And the use of the icon of the collision graphic enhances the user's attention to the theme and arouses the user's emotions.

   ![icon](https://user-images.githubusercontent.com/77243665/110905283-16ee1c00-82bf-11eb-8e87-dfa3031de454.png)

* The zoom function allows users to focus on the geographic location of each car collision.

* The user interface provides a legend and maps switcher, which adds user interaction.

   ![Legend](https://user-images.githubusercontent.com/77243665/110905625-9c71cc00-82bf-11eb-88c1-c6d47caa57be.png)

* There are rich interactive functions in the side panel to meet more customers' needs and examinations.

   ![ChooseYears](https://user-images.githubusercontent.com/77243665/110905761-d773ff80-82bf-11eb-8c05-6b588f8e93a4.png)

## Cons and Pros
The disadvantage of this dashboard is that it does not separately visualize the number of deaths caused by traffic accidents. The data includes all types of car collisions. Therefore, the data displayed on the dashboard is not enough to confirm that traffic accidents during covid-19 were more frequent before covid-19 occurred. The reason for this deficiency is that the data is large and difficult to subdivide in a short period of time. I will continue to improve this project.

Another shortcoming is that the main data type used in web development is raster which is displayed through tile layer. Therefore, leaflet cannot be used in the web map to add user interaction functions, such as configure pop-ups. This can be solved by vector data format displayed by geojson data type.

Even if this dashboard has shortcomings, its advantages still outweigh its disadvantages, and it is worth sharing. It clearly visualizes the specific locations of traffic accidents in 2018-2020. Spatial analysis of areas where accidents frequently occur. This is the key role of digital geography. Users can freely choose to click pane or web map to view the data of each year. Pane on the left shows statistics and can compare them year by year. The second statistical chart shows the data for each month of the three years, which analyzes the differences in society and people's lives in different months. It is suitable for the various needs of users. The basemaps follows the map design concept, using appropriate colors and icons. Moreover, the web map visualizes the frequent occurrence areas of traffic accidents through heat maps. The entire dashboard is easy to navigate and displaying appropriate and sufficient information and gives users visual enjoyment.

The dashboard still has parts worth sharing and adding. It can increase the cause of car collisions, such as weather, time (night or day), vehicle type (car, bicycle, pedestrian), and it can display more road condition information, such as street corner information, road damage, and remind users that the road is narrow. Whether the accident happened because of the unreasonable setting of traffic lights, etc.

## Analyzes the project and critically reflect social implications
By observing the visualized vehicle collision location of the project, the display in 2018 and 2019 are relatively similar. The most frequent collisions are on roads in downtown Seattle. Secondly, collisions on major traffic roads are also more frequent. There are relatively few collisions on small roads in cities. On the other hand, Highway I-5 is the section with the least number of vehicle collisions. The difference in 2020 is that the collision sites are more scattered and not clustered in downtown Seattle. The map also shows that car collisions in some social places such as parks, schools, and parking lots. In addition, the farther away from the urban area, the lower the incidence of collisions.

Clicking to view the different data for each year displayed in the histogram "comparison for Each Year". From 2018 to 2020, the number of car collisions in Seattle has been declining year by year. Due to the impact of covid-19, the data for 2020 has fallen. This data illustrates the reduction in economic activity after covid-19, and the economic downturn and recession in Seattle. People's lives have also been affected, towards a period of economic weakness. In addition, the data in 2019 is also significantly lower than in 2019. This allows us to see the changes in the automotive industry. Perhaps more advanced technology and safety technologies are used in the automobile manufacturing industry, thereby reducing the rate of car collisions. The decrease in collisions year by year also points out the efforts of transportation agencies in safety policies and the improvement of people's driving habits.

## Acknowledgement
I sincerely appreciate UW Professor Bo Zhao for providing the lectures and materials to analyze the project.

## Reference:
[1] The Rothenberg Law Firm: https://injurylawyer.com/car-accidents/has-the-covid-19-pandemic-reduced-the-number-of-car-accident-fatalities/
[2] data.Seattle.gov: https://data.seattle.gov/dataset/Collisions/nuam-5pkc
[3] System architecture for web mapping: https://www.e-education.psu.edu/geog585/node/684
