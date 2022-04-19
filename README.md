# HackingEDPlanningV2-Challenge2

<a href="http://www.youtube.com/watch?feature=player_embedded&v=aTGlGLpbQ7o" target="_blank"><img src="https://img.evbuc.com/https%3A%2F%2Fcdn.evbuc.com%2Fimages%2F237802049%2F336870561013%2F1%2Foriginal.20220228-102209?w=800&auto=format%2Ccompress&q=75&sharp=10&rect=0%2C54%2C1200%2C600&s=92cc71cae0ff03ed75357a1f0aef9819" 
alt="IMAGE ALT TEXT HERE" width="720" height="360" border="10" /></a>

🧐 Climate  change-related sea level rise is an increasing threat to livelihoods in  coastal regions around the world, with the education system not being  an exception. Ministries of Education need a way of determining which schools will be under the sea level first, so that mitigation and adaptation plans can be set into place.

🎯 The objective of the challenge is to create a methodology that uses Copernicus GLO-30 fine DEM to determine, based on a projected sea level rise, the areas that will be under the sea level for a given year, the schools that will be impacted, and, time permitting, the school-age population that will be affected. Participants joining this challenge are encouraged to use QGIS, although any FOSS is also welcomed.

This methodology will allow Ministries of Education to determine which schools to refurbish first, where to locate new schools, and the communities that will need additional educational services as the sea level rises.

⛑ Participants joining this challenge are encouraged to use QGIS, although any FOSS is also welcomed.

# Data

## Digital Elevation Model

The Copernicus GLO-30 Digital Elevation Model is a Digital Surface Model (DSM) which represents the surface of the Earth including buildings, infrastructure and vegetation. This DSM is derived from an edited DSM named WorldDEM, where flattening of water bodies and consistent flow of rivers has been included. In addition, editing of shore- and coastlines, special features such as airports, and implausible terrain structures has also been applied. It requires a free account to [download data](https://portal.opentopography.org/raster?opentopoID=OTSDEM.032021.4326.3) for any portion of the world. 

In the interest of time, the GeoTIFF for Bangladesh has already been downloaded [here](https://box.iiep.unesco.org/s/9ec4QpzcnK4Wtob). 

## School location 

A point layer containing each school in Bangladesh, along with other attributes, can be downloaded [here](https://data.humdata.org/dataset/bangladesh-education-facilities-by-lged).

## Population estimates

Granular population estimates are key to determine not only which schools will be affected first, but who will be touched where and when by the rise in sea levels. The gridded population estimates here have been prepared using [WorldPop](https://www.worldpop.org/geodata/summary?id=16810) unconstrained UN-adjusted[^1] data for 2020, following the methodology outlined [here](https://github.com/iiepdev/Spatialized-school-age-populations) (Gagnon & Vargas Mesa, 2021). The file is both in [GeoTIFF]() and in [polygon]() format. 

## Flooded areas

Different image collections exist within GEE to obtain flooding patterns. Below is a non-exhaustive list.

|Name of the data source|Frequency|Time span|Resolution|Code|
|:----|:----|:----|:----|:----|
|Sentinel-1 SAR GRD|Daily|2014-Present|10 meters|[Sentinel-1 SAR GRD](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD)|
|Global Flood Database v1|Daily|2000-2018|30 meters|[Global Flood Database](https://developers.google.com/earth-engine/datasets/catalog/GLOBAL_FLOOD_DB_MODIS_EVENTS_V1)|
|JRC Monthly Water History, v1.3|Monthly|1984-2020|30 meters|[JRC Monthly Water History](https://developers.google.cn/earth-engine/datasets/catalog/JRC_GSW1_3_MonthlyHistory)|

[^1]: While the information downloaded from WorldPop is unconstrained data, it was adjusted to UN estimates using the information produced by the [UN Population Division](https://population.un.org/wpp/Download/Standard/Interpolated/), particularly the [Annual Population by Age - Both Sexes](https://population.un.org/wpp/Download/Files/1_Indicators%20(Standard)/EXCEL_FILES/5_Interpolated/WPP2019_INT_F03_1_POPULATION_BY_AGE_ANNUAL_BOTH_SEXES.xlsx). This applies only for the vector file.
