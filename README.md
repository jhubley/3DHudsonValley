# 3DHudsonValley
Elevation Data from:<br/>
[USGS 1/3 arc-second DEM](http://viewer.nationalmap.gov/basic/?basemap=b1&category=ned,nedsrc&title=3DEP%20View)

Used [QGIS](http://www.qgis.org/en/site) to convert Arcgrid file to GeoTIFF.
Used [GDAL](http://www.gdal.org) to convert GeoTIFF to bin file. Command is:<br/>
gdal_translate -scale 982 1905 0 65535 -outsize 10 10 -ot UInt16 -of ENVI hudsonvalley.tif hudsonvalley.bin

I then used GDAL some more to output a hill-shade TIFF and a color-relief TIFF.
Good info on those methods [here](https://www.mapbox.com/tilemill/docs/guides/terrain-data).

You can combine the hillshade and color-relief a few different ways. One way is with [this Python script](http://fwarmerdam.blogspot.com/2010/01/hsvmergepy.html).
I, however, just opened both the hillshade and color-relief files in Photoshop, set them both at 50% transparency, layered one on top of the other, then flattened. I like the results I got this way.