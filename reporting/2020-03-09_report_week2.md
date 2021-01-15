# report week 2 

# Monday 09 February 

- Stage start at Cerema as a deeplearner trainie 
- Getting dataset
- Start Murex project

# Thuesday 10 February 

## Source : 

**Loading Data from OpenStreetMap with Python and the Overpass API**
https://towardsdatascience.com/loading-data-from-openstreetmap-with-python-and-the-overpass-api-513882a27fd0

**Parkings depuis data.gouv.fr**
https://www.data.gouv.fr/fr/datasets/parkings/

**Getting Started on Geospatial Analysis with Python, GeoJSON and GeoPandas**
https://www.twilio.com/blog/2017/08/geospatial-analysis-python-geojson-geopandas.html

**Deep learning #5 | Entrainement d'un modèle**
https://www.youtube.com/watch?v=BHs_2ttLRXk&list=PLpEPgC7cUJ4b1ARx8PyIQa_sdZRL2GXw5&index=5

**Keras pour les débutants: On fait une voiture autonome!**
https://www.youtube.com/watch?v=JogUFFcfIYg

# Wednesday 11 Frabruary

Audit QGIS / NEAT (robosat.pink) / YOLT & YOLO (reconaissance "objet")

## Install qgis
https://www.gis-blog.com/how-to-install-qgis-3-on-ubuntu/

```
sudo gedit /etc/apt/sources.list
```

Add :

```
deb     http://qgis.org/debian raring main
deb-src http://qgis.org/debian raring main
```

Save, then : 

```
gpg --keyserver keyserver.ubuntu.com --recv 47765B75
gpg --export --armor 47765B75 | sudo apt-key add -
sudo apt-get update
```

purge broken packages:

```
sudo apt-get autoremove
sudo apt-get autoclean
sudo apt-get -f install
sudo apt-get autoremove qgis
sudo apt-get --purge remove qgis
```
Grass plugin : 

```
sudo apt-get install grass
sudo apt-get install qgis-plugin-grass
```

qgis:

```
sudo apt-get install qgis python-qgis
```

if it don't work : 

```
sudo apt install qgis
```
------------------------------

## Install Neat 

**Il n'y a qu'a suivre la documentation :**
https://datapink.io/datapink/neat-EO/

# Thursday 12 February 

## QGIS [ECA]

**Mise en pratique QGIS sur su plan aérien, création de sample, création d'atlas et export de features d'atlas à fin de créé un dataset**

Import parkings.geojson sur le projet, ajout d'un layer openstreetmap 

Import d'emplacements de parkings par un export geojson depuis l'api overpass turbo sur région parisienne 

**Overpassturbo :**
https://overpass-turbo.eu/

```
[timeout:40000];
(
  //area(3601403916); // France métropolitaine 1403916
  area(3600008649); // paris 8649
)->.zone;

(
  node[amenity=parking](area.zone);
  (
    way[amenity=parking](area.zone);
    (._;>;);
  );
);
out meta;
```

Drag and drop geo.json into project et select les layers souhaité + customization si nécessaire.

-------------------------------------------------------------

**Ajout de layer js depuis un leaflet (ajout de connection) :**
https://leaflet-extras.github.io/leaflet-providers/preview/ 

J'ai choisis ce plugin : Esri.WorldImagery
```
https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}
```
-------------------------------

**Création de l'atlas et ajout des features :** 
https://www.sigterritoires.fr/index.php/faire-un-atlas-avec-qgis/

Project >> New print layout "atlas" 

Ajout d'item map + génération d'atlas sur l'export d'overpassturbo 

Enfin sampling des feature de l'atlas en .png.


# Friday 13 February

## FULL REMOTE 

Mesure COVID-19, l'équipe passe en full remote via un git partagé, répartition des taches par avec trello.

**1. Git partagé**
https://github.com/hachem13/StageCerema

**2. Trello**
https://trello.com/b/oE3T8HdO/stage-cerema

**3. Documentation** 
"URL à venir"
