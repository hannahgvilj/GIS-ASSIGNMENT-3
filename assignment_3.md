# Map 1: Segovia, Castilla y León Monterrubio Town Region 
**BACKGROUND**
Our challenge group isolated a region in Segovia, Castilla y Leon called Monterrubio as it lies directly within the highest density of Microtus Arvalis in the province. We are using this as our inital testing site as it will be the easiest to extract data from due to the high vole concentrations. Moreover, there is a livestock corridor (cañada real leonesa oriental) which we isolated as an area for rewilding (which we coincidentally visited on our field trip on friday). 
**ADDED LAYERS**
* 1. Microtus Arvalius Frequency: `https://www.gbif.org/occurrence/map?taxon_key=2438606&gadm_gid=ESP.5_1`
* 2. Cattle Livestock Corridor: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMVPE`
* 3. Hydrological layer: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLCITDTSHYCAL`
* 4. Red Natura 2000: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSPSZEP`
* 5. Cropland Borders: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLAYGDTSLCPOL2021`
**Geoprocessing:** 
* 1. I then tried to remove duplicated laters from a stepp bird later to provide a colour scale/frequency distribution: `[C:/Users/localuser/Downloads/enre_cyl_sens_ambi_aves_este.gpkg|layername=enre_cyl_sens_ambi_aves_este`](https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMAES)`
This was unsuccessful, as the file format did not allow for categorization or graduation in the properties. I tried several geoprocessing toold and redownloaded and re-input the later, however, geoprocessing was unsuccessful in every regard, therefore the later way not used.
* 2. I then tried buffer the hydrological later with 3m and 5m per the Castilla y Leon regulations, however, the projection was in degrees, so the buffer would not work. I had to reproject the later from degrees to meters in order to successfully buffer the river. 
* 3. this was not significantly visible on the map once done so: *  Export > Save Features As...In the CRS section, I clicked on the drop-down menu and choose a projected CRS suitable for my region. * UTM (Universal Transverse Mercator): My data was within one UTM zone, so I selected the appropriate zone (e.g., WGS 84 / UTM Zone 33N: EPSG 32633).--> this reprojected the layer into meters so I could buffer it. However, as the buffere was quite small, neitehr the 3m nor 5m was not visible on the map, therefore this later was not used.
```python
RUN: buffer of hydrological layer:
QGIS version: 3.34.11-Prizren
QGIS code revision: 2904bcec
Qt version: 5.15.13
Python version: 3.12.6
GDAL version: 3.9.2
GEOS version: 3.12.2-CAPI-1.18.2
PROJ version: Rel. 9.4.0, March 1st, 2024
PDAL version: 2.6.3 (git-version: b5523a)
Algorithm started at: 2024-11-28T18:37:39
Algorithm 'Buffer' starting…
Input parameters:
{ 'DISSOLVE' : False, 'DISTANCE' : 3, 'END_CAP_STYLE' : 0, 'INPUT' : 'Hydro_layer_M.gpkg|layername=hydro_M', 'JOIN_STYLE' : 0, 'MITER_LIMIT' : 2, 'OUTPUT' : 'TEMPORARY_OUTPUT', 'SEGMENTS' : 5, 'SEPARATE_DISJOINT' : False }
```
* 4. I then downloaded 2 types of predator bird data from gbif:
     * https://doi.org/10.15468/dl.fu69tw
     * https://doi.org/10.15468/dl.s7ebzd
  * none of them worked correctly on my laters
* 5. I then input the Natura 2000 layer. After this was input, this map supports our challenge proposal through the yellow square identifying a hotspot for vole activity. Rewilding measures can prioritize the surrounding livestock corridors (red lines) and adjacent protected areas (dark green). The red livestock corridors intersect the high-vole-density area, making them ideal for reintroducing grazing animals. Grazing reduces ground cover, limiting vole habitat and food availability. The protected Red Natura 2000 area (dark green) near the yellow square is critical for predator conservation. Birds of prey (owls, kestrels) and carnivores thrive in these areas, naturally reducing vole populations. The blue rivers near the vole hotspot can serve as key areas for rewilding efforts. Healthy riparian zones attract diverse predators. [MAP_1.pdf](https://github.com/user-attachments/files/17978379/MAP_1.pdf)

# Map 2: ELevation of Monterrubio Region and Buffers of Livestock Corridoors and River
**BACKGROUND**
I thought adding a layer displaying elevation in the region may aid in analyzing slope, elevation, and terrain features that might influence vole movement and predator suitability. As voles typically prefer medium-low elevations such as grasslands, meadows, agricultural fields, and forest edges, this layer could aid in displaying that. I thought focusing on lowland areas with rich vegetation (agricultural fields and meadows) is likely where vole concentrations are highest, as well as surrounding area analysis could confirm our proposal. 
**ADDED LAYERS**
* 1. Cattle Livestock Corridor: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMVPE`
* 2. Hydrological layer: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLCITDTSHYCAL`
* 3. Cropland Borders: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLAYGDTSLCPOL2021`
* 4. Elevation Levels - digital terrain model: slopes `https://idecyl.jcyl.es/geonetwork/srv/eng/catalog.search#/metadata/SPAGOBCYLCITDTSELPEN0811`
