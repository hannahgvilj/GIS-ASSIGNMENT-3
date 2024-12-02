# Map 1: Segovia, Castilla y León Monterrubio Town Region 
**BACKGROUND**
Our challenge group isolated a region in Segovia, Castilla y Leon called Monterrubio as it lies directly within the highest density of Microtus Arvalis in the province. We are using this as our inital testing site as it will be the easiest to extract data from due to the high vole concentrations. Moreover, there is a livestock corridor (cañada real leonesa oriental) which we isolated as an area for rewilding (which we coincidentally visited on our field trip on friday). 
**ADDED LAYERS**
Layer 1: Microtus Arvalius Frequency: `https://www.gbif.org/occurrence/map?taxon_key=2438606&gadm_gid=ESP.5_1`
Layer 2: Cattle Livestock Corridor: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMVPE`
Layer 3: Hydrological layer: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLCITDTSHYCAL`
Layer 4: Red Natura 2000: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSPSZEP`
Layer 5: Cropland Borders: `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLAYGDTSLCPOL2021`
**Geoprocessing:** 
1. I then tried to remove duplicated laters from a stepp bird later to provide a colour scale/frequency distribution: `[C:/Users/localuser/Downloads/enre_cyl_sens_ambi_aves_este.gpkg|layername=enre_cyl_sens_ambi_aves_este`](https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMAES)`
This was unsuccessful, as the file format did not allow for categorization or graduation in the properties. I tried several geoprocessing toold and redownloaded and re-input the later, however, geoprocessing was unsuccessful in every regard, therefore the later way not used.
2. I then tried buffer the hydrological later with 5m per the Castilla y Leon regulations, however, the projection was in degrees, so the buffer would not work. I had to reproject the later from degrees to meters in order to successfully buffer the river. 
3. this was not significantly visible on the map once done so: *  Export > Save Features As....
* In the CRS section, I clicked on the drop-down menu and choose a projected CRS suitable for my region. * UTM (Universal Transverse Mercator): My data was within one UTM zone, so I selected the appropriate zone (e.g., WGS 84 / UTM Zone 33N: EPSG 32633).
