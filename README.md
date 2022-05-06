# HackingEDPlanningV2-Challenge2

<a href="http://www.youtube.com/watch?feature=player_embedded&v=aTGlGLpbQ7o" target="_blank"><img src="https://img.evbuc.com/https%3A%2F%2Fcdn.evbuc.com%2Fimages%2F237802049%2F336870561013%2F1%2Foriginal.20220228-102209?w=800&auto=format%2Ccompress&q=75&sharp=10&rect=0%2C54%2C1200%2C600&s=92cc71cae0ff03ed75357a1f0aef9819" 
alt="Introductory video" width="720" height="360" border="10" /></a>

🇫🇷 [Version française](#version-française)

🇪🇸 [Versión en Español](#versi%C3%B3n-en-espa%C3%B1ol)

Note: By accessing this repository and the corresponding files, you agree to a non-disclosure agreement. To get a copy, please write to development@iiep.unesco.org

🧐 Climate  change-related sea level rise is an increasing threat to livelihoods in  coastal regions around the world, with the education system not being  an exception. Ministries of Education need a way of determining which schools will be under the sea level first, so that mitigation and adaptation plans can be set into place.

🎯 The objective of the challenge is to create a methodology that uses Copernicus GLO-30 fine DEM to determine, based on a projected sea level rise, the areas that will be under the sea level for a given year, the schools that will be impacted, and, time permitting, the school-age population that will be affected. Participants joining this challenge are encouraged to use QGIS, although any FOSS is also welcomed.

This methodology will allow Ministries of Education to determine which schools to refurbish first, where to locate new schools, and the communities that will need additional educational services as the sea level rises.

⛑ Participants joining this challenge are encouraged to use QGIS, although any FOSS is also welcomed.

# Data

## Digital Elevation Model

The Copernicus GLO-30 Digital Elevation Model is a Digital Surface Model (DSM) which represents the surface of the Earth including buildings, infrastructure and vegetation. This DSM is derived from an edited DSM named WorldDEM, where flattening of water bodies and consistent flow of rivers has been included. In addition, editing of shore- and coastlines, special features such as airports, and implausible terrain structures has also been applied. It requires a free account to [download data](https://portal.opentopography.org/raster?opentopoID=OTSDEM.032021.4326.3) for any portion of the world. 

In the interest of time, the GeoTIFF for Bangladesh has already been downloaded [here](https://box.iiep.unesco.org/s/9ec4QpzcnK4Wtob). 

## School location 

### School in Bangladesh

A point layer containing each school in Bangladesh, along with other attributes, can be downloaded [here](https://data.humdata.org/dataset/bangladesh-education-facilities-by-lged).

### OpenStreetMap school location

As an alternative to get school localisation you can use OpenStreetMap data. OpenStreetMap is a contributive map that could be explained as the wikipedia for cartography. Everybody could contribute to make the map better and add new things. [Get more information here.](https://wiki.openstreetmap.org/wiki/About_OpenStreetMap)

School in OpenStreetMap are described with at least the tag `"amenity"="school"` and more information could be added as the name, the website or the capacity. A wiki article give you more information [here](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dschool).

To dowload only the school in OpenStreetMap you can use a service called Overpass turbo with this formula : 

```
way["amenity"="school"]({{bbox}}); 			//filter school on the mapview
out center;									//transform all as center point
```

[Access this tool](https://overpass-turbo.eu/s/1i3e) then place the map in the region of your interest and then **<button>execute</button>** the formula and  **<button>extract</button>** to download a file usable by GIS software (`.geojson` `.gpx` or `.kml`).

## Population estimates

Granular population estimates are key to determine not only which schools will be affected first, but who will be touched where and when by the rise in sea levels. The gridded population estimates here have been prepared using [WorldPop](https://www.worldpop.org/geodata/summary?id=16810) unconstrained UN-adjusted data for 2019, following the methodology outlined [here](https://github.com/iiepdev/Spatialized-school-age-populations) (Gagnon & Vargas Mesa, 2021). The file is both in GeoTIFF ([Pre-primary](https://box.iiep.unesco.org/s/P4DD8WidZtS2Cr2), [Primary](https://box.iiep.unesco.org/s/3We94pkjywjkTJS), and [Secondary](https://box.iiep.unesco.org/s/eR4jcepHCEno4Qs)) and in [polygon](https://box.iiep.unesco.org/s/dnsswDPRdXsWCap) format (which contains single years of age and reconstructed school age populations as attributes)[^1]. 

## Flooded areas

Different image collections exist within GEE to obtain flooding patterns. Below is a non-exhaustive list.

|Name of the data source|Frequency|Time span|Resolution|Code|
|:----|:----|:----|:----|:----|
|Sentinel-1 SAR GRD|Daily|2014-Present|10 meters|[Sentinel-1 SAR GRD](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD)|
|Global Flood Database v1|Daily|2000-2018|30 meters|[Global Flood Database](https://developers.google.com/earth-engine/datasets/catalog/GLOBAL_FLOOD_DB_MODIS_EVENTS_V1)|
|JRC Monthly Water History, v1.3|Monthly|1984-2020|30 meters|[JRC Monthly Water History](https://developers.google.cn/earth-engine/datasets/catalog/JRC_GSW1_3_MonthlyHistory)|

[^1]: Note that the information in GeoTIFF format comes with a resolution of 100m by 100m, while the vector format comes in a 1Km by 1Km grid.



# How to use this GitHub repository ? 

If you have never used github repository you can download the content of this repository by clicking on the button **Code** and then **download zip**. If you want you can start to use github by forking this project as a base for your project and share your work on Github. 

![image](https://user-images.githubusercontent.com/20289907/165938434-c12486a7-b9ae-43e8-81f2-0e15e279bfd3.png)

# Version française

# Versión en Español

Nota: Al acceder a este repositorio y a los archivos correspondientes, usted acepta un acuerdo de no divulgación. Para obtener una copia, escriba a development@iiep.unesco.org

🧐 La subida del nivel del mar por efectos del cambio climático es una amenaza creciente para la subsistencia en las regiones costeras de todo el mundo, y los sistemas educativos no están exentos de este problema. Los ministerios de educación necesitan una forma de determinar qué escuelas se encontrarán primero bajo el nivel del mar, para poder definir planes de mitigación y adaptación.

🎯 El objetivo del reto es crear una metodología que utilice el MDE fino GLO-30 de Copernicus para determinar, basándose en una proyección de la subida del nivel del mar, las zonas que estarán bajo el agua en un año determinado, las escuelas que se verán afectadas por esta crecida y, si el tiempo lo permite, la población en edad escolar que se verá afectada.

Esta metodología permitiría a los ministerios de educación determinar qué escuelas hay que renovar en prioridad, dónde ubicar nuevas escuelas, y cómo identificar las comunidades que necesitarán servicios educativos adicionales a medida que suba el nivel del mar.

⛑ Se recomienda que las personas que se unan a este reto utilicen QGIS, aunque cualquier software libre y de código abierto también es bienvenido.
Datos

# Modelo digital de elevación

El Modelo Digital de Elevación GLO-30 de Copernicus es un Modelo Digital de Superficie (DSM) que representa la superficie de la Tierra, incluyendo edificios, infraestructuras y vegetación. Este MDS se deriva de un MDS editado denominado WorldDEM, en el que se ha incluido el aplanamiento de las masas de agua y el flujo constante de los ríos. Además, se ha aplicado la edición de las orillas y las costas, las características especiales como los aeropuertos y las estructuras del terreno inverosímiles. Se requiere una cuenta gratuita para [descargar los datos](https://portal.opentopography.org/raster?opentopoID=OTSDEM.032021.4326.3) de cualquier parte del mundo.

En aras del tiempo, el GeoTIFF de Bangladesh ya se ha descargado [aquí](https://box.iiep.unesco.org/s/9ec4QpzcnK4Wtob).

# Ubicación de la escuela

## Escuela en Bangladesh

[Aquí](https://data.humdata.org/dataset/bangladesh-education-facilities-by-lged) se puede descargar una capa de puntos que contiene cada escuela de Bangladesh, junto con otros atributos.

## Ubicación de la escuela en OpenStreetMap
Como alternativa para obtener la localización de la escuela puede utilizar los datos de OpenStreetMap. OpenStreetMap es un mapa colaborativo que podría explicarse como la Wikipedia de la cartografía. Todo el mundo puede contribuir a mejorar el mapa y añadir cosas nuevas. [Obtenga más información aquí](https://wiki.openstreetmap.org/wiki/About_OpenStreetMap).

Las escuelas en OpenStreetMap se describen al menos con la etiqueta `"amenity"="school"` y se puede añadir más información como el nombre, el sitio web o la capacidad. Un artículo de la wiki ofrece más información [aquí](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Dschool).

Para descargar sólo la escuela en OpenStreetMap puede utilizar un servicio llamado Overpass turbo con esta fórmula:

```
way["amenity"="school"]({{bbox}}); 			//Filtra los colegios en la vista actual
out center;									// Transforma todos en el punto central 
```

[Acceda a esta](https://overpass-turbo.eu/s/1i3e) herramienta y coloque el mapa en la región de su interés y luego ejecute la fórmula y extraiga para descargar un archivo utilizable por el software SIG (`. geojson` . `gpx` o . `kml`).

# Estimaciones de población

Las estimaciones granulares de población son fundamentales para determinar no sólo qué escuelas se verán afectadas en primer lugar, sino también a quién se verá afectado, así como dónde y cuándo, al momento de la subida del nivel del mar. Las estimaciones de población cuadriculadas aquí se han preparado utilizando datos [WorldPop](https://www.worldpop.org/geodata/summary?id=16810) no restringidos ajustados a los parámetros de las Naciones Unidas para el año 2019, siguiendo la metodología descrita [aquí](https://github.com/iiepdev/Spatialized-school-age-populations) (Gagnon & Vargas Mesa, 2021). El archivo está tanto en GeoTIFF ([preescolar](https://box.iiep.unesco.org/s/P4DD8WidZtS2Cr2), [primaria](https://box.iiep.unesco.org/s/3We94pkjywjkTJS) y [secundaria](https://box.iiep.unesco.org/s/eR4jcepHCEno4Qs)) como en formato de [polígono](https://box.iiep.unesco.org/s/dnsswDPRdXsWCap) (que contiene como atributos las poblaciones de un solo año de edad y de edad escolar reconstruida)[^2].

# Zonas inundadas

Existen diferentes colecciones de imágenes dentro de GEE para obtener patrones de inundación. A continuación se presenta una lista no exhaustiva.

|Nombre de la fuente de datos|Frecuencia|Periodo de tiempo|Resolución|Código|
|:----|:----|:----|:----|:----|
|Sentinel-1 SAR GRD|Diaria|2014-Present|10 metros|[Sentinel-1 SAR GRD](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD)|
|Base de datos mundial sobre inundaciones v1|Diaria|2000-2018|30 metros|[Global Flood Database](https://developers.google.com/earth-engine/datasets/catalog/GLOBAL_FLOOD_DB_MODIS_EVENTS_V1)|
|Historia mensual del agua del CCI, v1.3|Mensual|1984-2020|30 metros|[JRC Monthly Water History](https://developers.google.cn/earth-engine/datasets/catalog/JRC_GSW1_3_MonthlyHistory)|


[^2]: Note que la información en formato GeoTIFF tiene una resolución de 100m por 100m, mientras que la versión vectorial tiene information de 1Km por 1Km.
