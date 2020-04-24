# Deep Diving Spatial Autocorrelation to Identify Nutrient Pollution Hotspots in the Chesapeake Bay Watershed
---

## Introduction to Spatial Autocorrelation

### What is Spatial Autocorrelation
Spatial autocorrelation is property of spatial data used to describe the measure of the spatial relationship between the locations or values at locations of a variable. Positive spatial autocorrelation refers to the tendency for the variable to cluster in location and value, while negative spatial autocorrelation tends to refer to dissimilar variation. There are several spatial statistics tools for analyzing spatial autocorrelation in geographic data, I'll go over the 2 major statistics. 
### Moran's I
The Moran's I statistic measures spatial autocorrelation based on feature location and value, evaluating a set of features for clustering, dispersion, or randomness. This measure only indicates that similar values occur together, not whether clusters are composed of high or low values. Index value, P-value, and Z-score are calculated and evaluated to interpret the data. The Moran's I statistic for spatial autocorrelation is as follows:
<br><br>
<img src="../project2_486/MoransI.png?raw=true"/>
### Getis-Ord Gi*
The Getis-Ord Gi* statistic measures spatial autocorrellation based on feature location as well, however this statistic also interprets whether clusters have concentrated high or low values. Resulting Z-score and P-value are interprested to show features with high or low value spatial clusters. The resultant z-scores and p-values tell you where features with either high or low values cluster spatially. Statistical significance is measured with P-value of the feature, and intensity of hotspot is interpreted through Z-score, where a high positive z-score and small p-value indicates a hotspot, a low negative z-score and small p-value indicates a coldspot, and unlikely spatial clustering is indicated by either a z-score near zero or a large p-value. I use the Getis-Ord-Gi* statistic for my analysis for it's high/low cluster analysis ability. The Getis-Ord Gi* statistic for spatial autocorrelation is as follows:
<br><br>
<img src="../project2_486/GetisOrdGi.png?raw=true"/>

---

## Background and the Input Data
Measuring hotspots using spatial autocorrelation statistics is one of many potential tools for identifying areas affected by point source pollution in a watershed. Sometimes when these hotspots are in close proximity to cold spots we can more easily observe the potential sources of pollution.
<br><br>
<img src="../project2_486/WaterQualityStations.jpg?raw=true"/>

### Nutrient Pollution and the Chesapeake Bay
Nutrient pollution is a significant problem globally across watersheds, where nitrogen and phosphorus runoff are often the focus of analysis, research, debate, and management efforts, due to their potential for significant watershed disturbance as limiting plant nutrients. Some other high profile nutrient water quality measures are dissolved carbon (another limiting nutrient), suspended sediments (for implications of turbidity and carrying dissolved materials), and dissolved oxygen (as an important measure of ecosystem health). Nitrogen and phosphorus exist in many forms in the environment (nitrate, ammonia, phosphate, phosphorus salts), and therefore there are are many tests for both. A normal range for TN according to the U.S. EPA is 2mg/L-6mg/L, and TP is 10ug/L-40ug-L. The Chesapeake Bay faces major challenges from the negative effects of excess nutrient runoff; fish kills due to oxygen drop offs from algal bloom death threaten the ecosystem and thus the economic livlihood of those living off the Chesapeake Bay
### Water Quality Data
The Chesapeake Bay Program's Water Quality Database is an open source platform for selecting and downloading measured and calculated physical and nutrient parameters in the geographic extent of the Chesapeake Bay and tidal tributaries for their data collection from 1984-present. The data can is downloaded with geographic attributes, the smallest being 'Water Quality Station', and with other options like Hydrologic Unit and County/City. 

---

## Quantitative Data Analysis
Total Nitrogen and Total Phosphophorus water quality data was downloaded from CBP's database from April 20th 2010 to April 20th 2020 as a CSV file, and then was imported into QGIS and defined geographically. Hotspot analyses were done for TN and TP using ArcGIS's Hotspot analysis. QGIS has a 3rd party Hotspot tool that can be downloaded, however there are currently documented bugs with the install, so I opted for ArcMap as a second choice (The outputs are exactly the same) and just imported the shapefile back into QGIS when complete. QGIS's tool requires you to download pip via the python console, and then pysal via pip.

After hotspots were calculated I created a pointlayer of all the data with recorded high nutrient measurements (according to the previously mentioned EPA guidelines) from my original water quality data to select hotspots only in those locations. Although the statistical analysis measures 'High' and 'Low', the values are arbitrarty in reference to environmental guidelines, so I created this constraint to filter out 'hotspots' that fall below the threshold for high nutrient pollution. I convert the phospohrus measurements from mg/L to ug/L by creating a new field in the water quality station attribute data table.

---

## Identifying Hotspots and Looking Closer
Hotspots that coincided with values above regulatory norms were visualized as hotspots of interest in the map below. The Hotspot Analysis tool sorts hotspots into bins based on statistical confidence.
<br><br>
<img src="../project2_486/NutrientHotspots.jpg?raw=true"/>
I focused on 3 locations for my analysis, where hotspots were in close proximity to a coldspot (>5mi) within the same HUC8 watershed. There were more than 3 of these in total, but that is an analysis for another day. 
<br><br>
<img src="../project2_486/HotspotCloserLook.jpg?raw=true"/>
<br><br>
The first of my qualitative observations was in Central Pennsylvania near Lewisburg, along the western branch of the Susquehanna River. I found something interesting after looking upstream of a hotspot (N and P). Coal power plants are significant sources of nutrient pollution with leftover coal ash and worse.
<br><br>
<img src="../project2_486/MontourPowerPlantHotspot.jpg?raw=true"/>
<br><br>
My second observation was 2 golf courses upstream of a phosphorus hotspot in north central Maryland. Golf courses fertilize their land with nitrogen and phosphorus, often execessively. 
<br><br>
<img src="../project2_486/MonocasyRiverHotspot.jpg?raw=true"/>
<br><br>
My final observation came to no personal surprise as a Baltimore native. Looking at another phosphorus hotspot just East of Baltimore City at the Back River water quality station instantly led me to look for what I knew was upstream, the Back River Wastewater Treatment Plant. Wastewater treament effluent is highly concentrated in nutrients.
<br><br>
<img src="../project2_486/BackRiverHotspot.jpg?raw=true"/>
<br><br>

---

## Conclusions

Spatial autocorrelation statistics are excellent tools for identifying clutsering data. The applications for these tools are vast, and I hope to find more quantitiative analyses to do with hotspot data after calculation. The qualitative analysis used in this project (i.e., me using visual queues of proximity and contrast) are a hueristic for identifying point sources that could be potentially qualitatively realized using more statistical or geoprocessing tools. In this project I used the Getis-Ord Gi* statistic within ArcGIS's Hotspot Analysis tool to identify nutrient pollution hotspots for Total Nitrogen and Phosphorus at water quality stations in the Chesapeake Bay for the past 10 years, and then visually inspected various output scenarios to hypothesize identities of point source pollutions.

---

