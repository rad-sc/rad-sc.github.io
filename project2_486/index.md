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
The Getis-Ord Gi* statistic measures spatial autocorrellation based on feature location as well, however this statistic also interprets whether clusters have concentrated high or low values. Resulting Z-score and P-value are interprested to show features with high or low value spatial clustersThe resultant z-scores and p-values tell you where features with either high or low values cluster spatially. Statistical significance is measured with P-value of the feature, and intensity of hotspot is interpreted through Z-score, where a high positive z-score and small p-value indicates a hotspot, a low negative z-score and small p-value indicates a coldspot, and unlikely spatial clustering is indicated by either a z-score near zero or a large p-value. I use the Getis-Ord-Gi* statistic for my analysis for it's high/low cluster analysis ability. The Getis-Ord Gi* statistic for spatial autocorrelation is as follows:
<br><br>
<img src="../project2_486/GetisOrdGi.png?raw=true"/>

---

## Background and the Input Data
<img src="../project2_486/WaterQualityStations.jpg?raw=true"/>

### Nutrient Pollution and the Chesapeake Bay
Nutrient pollution is a significant problem globally across watersheds, where nitrogen and phosphorus runoff are often the focus of analysis, research, debate, and management efforts, due to their potential for significant watershed disturbance as limiting plant nutrients. Some other high profile nutrient water quality measures are dissolved carbon (another limiting nutrient), suspended sediments (for implications of turbidity and carrying dissolved materials), and dissolved oxygen (as an important measure of ecosystem health). Nitrogen and phosphorus exist in many forms in the environment (nitrate, ammonia, phosphate, phosphorus salts), and therefore there are are many tests for both. 
### Water Quality Data
The Chesapeake Bay Program's Water Quality Database is an open source platform for selecting and downloading measured and calculated physical and nutrient parameters in the geographic extent of the Chesapeake Bay and tidal tributaries for their data collection from 1984-present. The data can is downloaded with geographic attributes, the smallest being 'Water Quality Station', and with other options like Hydrologic Unit and County/City. 

---

## Data Analysis

---

## Identifying Hotspots and Looking Closer
<img src="../project2_486/NutrientHotspots.jpg?raw=true"/>
<br><br>
<img src="../project2_486/HotspotCloserLook.jpg?raw=true"/>
<br><br>
<img src="../project2_486/MontourPowerPlantHotspot.jpg?raw=true"/>
<br><br>
<img src="../project2_486/MonocasyRiverHotspot.jpg?raw=true"/>
<br><br>
<img src="../project2_486/BackRiverHotspot.jpg?raw=true"/>
<br><br>

---

## Conclusions

---

