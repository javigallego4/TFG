Folder Structure

|-WV3: Contains the Worldview 3 multispectral (+-1.4 m resolution) and panchromatic (+-0.34 m resolution) imagery, captured on
|      the 20th of June 2021. More info: https://earth.esa.int/eogateway/missions/worldview-3.
|      The CRS is of the imagery is: https://epsg.io/32630.
|
|---> polygon_*ID*: Each folder within the WV3 folder contains WV3 imagery clipped to the area of the polygon bounding a
|                  juniper, as well as a binary mask of that area where the pixels corresponding to the digitized junipers
|                  are given the value 1, and the rest of the pixels 0.
|
|-GIS: Contains the shapefiles containing the polygons used to generate the WV3 data.
|
|---> juniper_contours_4326: Polygons of the juniper digitization used for the binary masks, in EPSG:4326.
|
|---> juniper_contours_32630: Polygons of the juniper digitization used for the binary masks, in EPSG:32630.
|
|---> juniper_squares_4326: Polygons of the squares corresponding to the subdivision of the WV3 data. The ID of the polygon
|                           corresponds to the *ID* of the folders in the WV3 folder. EPSG:4326.
|
|---> juniper_squares_32630: Polygons of the squares corresponding to the subdivision of the WV3 data. The ID property of
|                            the polygon corresponds to the *ID* of the folders in the WV3 folder. EPSG:32630.