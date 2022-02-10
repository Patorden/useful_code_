# Get coordinates from a table 

````Python

# Here we install the geopandas package for analysing geospatial data

pip install geopandas 

import pandas as pd
import geopandas as gpd
import matplotlib.pyplot as plt

# Lets assign the coordinates form the df 

data_gdf = gpd.GeoDataFrame(df, geometry = gpd.points_from_xy(df['x_lon'], df['y_lat']))

# This next line indicates whaty tipe of data we are dealing with

type(data_gdf) # The output should say:geopandas.geodataframe.GeoDataFrame

# We can plot the coordinates in a simple boxplot:

data_gdf.plot()

# Then we assign the Datum and Proyections: 

ESRI_WKT = 'GEOGCS["GCS_WGS_1984",DATUM["D_WGS_1984", SPHEROID["WGS_1984",6378137,298.257223563]],PRIMEM["Greenwich",0],UNIT["Degree",0.017453292519943295]]'

# Then we can export the file as a .shp:

data_gdf.to_file(filename='urb.shp', driver = 'ESRI Shapefile')

```
